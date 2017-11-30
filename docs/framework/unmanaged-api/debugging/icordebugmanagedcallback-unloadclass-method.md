---
title: ICorDebugManagedCallback::UnloadClass-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UnloadClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e034f6950cc9d77ef4db350475379aa5c497f7f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="b1ff2-102">ICorDebugManagedCallback::UnloadClass-Methode</span><span class="sxs-lookup"><span data-stu-id="b1ff2-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="b1ff2-103">Benachrichtigt den Debugger, dass eine Klasse entladen wird.</span><span class="sxs-lookup"><span data-stu-id="b1ff2-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1ff2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1ff2-104">Syntax</span></span>  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1ff2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b1ff2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b1ff2-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit der Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="b1ff2-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="b1ff2-107">[in] Ein Zeiger auf ein ICorDebugClass-Objekt, das die Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="b1ff2-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1ff2-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1ff2-108">Remarks</span></span>  
 <span data-ttu-id="b1ff2-109">Die Klasse sollte nach diesem Aufruf nicht verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b1ff2-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1ff2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b1ff2-110">Requirements</span></span>  
 <span data-ttu-id="b1ff2-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1ff2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1ff2-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1ff2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1ff2-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1ff2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1ff2-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1ff2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1ff2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1ff2-115">See Also</span></span>  
 [<span data-ttu-id="b1ff2-116">LoadClass-Methode</span><span class="sxs-lookup"><span data-stu-id="b1ff2-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)  
 [<span data-ttu-id="b1ff2-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1ff2-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)