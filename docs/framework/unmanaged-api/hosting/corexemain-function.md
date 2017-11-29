---
title: _CorExeMain-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: _CorExeMain
helpviewer_keywords: _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8c341d578a45d72804d9ac33e2aefe513fd33922
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corexemain-function"></a><span data-ttu-id="565e4-102">_CorExeMain-Funktion</span><span class="sxs-lookup"><span data-stu-id="565e4-102">_CorExeMain Function</span></span>
<span data-ttu-id="565e4-103">Initialisiert die common Language Runtime (CLR), sucht den verwalteten Einstiegspunkt im CLR-Header der ausführbaren Assembly und startet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="565e4-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="565e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="565e4-104">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="565e4-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="565e4-105">Remarks</span></span>  
 <span data-ttu-id="565e4-106">Diese Funktion wird durch das aus verwalteten ausführbaren Assemblys erstellte Prozesse-Ladeprogramm aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="565e4-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="565e4-107">DLL-Assemblys erfordert das Ladeprogramm die [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) stattdessen-Funktion.</span><span class="sxs-lookup"><span data-stu-id="565e4-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="565e4-108">Vom Ladeprogramm des Betriebssystems ruft diese Methode unabhängig von den Einstiegspunkt in der Bilddatei enthaltenen angegeben.</span><span class="sxs-lookup"><span data-stu-id="565e4-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="565e4-109">In Windows 98, Windows ME, Windows NT und Windows 2000 die `_CorExeMain` Funktion indirekt durch einen Fixup im Ladeprogramm Betriebssystems aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="565e4-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="565e4-110">In allen anderen Versionen von Windows wird er direkt vom Ladeprogramm Betriebssystems aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="565e4-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="565e4-111">Weitere Informationen finden Sie im Abschnitt "Hinweise" in der [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="565e4-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="565e4-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="565e4-112">Requirements</span></span>  
 <span data-ttu-id="565e4-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="565e4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="565e4-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="565e4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="565e4-115">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="565e4-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="565e4-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="565e4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="565e4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="565e4-117">See Also</span></span>  
 [<span data-ttu-id="565e4-118">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="565e4-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)