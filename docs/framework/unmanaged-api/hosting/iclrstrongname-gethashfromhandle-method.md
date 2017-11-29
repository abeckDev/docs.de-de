---
title: ICLRStrongName::GetHashFromHandle-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01fefe99e82584267b3c0f3e0e528dd798affa15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="c1996-102">ICLRStrongName::GetHashFromHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="c1996-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="c1996-103">Generiert einen Hash des Inhalts der Datei, die das angegebene Dateihandle mithilfe des angegebenen Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="c1996-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1996-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1996-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1996-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c1996-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="c1996-106">[in] Das Handle der Datei, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c1996-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="c1996-107">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="c1996-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="c1996-108">Verwenden Sie 0 (null) für den Standardalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="c1996-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="c1996-109">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="c1996-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="c1996-110">[in] Die angeforderte maximale Größe der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="c1996-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="c1996-111">[out] Die Größe in Bytes, der zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="c1996-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1996-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c1996-112">Return Value</span></span>  
 <span data-ttu-id="c1996-113">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="c1996-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1996-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c1996-114">Requirements</span></span>  
 <span data-ttu-id="c1996-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1996-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1996-116">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c1996-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c1996-117">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c1996-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1996-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1996-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1996-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1996-119">See Also</span></span>  
 [<span data-ttu-id="c1996-120">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1996-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)