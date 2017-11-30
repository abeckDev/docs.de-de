---
title: ICorDebugManagedCallback::ControlCTrap-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ControlCTrap
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df6aab0f8f220e53c8aab0d40a8b300d95822068
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="2c60c-102">ICorDebugManagedCallback::ControlCTrap-Methode</span><span class="sxs-lookup"><span data-stu-id="2c60c-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="2c60c-103">Benachrichtigt den Debugger, dass ein STRG + C im Prozess aufgefangen wird, der debuggt wird.</span><span class="sxs-lookup"><span data-stu-id="2c60c-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c60c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c60c-104">Syntax</span></span>  
  
```  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c60c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c60c-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="2c60c-106">[in] Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, in dem die STRG + C abgefangen wird.</span><span class="sxs-lookup"><span data-stu-id="2c60c-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c60c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2c60c-107">Return Value</span></span>  
  
|<span data-ttu-id="2c60c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c60c-108">HRESULT</span></span>|<span data-ttu-id="2c60c-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c60c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c60c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c60c-110">S_OK</span></span>|<span data-ttu-id="2c60c-111">Der Debugger behandelt das Trap STRG + C.</span><span class="sxs-lookup"><span data-stu-id="2c60c-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="2c60c-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2c60c-112">S_FALSE</span></span>|<span data-ttu-id="2c60c-113">Der Debugger behandelt nicht das Trap STRG + C.</span><span class="sxs-lookup"><span data-stu-id="2c60c-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c60c-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c60c-114">Remarks</span></span>  
 <span data-ttu-id="2c60c-115">Für diesen Rückruf werden alle Anwendungsdomänen innerhalb des Prozesses beendet.</span><span class="sxs-lookup"><span data-stu-id="2c60c-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c60c-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c60c-116">Requirements</span></span>  
 <span data-ttu-id="2c60c-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c60c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c60c-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c60c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c60c-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c60c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c60c-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c60c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c60c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c60c-121">See Also</span></span>  
 [<span data-ttu-id="2c60c-122">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c60c-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)