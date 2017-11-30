---
title: EClrFailure-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrFailure
helpviewer_keywords: EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94358fd0626fa17f1fd6d3c365aff79f89dde467
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="6d5a5-102">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6d5a5-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="6d5a5-103">Beschreibt den Satz von Fehlern, die für die ein Host Richtlinienaktionen festlegen kann.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d5a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d5a5-104">Syntax</span></span>  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a><span data-ttu-id="6d5a5-105">Member</span><span class="sxs-lookup"><span data-stu-id="6d5a5-105">Members</span></span>  
  
|<span data-ttu-id="6d5a5-106">Member</span><span class="sxs-lookup"><span data-stu-id="6d5a5-106">Member</span></span>|<span data-ttu-id="6d5a5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d5a5-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="6d5a5-108">Fehler beim belegen von einer Ressource (z. B. einen Thread, einen Speicherblock oder eine Sperre) in einem unkritische Codebereich.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="6d5a5-109">Fehler beim belegen von einer Ressource (z. B. einen Thread, einen Speicherblock oder eine Sperre) in einem kritischen Codebereich.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="6d5a5-110">Die common Language Runtime (CLR) ist nicht mehr in der Lage, verwalteten Code im Prozess ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="6d5a5-111">Damit Aufrufe hosting-Funktionen die HRESULT-Wert HOST_E_CLRNOTAVAILABLE zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="6d5a5-112">Fehler durch einen Thread hat auf eine Sperre bei der Rückkehr aus einer <xref:System.AppDomain> Objekt.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="6d5a5-113">Der Host kann dieses Fehlers darin, dass einen Thread zum Abbrechen nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="6d5a5-114">Ein Stapelüberlauf aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="6d5a5-115">Es wurde versucht, das Lesen und Schreiben von geschütztem Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="6d5a5-116">Nicht unterstützt, die der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d5a5-116">Not supported in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="6d5a5-117">Ein Code-Vertrags-Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-117">A code contract failure occurred.</span></span> <span data-ttu-id="6d5a5-118">Finden Sie unter [Code Verträge](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="6d5a5-118">See [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d5a5-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d5a5-119">Remarks</span></span>  
 <span data-ttu-id="6d5a5-120">Finden Sie unter der [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) Methode eine Liste der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, die der Host Sie die Richtlinienaktionen fehlerbedingungen angeben können.</span><span class="sxs-lookup"><span data-stu-id="6d5a5-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="6d5a5-121">Weitere Informationen über kritische und nicht kritische Bereiche des Codes finden Sie unter [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="6d5a5-121">For more information about critical and non-critical regions of code, see [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d5a5-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d5a5-122">Requirements</span></span>  
 <span data-ttu-id="6d5a5-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d5a5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d5a5-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6d5a5-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d5a5-125">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="6d5a5-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d5a5-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d5a5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d5a5-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d5a5-127">See Also</span></span>  
 [<span data-ttu-id="6d5a5-128">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d5a5-128">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="6d5a5-129">SetActionOnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="6d5a5-129">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)  
 [<span data-ttu-id="6d5a5-130">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d5a5-130">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="6d5a5-131">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="6d5a5-131">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)