---
title: COR_GC_REFERENCE-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a86604febb7641eef147608e564a27883fdc4bec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreference-structure"></a>COR_GC_REFERENCE-Struktur
Enthält Informationen zu einem Objekt, das speicherbereinigt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`domain`|Ein Zeiger auf die Anwendungsdomäne, zu der das Handle oder das Objekt gehört. Der Wert möglicherweise `null`.|  
|`location`|ICorDebugValue oder ein [ICorDebugReferenceValue-Schnittstelle, die das Objekt, das speicherbereinigt werden soll entspricht.|  
|`type`|Ein [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, in dem Stammverzeichnis stammt. Weitere Informationen finden Sie im Abschnitt "Hinweise".|  
|`extraData`|Zusätzliche Daten über das Objekt, das speicherbereinigt werden soll. Diese Informationen hängt von der Quelle des Objekts, die durch die `type` Feld. Weitere Informationen finden Sie im Abschnitt "Hinweise".|  
  
## <a name="remarks"></a>Hinweise  
 Die `type` Feld ist eine [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, in dem der Verweis stammt. Ein bestimmter `COR_GC_REFERENCE` Wert reflektiert die folgenden Arten von verwalteten Objekten:  
  
-   Objekte aus allen verwalteten Stapeln (`CorGCReferenceType.CorReferenceStack`). Dies schließt die aktive Verweise in verwaltetem Code als auch Objekte, die von der common Language Runtime erstellt.  
  
-   Objekte aus der Handletabelle (`CorGCReferenceType.CorHandle*`). Dies schließt starken Verweise (`HNDTYPE_STRONG` und `HNDTYPE_REFCOUNT`) und statische Variablen in einem Modul.  
  
-   Objekte aus der Finalizerwarteschlange (`CorGCReferenceType.CorReferenceFinalizer`). Die Finalizer-Warteschlange Stämme Objekte auf, bis der Finalizer ausgeführt wurde.  
  
 Die `extraData` Feld enthält zusätzliche Daten abhängig von der Quelle (oder Typ) des Verweises. Dabei sind folgende Werte möglich:  
  
-   `DependentSource` Wenn die `type` ist `CorGCREferenceType.CorHandleStrongDependent`, dieses Feld ist das Objekt, das, wenn aktiv, wird das Objekt, um zur Garbage Collection werden Stämme `COR_GC_REFERENCE.Location`.  
  
-   `RefCount` Wenn die `type` ist `CorGCREferenceType.CorHandleStrongRefCount`, dieses Feld wird der Verweiszähler des Handles.  
  
-   `Size` Wenn die `type` ist `CorGCREferenceType.CorHandleStrongSizedByref`, dieses Feld ist die letzte Größe der Objektstruktur für den Garbage Collector die Stämme Objekt berechnet. Beachten Sie, dass diese Berechnung nicht unbedingt auf dem neuesten Stand ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
