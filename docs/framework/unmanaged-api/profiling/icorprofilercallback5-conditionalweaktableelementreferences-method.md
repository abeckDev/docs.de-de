---
title: ICorProfilerCallback5::ConditionalWeakTableElementReferences-Methode
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
- ICorProfilerCallback5.ConditionalWeakTableReferences
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- CondiitonalWeakTableElementReferences
helpviewer_keywords:
- ConditionalWeakTableElementReferences method, ICorProfilerCallback5 interface [.NET Framework profiling]
- ICorProfilerCallback5::ConditionalWeakTableElementReferences method [.NET Framework profiling]
ms.assetid: 532c7a02-a9de-4cea-bb2b-7f470da594de
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8cfe86ac7d0cd5b4a5c6adb9f12ffe9577b6e611
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a>ICorProfilerCallback5::ConditionalWeakTableElementReferences-Methode
Identifiziert den transitiven Abschluss von Objekten, auf die durch diese Stammelemente verwiesen wird, sowohl über direkte Memberfeldverweise, als auch `ConditionalWeakTable`-Abhängigkeiten.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ConditionalWeakTableElementReferences(     [in]                     ULONG    cRootRefs,     [in, size_is(cRootRefs)] ObjectID keyRefIds[],     [in, size_is(cRootRefs)] ObjectID valueRefIds[],     [in, size_is(cRootRefs)] GCHandleID rootIds[]);};  
```  
  
#### <a name="parameters"></a>Parameter  
 `cRootRefs`  
 [in] Die Anzahl der Elemente in `keyRefIds`-, in `valueRefIds`- und `rootIds`-Arrays.  
  
 `keyRefIds`  
 [in] Ein Array von Objekt-IDs, von denen jede die `ObjectID` für das primäre Element im abhängigen Handlepaar enthält.  
  
 `valueRefIds`  
 [in] Ein Array von Objekt-IDs, von denen jede die `ObjectID` für das sekundäre Element im abhängigen Handlepaar enthält. (`keyRefIds[i]` hält `valueRefIds[i]` aktiv.)  
  
 `rootIds`  
 [in] Ein Array von `GCHandleID`-Werten, die auf eine ganze Zahl zeigen, die zusätzliche Informationen über den Garbage Collection-Stamm enthält.  
  
 Keine `ObjectID`-Werte, die von der `ConditionalWeakTableElementReferences`-Methode zurückgegeben werden, sind während des Rückrufs selbst gültig, da der Garbage Collector möglicherweise gerade Objekten von alten an neue Speicherorte verschiebt. Deshalb sollten Profiler nicht versuchen, Objekte während eines `ConditionalWeakTableElementReferences`-Aufrufs zu überprüfen. Bei `GarbageCollectionFinished` wurden alle Objekte zu den neuen Speicherorten verschoben, und die Überprüfung kann ausgeführt werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie implementieren [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) und verwenden Sie diese Methode.  
  
```  
HRESULT Callback5Impl::ConditionalWeakTableElementReferences(  
    ULONG      cRootRefs,  
    ObjectID   keyRefIds[],  
    ObjectID   valueRefIds[],  
    GCHandleID rootIds[])  
{  
    printf("Callback5Impl::ConditionalWeakTableElementReferences called\n");  
    for (unsigned int i = 0; i < cRootRefs; ++i)  
    {  
        // Save dependency to XML for later retrieval  
        PersistDependencyToXml(rootIds[i], keyRefIds[i], valueRefIds[i]);  
        // or store dependency to an internal map  
        m_cwt_deps->add_dep(rootIds[i], keyRefIds[i], valueRefIds[i]);  
        // or add arc to object graph  
        m_obj_graph->add_arc(keyRefIds[i], valueRefIds[i], rootIds[i]);  
    }  
    return S_OK;  
}  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein Profiler für die [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] oder höhere Versionen implementiert die [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) -Schnittstelle und zeichnet die Abhängigkeiten, die gemäß der `ConditionalWeakTableElementReferences` Methode. `ICorProfilerCallback5`Stellt den vollständigen Satz von Abhängigkeiten zwischen als live-Objekte dargestellt werden, indem `ConditionalWeakTable` Einträge. Diese Abhängigkeiten und die memberfeldverweise gemäß der [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) Methode ermöglichen einen verwalteten Profiler, die das vollständige Objektdiagramm von aktiven Objekten zu generieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback5-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)
