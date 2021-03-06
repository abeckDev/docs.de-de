---
title: HttpCookieSession
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 101cb624-8303-448a-a3af-933247c1e109
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c06efd7450afe93eaecca1e678eb6f8bf5de7a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="httpcookiesession"></a>HttpCookieSession
In diesem Beispiel wird das Erstellen eines benutzerdefinierten Protokollkanals für die Verwendung von HTTP-Cookies für die Sitzungsverwaltung veranschaulicht. Dieser Kanal ermöglicht die Kommunikation zwischen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Diensten und ASMX-Clients oder zwischen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients und ASMX-Diensten.  
  
 Wenn ein Client eine Webmethode in einem sitzungsbasierten ASMX-Webdienst aufruft, führt das [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Modul Folgendes aus:  
  
-   Generiert eine eindeutige ID (Sitzungs-ID).  
  
-   Generiert das Sitzungsobjekt und ordnet es der eindeutigen ID zu.  
  
-   Fügt die eindeutige ID dem HTTP-Antwortheader Set-Cookie hinzu und sendet diesen an den Client.  
  
-   Identifiziert den Client in nachfolgenden Aufrufen auf Grundlage der an ihn gesendeten Sitzungs-ID.  
  
 Der Client schließt diese Sitzungs-ID in nachfolgenden Anforderungen an den Server ein. Der Server lädt mithilfe der Sitzungs-ID vom Client das entsprechende Sitzungsobjekt für den aktuellen HTTP-Kontext.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpCookieSession`  
  
## <a name="httpcookiesession-channel-message-exchange-pattern"></a>HttpCookieSession-Nachrichtenaustauschmuster für Kanal  
 In diesem Beispiel werden Sitzungen für ASMX-ähnliche Szenarios aktiviert. Unten im Kanalstapel befindet sich der HTTP-Transport, der <xref:System.ServiceModel.Channels.IRequestChannel> und <xref:System.ServiceModel.Channels.IReplyChannel> unterstützt. Der Kanal stellt Sitzungen für die höheren Ebenen des Kanalstapels bereit. Im Beispiel werden zwei Kanäle implementiert, die Sitzungen unterstützen (<xref:System.ServiceModel.Channels.IRequestSessionChannel> und <xref:System.ServiceModel.Channels.IReplySessionChannel>).  
  
## <a name="service-channel"></a>Dienstkanal  
 Im Beispiel wird ein Dienstkanal in der `HttpCookieReplySessionChannelListener`-Klasse bereitgestellt. Diese Klasse implementiert die <xref:System.ServiceModel.Channels.IChannelListener>-Schnittstelle und konvertiert den <xref:System.ServiceModel.Channels.IReplyChannel>-Kanal weiter unten im Kanalstapel in <xref:System.ServiceModel.Channels.IReplySessionChannel>. Dieser Prozess kann folgendermaßen unterteilt werden:  
  
-   Wenn der Kanallistener geöffnet wird, akzeptiert er einen inneren Kanal vom inneren Listener. Da es sich bei dem inneren Listener um einen Datagrammlistener handelt und die Lebensdauer eines akzeptierten Kanals unabhängig von der Lebensdauer des Listeners ist, kann der innere Listener geschlossen und nur der innere Kanal beibehalten werden.  
  
    ```  
                this.innerChannelListener.Open(timeoutHelper.RemainingTime());  
    this.innerChannel = this.innerChannelListener.AcceptChannel(timeoutHelper.RemainingTime());  
    this.innerChannel.Open(timeoutHelper.RemainingTime());  
    this.innerChannelListener.Close(timeoutHelper.RemainingTime());  
    ```  
  
-   Wenn der Prozess zum Öffnen abgeschlossen ist, wird eine Nachrichtenschleife zum Empfangen von Nachrichten vom inneren Kanal eingerichtet.  
  
    ```  
    IAsyncResult result = BeginInnerReceiveRequest();  
    if (result != null && result.CompletedSynchronously)  
    {  
       // do not block the user thread  
       if (this.completeReceiveCallback == null)  
       {  
          this.completeReceiveCallback = new WaitCallback(CompleteReceiveCallback);  
       }  
       ThreadPool.QueueUserWorkItem(this.completeReceiveCallback, result);  
    }  
    ```  
  
-   Wenn eine Nachricht eingeht, prüft der Dienstkanal die Sitzungs-ID und führt ein De-Multiplexing für den entsprechenden Sitzungskanal durch. Der Kanallistener verwaltet ein Wörterbuch, das die Sitzungs-IDs den Sitzungskanalinstanzen zuordnet.  
  
    ```  
    Dictionary<string, IReplySessionChannel> channelMapping;  
    ```  
  
 Die `HttpCookieReplySessionChannel` -Klasse implementiert <xref:System.ServiceModel.Channels.IReplySessionChannel>. In höheren Ebenen des Kanalstapels wird die <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A>-Methode aufgerufen, um Anforderungen für diese Sitzung zu lesen. Jeder Sitzungskanal verfügt über eine private Meldungswarteschlange, die vom Dienstkanal aufgefüllt wird.  
  
```  
InputQueue<RequestContext> requestQueue;  
```  
  
 Wenn die <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A>-Methode aufgerufen wird und sich keine Meldungen in der Meldungswarteschlange befinden, wartet der Kanal für einen angegebenen Zeitraum und beendet sich dann selbst. So werden die für Nicht-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients erstellten Sitzungskanäle bereinigt.  
  
 Mit `channelMapping` wird `ReplySessionChannels` nachverfolgt. Außerdem wird der zugrunde liegende `innerChannel` erst geschlossen, wenn alle akzeptierten Kanäle geschlossen wurden. So kann `HttpCookieReplySessionChannel` über die Lebensdauer von `HttpCookieReplySessionChannelListener` hinaus vorhanden sein. Außerdem besteht nicht die Gefahr, dass der Listener durch die Garbage Collection entfernt wird, da die akzeptierten Kanäle über den `OnClosed`-Rückruf einen Verweis auf den Listener beibehalten.  
  
## <a name="client-channel"></a>Clientkanal  
 Der entsprechende Clientkanal befindet sich in der `HttpCookieSessionChannelFactory`-Klasse. Bei der Kanalerstellung schließt die Kanalfactory den inneren Anforderungskanal mit einem `HttpCookieRequestSessionChannel` ein. Die `HttpCookieRequestSessionChannel`-Klasse leitet die Aufrufe des zugrunde liegenden Anforderungskanals weiter. Wenn der Client den Proxy schließt, sendet `HttpCookieRequestSessionChannel` eine Meldung an den Dienst, mit der angegeben wird, dass der Kanal geschlossen wird. So kann der Dienstkanalstapel den verwendeten Sitzungskanal ordnungsgemäß beenden.  
  
## <a name="binding-and-binding-element"></a>Bindung und Bindungselement  
 Nach dem Erstellen der Dienst- und Clientkanäle ist der nächste Schritt das Integrieren der Kanäle in der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Laufzeit. Kanäle werden durch Bindungen und Bindungselemente für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verfügbar gemacht. Eine Bindung besteht aus einem oder mehreren Bindungselementen. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt mehrere systemdefinierte Bindungen bereit, beispielsweise BasicHttpBinding und WSHttpBinding. Die `HttpCookieSessionBindingElement`-Klasse enthält die Implementierung des Bindungselements. Sie überschreibt die Methoden zur Kanallistener- und Kanalfactoryerstellung, um die erforderlichen Instanziierungen des Kanallisteners und der Kanalfactory auszuführen.  
  
 Im Beispiel werden Richtlinienassertionen für die Dienstbeschreibung verwendet. So können im Beispiel die Kanalanforderungen für andere Clients veröffentlicht werden, die den Dienst verwenden können. Dieses Bindungselement veröffentlicht beispielsweise Richtlinienassertionen, damit potenzielle Clients wissen, dass Sitzungen unterstützt werden. Da im Beispiel die `ExchangeTerminateMessage`-Eigenschaft in der Bindungselementkonfiguration aktiviert wird, werden die erforderlichen Assertionen hinzugefügt, um zu zeigen, dass der Dienst eine zusätzliche Meldungsaustauschaktion zum Beenden der Sitzungskommunikation unterstützt. Clients können diese Aktion dann verwenden. Im folgenden WSDL-Code werden die aus `HttpCookieSessionBindingElement` erstellten Richtlinienassertionen veranschaulicht.  
  
```xml  
<wsp:Policy wsu:Id="HttpCookieSessionBinding_IWcfCookieSessionService_policy" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wsp:ExactlyOne>  
<wsp:All>  
<wspe:Utf816FFFECharacterEncoding xmlns:wspe="http://schemas.xmlsoap.org/ws/2004/09/policy/encoding"/>  
<mhsc:httpSessionCookie xmlns:mhsc="http://samples.microsoft.com/wcf/mhsc/policy"/>  
</wsp:All>  
</wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 Die `HttpCookieSessionBinding`-Klasse ist eine vom System bereitgestellte Bindung, die das zuvor beschriebene Bindungselement verwendet.  
  
## <a name="adding-the-channel-to-the-configuration-system"></a>Hinzufügen des Kanals zum Konfigurationssystem  
 Im Beispiel werden zwei Klassen bereitgestellt, die den Beispielkanal durch Konfiguration verfügbar machen. Die erste ist ein <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> für das `HttpCookieSessionBindingElement`. Dem `HttpCookieSessionBindingConfigurationElement`, das sich von <xref:System.ServiceModel.Configuration.StandardBindingElement> herleitet, wird der Großteil der Implementierung übertragen. `HttpCookieSessionBindingConfigurationElement` verfügt über Eigenschaften, die den Eigenschaften von `HttpCookieSessionBindingElement` entsprechen.  
  
### <a name="binding-element-extension-section"></a>Abschnitt für Bindungselementerweiterungen  
 Der Abschnitt `HttpCookieSessionBindingElementSection` ist ein <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>, das die `HttpCookieSessionBindingElement` für das Konfigurationssystem verfügbar macht. Mit wenigen Überschreibungen werden der Konfigurationsabschnittsname, der Typ des Bindungselements und das Erstellen des Bindungselements definiert. Danach kann der Erweiterungsabschnitt wie folgt in einer Konfigurationsdatei registriert werden:  
  
```xml  
<configuration>        
    <system.serviceModel>        
      <extensions>          
        <bindingElementExtensions>            
          <add name="httpCookieSession"   
               type=  
"Microsoft.ServiceModel.Samples.HttpCookieSessionBindingElementElement,   
                    HttpCookieSessionExtension, Version=1.0.0.0,   
                    Culture=neutral, PublicKeyToken=null"/>  
        </bindingElementExtensions >  
      </extensions>  
  
      <bindings>  
      <customBinding>  
        <binding name="allowCookiesBinding">  
          <textMessageEncoding messageVersion="Soap11WSAddressing10" />  
          <httpCookieSession sessionTimeout="10" exchangeTerminateMessage="true" />  
          <httpTransport allowCookies="true" />  
        </binding>  
      </customBinding>  
      </bindings>        
    </system.serviceModel>    
</configuration>  
```  
  
## <a name="test-code"></a>Testcode  
 Testcode für die Verwendung dieses Beispieltransports ist in den Client- und Dienstverzeichnissen verfügbar. Er besteht aus zwei Tests: ein Test verwendet eine Bindung mit `allowCookies` festgelegt `true` auf dem Client. Im zweiten Test wird das explizite Herunterfahren (mit abschließenden Meldungsaustausch) für die Bindung aktiviert.  
  
 Wenn Sie das Beispiel ausführen, sollten Sie folgende Ausgabe erhalten:  
  
```  
Simple binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
Smart binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Installieren Sie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mithilfe des folgenden Befehls.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Siehe auch
