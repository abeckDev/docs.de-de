---
title: '&lt;security&gt; von &lt;netHttpBinding'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cbe36a801565af0d3664e5c827f8ce903be3b5c7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltnethttpbinding"></a>&lt;security&gt; von &lt;netHttpBinding
Definiert die Sicherheitsfunktionen des der [ \<BasicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).  
  
 \<system.ServiceModel>  
\<bindings>  
\<netHttpBinding>  
\<binding>  
\<security>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Modus|Dies ist optional. Gibt den verwendeten Sicherheitstyp an. Die Standardeinstellung ist `None`. Dieses Attribut ist vom Typ <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> --> `System.ServiceModel.NetHttpSecurityMode`.|
  
## <a name="mode-attribute"></a>mode-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Keiner|-Nachrichten werden während der Übertragung nicht gesichert.|  
|Transport|Die Sicherheit wird über HTTPS bereitgestellt. Die SOAP-Nachrichten werden über HTTPS gesichert. Der Dienst wird über das X.509-Zertifikat beim Client authentifiziert. Der Client wird über ClientCredentialType authentifiziert.|  
|Meldung|Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt. Standardmäßig wird der Text verschlüsselt und signiert. Bei dieser Bindung erfordert das System, dass das Serverzertifikat dem Client out-of-band zur Verfügung gestellt wird. Der einzig gültige `ClientCredentialType` für diese Bindung lautet `Certificate`.|  
|TransportWithMessageCredential|Integrität, Vertraulichkeit und Serverauthentifizierung werden über die Transportsicherheit bereitgestellt. Die Clientauthentifizierung wird über die SOAP-Nachrichtensicherheit bereitgestellt. Dieser Modus ist relevant, wenn sich der Benutzer mit Benutzername/Kennwort authentifiziert und eine vorhandene HTTP-Bereitstellung für die Absicherung der Nachrichtenübertragung vorhanden ist.|  
|TransportCredentialOnly|Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit. Er bietet dagegen HTTP-basierte Clientauthentifizierung. Dieser Modus sollte mit Vorsicht angewendet werden. Er ist nur für Umgebungen geeignet, in denen die Transportsicherheit mit anderen Mitteln sichergestellt wird (z.&#160;B. durch IPSec) und nur die Clientauthentifizierung über die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Infrastruktur bereitgestellt wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nethttpbinding.md)|Definiert die Transportsicherheitseinstellungen für einen Standard-HTTP-Dienst. Dieses Element entspricht <xref:System.ServiceModel.HttpTransportSecurity>.|  
|[\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-nethttpbinding.md)|Definiert die Nachrichtensicherheitseinstellungen für einen Standard-HTTP-Dienst. Dieses Element entspricht <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Bindung|Das Bindungselement, das von der [ \<BasicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig wird die SOAP-Nachricht nicht geschützt, und der Client wird nicht authentifiziert. Dieses Element ermöglicht es Ihnen, zusätzliche Sicherheitseinstellungen für das `netHttpBinding`-Element zu konfigurieren.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.NetHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>    
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Ausählen eines Anmeldeinformationentyps](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
