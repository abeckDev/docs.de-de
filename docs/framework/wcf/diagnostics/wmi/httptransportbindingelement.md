---
title: HttpTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b6370284dbd9c680b29f315c791ea76356e7b36f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="httptransportbindingelement"></a>HttpTransportBindingElement
HttpTransportBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```  
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die HttpTransportBindingElement-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die HttpTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="allowcookies"></a>AllowCookies  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob der Client Cookies akzeptiert und bei zukünftigen Anfragen weiterleitet.  
  
### <a name="authenticationscheme"></a>Authentifizierungsschemas  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Authentifizierungsschema, das zum Authentifizieren von Clientanforderungen verwendet wird, die von einem HTTP-Listener verarbeitet werden.  
  
### <a name="bypassproxyonlocal"></a>BypassProxyOnLocal  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob Proxys für lokale Adressen ignoriert werden.  
  
### <a name="hostnamecomparisonmode"></a>HostNameComparisonMode  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob der Hostname zum Erreichen des Dienstes bei übereinstimmendem URI verwendet wird.  
  
### <a name="keepaliveenabled"></a>KeepAliveEnabled  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Bei Aktivierung werden HTTP-Verbindungen unabhängig von der Aktivitätsebene beibehalten.  
  
### <a name="maxbuffersize"></a>MaxBufferSize  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Größe des Pufferpools.  
  
### <a name="proxyaddress"></a>ProxyAddress  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein URI, der die Adresse des Proxys enthält, der für HTTP-Anforderungen verwendet werden soll.  
  
### <a name="proxyauthenticationscheme"></a>ProxyAuthenticationScheme  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Authentifizierungsschema, das zum Authentifizieren von Clientanforderungen verwendet wird, die von einem HTTP-Proxy verarbeitet werden.  
  
### <a name="realm"></a>Bereich  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Authentifizierungsbereich.  
  
### <a name="transfermode"></a>TransferMode  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob Meldungen bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.  
  
### <a name="unsafeconnectionntlmauthentication"></a>UnsafeConnectionNtlmAuthentication  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob die Freigabe nicht sicherer Verbindungen auf dem Server aktiviert ist.  
  
### <a name="usedefaultwebproxy"></a>UseDefaultWebProxy  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob die Proxyeinstellungen auf dem Computer anstatt der benutzerspezifischen Einstellungen verwendet werden sollen.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
