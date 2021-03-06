---
title: PNRP-Clouds
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a82e2bf1-62ab-4c2d-83f3-3217a6aead2e
caps.latest.revision: "4"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f142c7aaa71ab2dbee1d2955f2c235a65e6c8bfa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="pnrp-clouds"></a>PNRP-Clouds
Eine PNRP-Cloud stellt eine Gruppe von Knoten dar, die über das Netzwerk miteinander kommunizieren können. Der Begriff „Cloud“ wird synonym mit „Peermesh“ und „Peer-to-Peer-Diagramm“ verwendet.  
  
 Die Kommunikation zwischen den Knoten sollte die Grenze einer Cloud nie überschreiten. Eine <xref:System.Net.PeerToPeer.Cloud>-Instanz wird durch ihren Namen eindeutig bestimmt. Dabei muss Groß- und Kleinschreibung beachtet werden. Ein einzelner Peer oder Knoten kann mit mehr als einer Cloud verbunden sein.  
  
 Clouds sind sehr eng an Netzwerkschnittstellen gebunden.  Auf einem mehrfach vernetzten Computer mit zwei Netzwerkkarten, die mit unterschiedlichen Subnetzen verbunden sind, werden drei Clouds zurückgegeben: eine für jede lokale Linkadresse pro Schnittstelle und eine einzelne Cloud mit globalem Gültigkeitsbereich.  
  
 PNRP verwendet drei Cloudbereiche, wobei diese Bereiche eine Gruppe von Computern darstellen, die sich gegenseitig finden können:  
  
-   Die globale Cloud entspricht dem globalen IPv6-Adressbereich sowie globalen Adressen. Sie stellt alle Computer des gesamten IPv6-Internets dar. Es gibt nur eine einzige globale Cloud.  
  
-   Die verbindungslokale Cloud entspricht dem verbindungslokalen IPv6-Adressbereich sowie verbindungslokalen Adressen. Eine verbindungslokale Cloud gilt für einen bestimmten Link, der in der Regel mit dem lokal verbundenen Subnetz identisch ist. Es können mehrere verbindungslokale Clouds vorhanden sein.  
  
 Eine dritte Möglichkeit ist die standortspezifische Cloud, die dem standortspezifischen IPv6-Adressbereich sowie standortlokalen Adressen entspricht. Diese Cloud ist veraltet, wird jedoch weiterhin in PNRP unterstützt.  
  
## <a name="clouds"></a>Clouds  
 PNRP-Clouds werden durch Instanzen der <xref:System.Net.PeerToPeer.Cloud>-Klasse dargestellt. Gruppen von Clouds, die einen Peer verwenden, werden durch Instanzen der Enumerable-Klasse <xref:System.Net.PeerToPeer.CloudCollection> dargestellt. Sammlungen von PNRP-Clouds, die dem aktuellen Peer bekannt sind, können durch Aufrufen der statischen <xref:System.Net.PeerToPeer.Cloud.GetAvailableClouds%2A>-Methode abgerufen werden.  
  
 Die einzelnen Clouds verfügen über eindeutige Namen, die als Unicode-Zeichenfolge mit 256 Zeichen dargestellt werden. Diese Namen werden zusammen mit dem oben genannten Gültigkeitsbereich zum Erstellen von eindeutigen Instanzen der Cloudklasse verwendet. Diese Instanzen können serialisiert und zur dauerhaften Verwendung rekonstruiert werden.  
  
 Nachdem eine Cloudinstanz erstellt oder abgerufen wurde, können Peernamen darin registriert werden, um ein Netz aus bekannten Peers zu erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.PeerToPeer.Cloud>  
 [Peer Name Resolution-Protokoll (PNRP)](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)
