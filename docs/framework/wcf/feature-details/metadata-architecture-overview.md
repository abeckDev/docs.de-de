---
title: "Übersicht über die Metadatenarchitektur"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metadata [WCF], overview
ms.assetid: 1d37645e-086d-4d68-a358-f3c5b6e8205e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8890cc05ec6b0b889dafcb787e216b50a681876
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="metadata-architecture-overview"></a>Übersicht über die Metadatenarchitektur
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bietet eine umfangreiche Infrastruktur für den Export, die Veröffentlichung, den Abruf und den Import von Dienstmetadaten. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste beschreiben mithilfe von Metadaten die Interaktion mit den Endpunkten des Diensts, sodass Tools, z. B. Svcutil.exe, automatisch Clientcode für den Zugriff auf den Dienst generieren können.  
  
 Die meisten der Typen, die die Metadaten-Infrastruktur von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bilden, befinden sich im <xref:System.ServiceModel.Description>-Namespace.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die <xref:System.ServiceModel.Description.ServiceEndpoint>-Klasse, um Endpunkte in einem Dienst zu beschreiben. Sie können mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Metadaten für Dienstendpunkte generieren oder Dienstmetadaten importieren, um <xref:System.ServiceModel.Description.ServiceEndpoint>-Instanzen zu erzeugen.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt die Metadaten für einen Dienst als Instanz des <xref:System.ServiceModel.Description.MetadataSet>-Typs dar, dessen Struktur eng an das Metadaten-Serialisierungsformat gebunden ist, das in WS-MetadataExchange definiert ist. Der <xref:System.ServiceModel.Description.MetadataSet>-Typ fasst die eigentlichen Dienstmetadaten, wie WSDL (Web Services Description Language)-Dokumente, XML-Schemadokumente oder WS-Richtlinienausdrücke, in einer Auflistung von <xref:System.ServiceModel.Description.MetadataSection>-Instanzen zusammen. Jede <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType>-Instanz enthält einen bestimmten Metadaten-Dialekt und einen Bezeichner. Ein <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType>-Element kann die folgenden Elemente in seiner <xref:System.ServiceModel.Description.MetadataSection.Metadata%2A?displayProperty=nameWithType>-Eigenschaft enthalten:  
  
-   Nicht formatierte Metadaten  
  
-   Eine <xref:System.ServiceModel.Description.MetadataReference>-Instanz.  
  
-   Eine <xref:System.ServiceModel.Description.MetadataLocation>-Instanz.  
  
 <xref:System.ServiceModel.Description.MetadataReference?displayProperty=nameWithType>-Instanzen zeigen auf einen anderen MEX (Metadata Exchange)-Endpunkt, und <xref:System.ServiceModel.Description.MetadataLocation?displayProperty=nameWithType>-Instanzen zeigen mithilfe einer HTTP-URL auf ein Metadatendokument. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt die Verwendung von WSDL-Dokumenten zur Beschreibung von Dienstendpunkten, Dienstverträgen, Bindungen, Nachrichtenaustauschmustern, Nachrichten und Fehlermeldungen, die durch einen Dienst implementiert werden. Die vom Dienst verwendeten Datentypen werden in WSDL-Dokumenten mithilfe eines XML-Schemas beschrieben. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Schemaimport / Export](../../../../docs/framework/wcf/feature-details/schema-import-and-export.md). Sie können [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zum Exportieren und Importieren von WSDL-Erweiterungen für Dienstverhalten, Vertragsverhalten und Bindungselemente verwenden, die die Funktionalität eines Diensts erweitern. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Exportieren von benutzerdefinierten Metadaten für einen WCF-Erweiterung](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="exporting-service-metadata"></a>Exportieren von Dienstmetadaten  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], *metadatenexport* versteht man Beschreibung von Dienstendpunkten und Ihrer Projektion in eine parallele, standardisierte Darstellung, die Clients verwenden können, wie Sie den Dienst verwenden können. Mit einer Implementierung der abstrakten <xref:System.ServiceModel.Description.ServiceEndpoint>-Klasse können Sie Metadaten aus <xref:System.ServiceModel.Description.MetadataExporter>-Instanzen exportieren. Eine <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType>-Implementierung generiert Metadaten, die in einer <xref:System.ServiceModel.Description.MetadataSet>-Instanz gekapselt werden.  
  
 Die <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType>-Klasse stellt ein Framework für die Generierung von Richtlinienausdrücken bereit, welche die Fähigkeiten und Anforderungen einer Endpunktbindung und die zugehörigen Vorgänge, Meldungen und Fehler beschreiben. Diese Richtlinienausdrücke werden in einer <xref:System.ServiceModel.Description.PolicyConversionContext>-Instanz aufgezeichnet. Eine <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType>-Implementierung kann diese Richtlinienausdrücke dann an die von ihr generierten Metadaten anfügen.  
  
 Der <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> ruft jedes <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>-Objekt auf, das die <xref:System.ServiceModel.Description.IPolicyExportExtension>-Schnittstelle in der Bindung eines <xref:System.ServiceModel.Description.ServiceEndpoint> implementiert, wenn ein <xref:System.ServiceModel.Description.PolicyConversionContext>-Objekt für die zu verwendende <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType>-Implementierung erzeugt wird. Sie können neue Richtlinienassertionen exportieren, indem Sie die <xref:System.ServiceModel.Description.IPolicyExportExtension>-Schnittstelle in Ihren benutzerdefinierten Implementierungen des <xref:System.ServiceModel.Channels.BindingElement>-Typs implementieren.  
  
 Der <xref:System.ServiceModel.Description.WsdlExporter>-Typ stellt die Implementierung der abstrakten <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType>-Klasse in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dar. Der <xref:System.ServiceModel.Description.WsdlExporter>-Typ generiert WSDL-Metadaten mit angefügten Richtlinienausdrücken.  
  
 Um benutzerdefinierte WSDL-Metadaten oder WSDL-Ausdrücke für Endpunktverhalten, Vertragsverhalten oder Bindungselemente in einem Dienstendpunkt zu exportieren, können Sie die <xref:System.ServiceModel.Description.IWsdlExportExtension>-Schnittstelle implementieren. Der <xref:System.ServiceModel.Description.WsdlExporter> untersucht eine <xref:System.ServiceModel.Description.ServiceEndpoint>-Instanz daraufhin, ob sie Bindungselemente, Vorgangsverhalten, Vertragsverhalten und Endpunktverhalten enthält, die beim Erzeugen eines WSDL-Dokuments die <xref:System.ServiceModel.Description.IWsdlExportExtension>-Schnittstelle implementieren.  
  
## <a name="publishing-service-metadata"></a>Veröffentlichen von Dienstmetadaten  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste veröffentlichen Metadaten, indem sie einen oder mehrere Metadatenendpunkte verfügbar machen. Durch die Veröffentlichung von Dienstmetadaten werden die Dienstmetadaten mithilfe standardisierter Protokolle, wie MEX und HTTP/GET-Anforderungen, zur Verfügung gestellt. Metadatenendpunkte ähneln anderen Dienstendpunkten insofern, als dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen. Sie können einem Diensthost in der Konfiguration oder im Code Metadatenendpunkte hinzufügen.  
  
 Um Metadatenendpunkte für einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst zu veröffentlichen, müssen Sie zunächst eine Instanz des <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Dienstverhaltens zum Dienst hinzufügen. Durch das Hinzufügen einer <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>-Instanz zu einem Dienst wird der Dienst um die Fähigkeit ergänzt, Metadaten zu veröffentlichen, indem er einen oder mehrere Metadatenendpunkt verfügbar macht. Sobald Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>-Dienstverhalten hinzufügen, können Sie Metadatenendpunkte verfügbar machen, die das MEX-Protokoll unterstützen, oder Metadatenendpunkte, die auf die HTTP/GET-Anforderungen antworten.  
  
 Um Metadatenendpunkte hinzuzufügen, die das MEX-Protokoll verwenden, fügen Sie Dienstendpunkte zum Diensthost, der den Dienstvertrag, der mit dem Namen IMetadataExchange verwenden.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] definiert die <xref:System.ServiceModel.Description.IMetadataExchange> Schnittstelle, die diesen Vertrag-Dienstnamen aufweist. WS-MetadataExchange-Endpunkte oder MEX-Endpunkte können eine der vier Standardbindungen nutzen, die von den statischen Factorymethoden der <xref:System.ServiceModel.Description.MetadataExchangeBindings>-Klasse verfügbar gemacht werden, sodass eine Anpassung an die von den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Tools, wie Svcutil.exe, verwendeten Standardbindungen erreicht wird. Sie können MEX-Metadatenendpunkte auch mithilfe einer benutzerdefinierten Bindung konfigurieren.  
  
 Das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> verwendet einen <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=nameWithType>, um Metadaten für alle Dienstendpunkte in den Dienst zu exportieren. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Exportieren von Metadaten von einem Dienst finden Sie unter [exportieren und Importieren von Metadaten](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
 Das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> ergänzt den Diensthost, indem eine <xref:System.ServiceModel.Description.ServiceMetadataExtension>-Instanz als Erweiterung dem Diensthost hinzugefügt wird. Die <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> stellt die Implementierung für die Metadaten bereit, die Protokolle veröffentlichen. Sie können darüber hinaus <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> verwenden, um die Metadaten des Diensts bei Laufzeit abzurufen, indem Sie auf die <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A>-Eigenschaft zugreifen.  
  
> [!CAUTION]
>  Wenn Sie der Konfigurationsdatei Ihrer Anwendung einen MEX-Endpunkt hinzufügen und anschließend dem Diensthost im Code das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Element hinzufügen, wird sinngemäß folgende Ausnahme ausgegeben:  
>   
>  System.InvalidOperationException: Der Vertragsname "IMetadataExchange" wurde nicht in der Liste der von Dienst "Service1" implementierten Verträge gefunden. Fügen Sie der Konfigurationsdatei oder dem ServiceHost ein ServiceMetadataBehavior-Element hinzu, um die Unterstützung des Vertrags zu aktivieren.  
>   
>  Fügen Sie der Konfigurationsdatei das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Element hinzu, oder fügen Sie den Endpunkt und das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Element im Code hinzu, um das Problem zu umgehen.  
>   
>  Ein Beispiel zum Hinzufügen von <xref:System.ServiceModel.Description.ServiceMetadataBehavior> in einer Anwendungskonfigurationsdatei finden Sie unter der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md). Ein Beispiel zum Hinzufügen von <xref:System.ServiceModel.Description.ServiceMetadataBehavior> im Code finden Sie unter der [Selbsthosting](../../../../docs/framework/wcf/samples/self-host.md) Beispiel.  
  
> [!CAUTION]
>  Beim Veröffentlichen von Metadaten für einen Dienst, der zwei unterschiedliche Dienstverträge verfügbar macht, in denen jeweils eine Operation mit dem gleichen Namen enthalten ist, wird eine Ausnahme ausgelöst. Beispiel: Wenn ein Dienst einen Dienstvertrag namens "ICarService" mit einer Get(Car c)-Operation verfügbar macht und der gleiche Dienst einen Dienstvertrag namens "IBookService" mit einer Get(Book b)-Operation verfügbar macht, wird beim Erstellen der Metadaten für den Dienst eine Ausnahme ausgelöst oder eine Fehlermeldung angezeigt. Verwenden Sie eine der folgenden Vorgehensweisen, um dieses Problem zu umgehen:  
>   
>  -   Benennen Sie eine der Operationen um.  
> -   Legen Sie die <xref:System.ServiceModel.OperationContractAttribute.Name%2A>-Eigenschaft auf einen anderen Namen fest.  
> -   Legen Sie einen der Namespaces der Operation mit der <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft auf einen anderen Namespace fest.  
  
## <a name="retrieving-service-metadata"></a>Abrufen der Dienstmetadaten  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann Dienstmetadaten mithilfe standardisierter Protokolle, wie z. B. WS-MetadataExchange- und HTTP, abrufen. Beide Protokolle werden vom <xref:System.ServiceModel.Description.MetadataExchangeClient>-Typ unterstützt. Sie rufen Dienstmetadaten mit dem <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>-Typ ab, indem Sie eine Adresse und eine optionale Bindung angeben. Bei der von einer <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>-Instanz verwendeten Bindung kann es sich um eine der Standardbindungen aus der statischen <xref:System.ServiceModel.Description.MetadataExchangeBindings>-Klasse, eine vom Benutzer angegebene Bindung oder eine aus einer Endpunktkonfiguration für den `IMetadataExchange`-Vertrag geladene Bindung handeln. Der <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> kann auch HTTP-URL-Verweise auf Metadaten mit dem <xref:System.Net.HttpWebRequest>-Typ auflösen.  
  
 Standardmäßig wird eine <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>-Instanz an eine einzelne <xref:System.ServiceModel.Channels.ChannelFactoryBase>-Instanz gebunden. Sie können die <xref:System.ServiceModel.Channels.ChannelFactoryBase>-Instanz, die von einem <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> verwendet wird, durch Überschreiben der virtuellen <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>-Methode ändern oder ersetzen. Ebenso können Sie die <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>-Instanz, die von einem <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> zur Erstellung von HTTP/GET-Anforderungen verwendet wird, durch Überschreiben der virtuellen <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=nameWithType>-Methode ändern oder ersetzen.  
  
 Sie können Dienstmetadaten mithilfe von WS-MetadataExchange oder HTTP/GET-Anforderungen durch das Tool Svcutil.exe verwenden, und übergeben Abrufen der **/target:metadata** Switch- und eine Adresse. Svcutil.exe lädt die Metadaten von der angegebenen Adresse herunter und speichert die Dateien auf dem Datenträger. Svcutil.exe verwendet intern eine <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>-Instanz und lädt die MEX-Endpunktkonfiguration, deren Name mit dem Schema der an Svcutil.exe als Eingabe weitergegebenen Adresse übereinstimmt, aus der Anwendungskonfigurationsdatei, sofern vorhanden. Andernfalls verwendet Svcutil.exe standardmäßig eine der Bindungen, die durch den statischen <xref:System.ServiceModel.Description.MetadataExchangeBindings>-Factorytyp definiert werden.  
  
## <a name="importing-service-metadata"></a>Importieren von Dienstmetadaten  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wird beim Importieren von Metadaten eine abstrakte Darstellung eines Diensts oder seiner Komponenten aus dessen Metadaten generiert. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann beispielsweise Instanzen von <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Channels.Binding> oder <xref:System.ServiceModel.Description.ContractDescription> aus einem WSDL-Dokument für einen Dienst importieren. Mit einer Implementierung der abstrakten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Klasse können Sie Metadaten von Diensten in <xref:System.ServiceModel.Description.MetadataImporter> importieren. Die Unterstützung für das Importieren von Metadatenformaten, die die Importlogik der WS-Richtlinie in <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> unterstützen, wird durch Typen implementiert, die von der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Klasse abgeleitet sind.  
  
 Eine <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType>-Implementierung sammelt die an die Dienstmetadaten angefügten Richtlinienausdrücke in einem <xref:System.ServiceModel.Description.PolicyConversionContext>-Objekt. Der <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> verarbeitet die Richtlinien dann im Rahmen des Importvorgangs, indem er die Implementierungen der <xref:System.ServiceModel.Description.IPolicyImportExtension>-Schnittstelle in der <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>-Eigenschaft aufruft.  
  
 Sie können einen <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> um Unterstützung für den Import neuer Richtlinienassertionen erweitern, indem Sie Ihre eigene Implementierung der <xref:System.ServiceModel.Description.IPolicyImportExtension>-Schnittstelle der <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>-Auflistung in einer <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType>-Instanz hinzufügen. Sie können stattdessen die Richtlinienimporterweiterung auch in der Konfigurationsdatei der Clientanwendung registrieren.  
  
 Der <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>-Typ stellt die Implementierung der abstrakten <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType>-Klasse in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dar. Der <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>-Typ importiert WSDL-Metadaten mit angefügten Richtlinien, die in einem <xref:System.ServiceModel.Description.MetadataSet>-Objekt zusammengefasst sind.  
  
 Um Unterstützung für das Importieren von WSDL-Erweiterungen hinzuzufügen, implementieren Sie die <xref:System.ServiceModel.Description.IWsdlImportExtension>-Schnittstelle, und fügen Sie diese Implementierung der <xref:System.ServiceModel.Description.WsdlImporter.WsdlImportExtensions%2A>-Eigenschaft der <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>-Instanz hinzu. Der <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> kann auch Implementierungen der <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType>-Schnittstelle laden, die in der Clientkonfigurationsdatei registriert ist.  
  
## <a name="dynamic-bindings"></a>Dynamische Bindungen  
 Sie können die Bindung, die zum Erstellen eines Kanals zu einem Dienstendpunkt verwendet wird, dynamisch aktualisieren, wenn sich die Bindung für den Endpunkt ändert oder wenn Sie einen Kanal zu einem Endpunkt erstellen möchten, der den gleichen Vertrag verwendet, aber über eine andere Bindung verfügt. Sie können mithilfe der statischen <xref:System.ServiceModel.Description.MetadataResolver>-Klasse zur Laufzeit Metadaten für Dienstendpunkte abrufen und importieren, die einen bestimmten Vertrag implementieren. Mit den importierten <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>-Objekten können Sie einen Client oder eine Kanalfactory für den gewünschten Endpunkt erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Description>  
 [Metadatenformate](../../../../docs/framework/wcf/feature-details/metadata-formats.md)  
 [Exportieren und Importieren von Metadaten](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)  
 [Veröffentlichen von Metadaten](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)  
 [Abrufen von Metadaten](../../../../docs/framework/wcf/feature-details/retrieving-metadata.md)  
 [Verwenden von Metadaten](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [Sicherheitsüberlegungen für Metadaten](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)  
 [Erweitern des Metadatensystems](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)
