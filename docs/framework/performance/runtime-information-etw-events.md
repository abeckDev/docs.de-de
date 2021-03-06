---
title: ETW-Laufzeitinformationsereignisse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime information events [.NET Framework]
- ETW, runtime information events
ms.assetid: 68b4edbc-7f3b-45f6-ab75-4fd066d6af9a
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5262d778151cfe0a0d7ed1750e0b71d4c9214a64
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="runtime-information-etw-events"></a>ETW-Laufzeitinformationsereignisse
Diese ETW-Ereignisse erfassen Informationen über die Laufzeit, einschließlich der SKU, der Versionsnummer, der Art der Aktivierung der Laufzeit, der Befehlszeilenparameter, mit denen sie gestartet wurde, der GUID (wenn zutreffend) und weiterer wichtiger Informationen. Wenn innerhalb eines Prozesses mehrere Laufzeiten ausgeführt werden, helfen Ihnen die von diesen Ereignissen bereitgestellten Informationen dabei, die Laufzeiten eindeutig zu machen.  
  
 Die folgende Tabelle enthält zwei Laufzeitinformationsereignisse. Die Ereignisse können unter jedem Schlüsselwort oder jeder Maske ausgelöst werden. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|event|Ereignis-ID|Anbieter|Beschreibung|  
|-----------|--------------|--------------|-----------------|  
|`RuntimeInformationEvent`|187|CLRRuntime|Wird ausgelöst, wenn eine Laufzeit geladen wird|  
|`RuntimeInformationDCStart`|187|CLRRundown|Zählt die geladenen Laufzeiten auf|  
  
 In der folgenden Tabelle finden Sie die Ereignisdaten.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
|Sku|win:UInt16|1 – Desktop-CLR<br /><br /> 2 – CoreCLR|  
|BclVersion – Major Version|win:UInt16|Hauptversion der mscorlib.dll|  
|BclVersion – Major Version|win:UInt16|Nummer der Nebenversion der mscorlib.dll|  
|BclVersion – Build Number|win:UInt16|Buildnummer der mscorlib.dll|  
|BclVersion – QFE|win:UInt16|Nummer der Hotfixversion der mscorlib.dll|  
|VMVersion – Major Version|win:UInt16|Version der clr.dll oder coreclr.dll, abhängig von der SKU|  
|VMVersion – Minor Version|win:UInt16|Version der clr.dll oder coreclr.dll, abhängig von der SKU|  
|VMVersion – Build Number|win:UInt16|Buildnummer der clr.dll oder coreclr.dll|  
|VMVersion – QFE|win:UInt16|Nummer der Hotfixversion der clr.dll oder coreclr.dll|  
|StartupFlags|win:UInt32|In mscoree.h definierte Startflags|  
|StartupMode|win:UInt8|0x01 – verwaltete ausführbare Datei<br /><br /> 0x02 – gehostete CLR<br /><br /> 0x04 – C++ verwalteter Interop<br /><br /> 0x08 – COM-aktiviert<br /><br /> 0x10 – andere|  
|COMMANDLINE|win:UnicodeString|Nur ungleich NULL, wenn StartupMode = 0x01|  
|ComObjectGUID|win:GUID|Nur ungleich NULL, wenn StartupMode = 0x08|  
|RuntimeDLLPath|win:UnicodeString|Pfad zur CLR-DLL-Datei, die in den Prozess geladen wurde|  
  
## <a name="see-also"></a>Siehe auch  
 [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md)
