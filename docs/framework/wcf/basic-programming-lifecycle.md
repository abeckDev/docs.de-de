---
title: Grundlegender Programmierlebenszyklus
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
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4f5c45cad0b1e4ae1aa6b1963e9acdab47cd9203
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="basic-programming-lifecycle"></a>Grundlegender Programmierlebenszyklus
Mit [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] können Anwendungen miteinander zu kommunizieren, unabhängig davon, ob sie sich auf demselben Computer, im Internet oder auf verschiedenen Anwendungsplattformen befinden. In diesem Thema werden die Aufgaben beschrieben, die zum Erstellen einer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Anwendung erforderlich sind. Eine funktionierende beispielanwendung finden Sie unter [Lernprogramm für erste Schritte](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
## <a name="the-basic-tasks"></a>Grundlegende Aufgaben  
 Die folgenden grundlegenden Aufgaben müssen in der angegebenen Reihenfolge ausgeführt werden:  
  
1.  Definieren Sie den Dienstvertrag. Ein Dienstvertrag gibt die Signatur eines Diensts, die Daten, die ausgetauscht werden, sowie andere vertraglich erforderliche Daten an. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Entwerfen von Dienstverträgen](../../../docs/framework/wcf/designing-service-contracts.md).  
  
2.  Implementieren Sie den Vertrag. Zum Implementieren eines Dienstvertrags erstellen Sie eine Klasse, die den Vertrag implementiert, und geben Sie das benutzerdefinierte Verhalten der Laufzeit an. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Implementieren von Dienstverträgen](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
3.  Konfigurieren Sie den Dienst, indem Sie Endpunkte und andere Verhaltensinformationen angeben. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Konfigurieren von Diensten](../../../docs/framework/wcf/configuring-services.md).  
  
4.  Hosten Sie den Dienst. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Hostingdienste](../../../docs/framework/wcf/hosting-services.md).  
  
5.  Erstellen Sie eine Clientanwendung. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Erstellen Clients](../../../docs/framework/wcf/building-clients.md).  
  
 Obwohl die Themen in diesem Abschnitt dieser Reihenfolge entsprechen, beginnen einige Szenarien nicht am Anfang. Wenn Sie beispielsweise einen Client für einen bereits vorhandenen Dienst erstellen möchten, beginnen Sie bei Schritt 5. Wenn Sie hingegen einen Dienst erstellen, den andere verwenden, können Sie Schritt 5 überspringen.  
  
 Sobald Sie mit der Entwicklung von Dienstverträgen vertraut sind, können Sie auch eine Lesen [Einführung in die Erweiterbarkeit](../../../docs/framework/wcf/introduction-to-extensibility.md). Wenn Sie Probleme mit Ihrem Dienst haben, überprüfen Sie [Schnelleinstieg zur Problembehandlung in WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) um festzustellen, ob andere Benutzer die gleiche oder ähnliche Probleme haben.  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren von Dienstverträgen](../../../docs/framework/wcf/implementing-service-contracts.md)
