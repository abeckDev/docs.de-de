---
title: ICorProfilerCallback2::SurvivingReferences-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.SurvivingReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::SurvivingReferences
helpviewer_keywords:
- ICorProfilerCallback2::SurvivingReferences method [.NET Framework profiling]
- SurvivingReferences method [.NET Framework profiling]
ms.assetid: f165200e-3a91-47f7-88fc-13ff10c8babc
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3764bfb79b39af897600202e8bc0f2ffbc4da95b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2survivingreferences-method"></a><span data-ttu-id="fca9a-102">ICorProfilerCallback2::SurvivingReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="fca9a-102">ICorProfilerCallback2::SurvivingReferences Method</span></span>
<span data-ttu-id="fca9a-103">Meldet das Layout von Objekten im Heap als Folge einer nicht komprimierenden Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fca9a-103">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fca9a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fca9a-104">Syntax</span></span>  
  
```  
HRESULT SurvivingReferences(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] ULONG  
                cObjectIDRangeLength[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fca9a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fca9a-105">Parameters</span></span>  
 `cSurvivingObjectIDRanges`  
 <span data-ttu-id="fca9a-106">[in] Die Anzahl der Blöcke zusammenhängender Objekte, die als Folge der nicht komprimierenden Garbage Collection beibehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="fca9a-106">[in] The number of blocks of contiguous objects that survived as the result of the non-compacting garbage collection.</span></span> <span data-ttu-id="fca9a-107">Dies bedeutet, dass der Wert von `cSurvivingObjectIDRanges` die Größe der Arrays `objectIDRangeStart` und `cObjectIDRangeLength`, die eine `ObjectID` bzw. eine Länge speichern, für jeden Objektblock darstellt.</span><span class="sxs-lookup"><span data-stu-id="fca9a-107">That is, the value of `cSurvivingObjectIDRanges` is the size of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays, which store an `ObjectID` and a length, respectively, for each block of objects.</span></span>  
  
 <span data-ttu-id="fca9a-108">Die nächsten zwei Argumente von `SurvivingReferences` sind parallele Arrays.</span><span class="sxs-lookup"><span data-stu-id="fca9a-108">The next two arguments of `SurvivingReferences` are parallel arrays.</span></span> <span data-ttu-id="fca9a-109">`objectIDRangeStart` und `cObjectIDRangeLength` betreffen also alle den gleichen Block zusammenhängender Objekte.</span><span class="sxs-lookup"><span data-stu-id="fca9a-109">In other words, `objectIDRangeStart` and `cObjectIDRangeLength` concern the same block of contiguous objects.</span></span>  
  
 `objectIDRangeStart`  
 <span data-ttu-id="fca9a-110">[in] Ein Array von `ObjectID`-Werten, von denen jeder die Startadresse eines Blocks zusammenhängender aktiver Objekte im Arbeitsspeicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="fca9a-110">[in] An array of `ObjectID` values, each of which is the starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="fca9a-111">[in] Ein Array von Ganzzahlen, von denen jede die Größe eines beibehaltenen Blocks zusammenhängender Objekte im Arbeitsspeicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="fca9a-111">[in] An array of integers, each of which is the size of a surviving block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="fca9a-112">Es wird eine Größe für jeden Block angegeben, auf den im `objectIDRangeStart`-Array verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="fca9a-112">A size is specified for each block that is referenced in the `objectIDRangeStart` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fca9a-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fca9a-113">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fca9a-114">Mit dieser Methode werden auf 64-Bit-Plattformen Größen für Objekte, die größer als 4 GB sind, als `MAX_ULONG` gemeldet.</span><span class="sxs-lookup"><span data-stu-id="fca9a-114">This method reports sizes as `MAX_ULONG` for objects that are greater than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="fca9a-115">Für Objekte, die größer als 4 GB sind, verwenden die [icorprofilercallback4:: Survivingreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="fca9a-115">For objects that are larger than 4 GB, use the [ICorProfilerCallback4::SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="fca9a-116">Die Elemente der `objectIDRangeStart`- und `cObjectIDRangeLength`-Arrays sollten wie folgt interpretiert werden, um festzustellen, ob ein Objekt bei der Garbage Collection beibehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="fca9a-116">The elements of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays should be interpreted as follows to determine whether an object survived the garbage collection.</span></span> <span data-ttu-id="fca9a-117">Angenommen, ein `ObjectID`-Wert (`ObjectID`) liegt innerhalb des folgenden Bereichs:</span><span class="sxs-lookup"><span data-stu-id="fca9a-117">Assume that an `ObjectID` value (`ObjectID`) lies within the following range:</span></span>  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="fca9a-118">Für jeden Wert von `i` im folgenden Bereich wurde das Objekt bei der Garbage Collection beibehalten:</span><span class="sxs-lookup"><span data-stu-id="fca9a-118">For any value of `i` that is in the following range, the object has survived the garbage collection:</span></span>  
  
 <span data-ttu-id="fca9a-119">0 <= `i` < `cSurvivingObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="fca9a-119">0 <= `i` < `cSurvivingObjectIDRanges`</span></span>  
  
 <span data-ttu-id="fca9a-120">Eine nicht komprimierende Garbage Collection gibt den von "inaktiven" Objekten belegten Arbeitsspeicher frei, komprimiert diesen freigegebenen Speicherplatz jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="fca9a-120">A non-compacting garbage collection reclaims the memory occupied by "dead" objects, but does not compact that freed space.</span></span> <span data-ttu-id="fca9a-121">Als Ergebnis wird Arbeitsspeicher an den Heap zurückgegeben, es werden jedoch keine "aktiven" Objekte verschoben.</span><span class="sxs-lookup"><span data-stu-id="fca9a-121">As a result, memory is returned to the heap, but no "live" objects are moved.</span></span>  
  
 <span data-ttu-id="fca9a-122">Die CLR (Common Language Runtime) ruft `SurvivingReferences` für nicht komprimierende Garbage Collections auf.</span><span class="sxs-lookup"><span data-stu-id="fca9a-122">The common language runtime (CLR) calls `SurvivingReferences` for non-compacting garbage collections.</span></span> <span data-ttu-id="fca9a-123">Für komprimierende Garbage Collections [ICorProfilerCallback:: MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) stattdessen aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fca9a-123">For compacting garbage collections, [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) is called instead.</span></span> <span data-ttu-id="fca9a-124">Eine einzelne Garbage Collection kann für eine Generation komprimierend und für eine andere nicht komprimierend sein.</span><span class="sxs-lookup"><span data-stu-id="fca9a-124">A single garbage collection can be compacting for one generation and non-compacting for another.</span></span> <span data-ttu-id="fca9a-125">Für eine Garbage Collection einer bestimmten Generation empfängt der Profiler einen `SurvivingReferences`-Rückruf oder einen `MovedReferences`-Rückruf, nicht jedoch beides.</span><span class="sxs-lookup"><span data-stu-id="fca9a-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences` callback or a `MovedReferences` callback, but not both.</span></span>  
  
 <span data-ttu-id="fca9a-126">Es werden ggf. mehrere `SurvivingReferences`-Rückrufe während einer bestimmten Garbage Collection aufgrund der eingeschränkten internen Pufferung, mehrerer Threads, die bei der Garbage Collection des Servers gemeldet werden, oder anderer Gründe empfangen.</span><span class="sxs-lookup"><span data-stu-id="fca9a-126">Multiple `SurvivingReferences` callbacks might be received during a particular garbage collection, due to limited internal buffering, multiple threads reporting in the case of server garbage collection, and other reasons.</span></span> <span data-ttu-id="fca9a-127">Wenn mehrere Rückrufe während einer Garbage Collection erfolgen, sind die Informationen kumulativ. Alle Verweise, die in einen `SurvivingReferences`-Rückruf gemeldet werden, werden bei der Garbage Collection beibehalten.</span><span class="sxs-lookup"><span data-stu-id="fca9a-127">In the case of multiple callbacks during a garbage collection, the information is cumulative — all references that are reported in any `SurvivingReferences` callback survive the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fca9a-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fca9a-128">Requirements</span></span>  
 <span data-ttu-id="fca9a-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fca9a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fca9a-130">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fca9a-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fca9a-131">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fca9a-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fca9a-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fca9a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fca9a-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fca9a-133">See Also</span></span>  
 [<span data-ttu-id="fca9a-134">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fca9a-134">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="fca9a-135">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fca9a-135">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="fca9a-136">SurvivingReferences2-Methode</span><span class="sxs-lookup"><span data-stu-id="fca9a-136">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)