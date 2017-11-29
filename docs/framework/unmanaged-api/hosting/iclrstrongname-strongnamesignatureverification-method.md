---
title: ICLRStrongName::StrongNameSignatureVerification-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureVerification
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e326eadcf91fbab0edb81844172bfabbd0851dc7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="a3efa-102">ICLRStrongName::StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="a3efa-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="a3efa-103">Ruft einen Wert, der angibt, ob das Assemblymanifest im angegebenen Pfad eine starke Namenssignatur enthält, die gemäß den angegebenen Flags überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="a3efa-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3efa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3efa-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3efa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3efa-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a3efa-106">[in] Der Pfad zur portable ausführbare (.dll oder .exe)-Datei für die Assembly aus, um zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a3efa-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="a3efa-107">[in] Flags, um das Verhalten für die Überprüfung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a3efa-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="a3efa-108">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="a3efa-108">The following values are supported:</span></span>  
  
-   <span data-ttu-id="a3efa-109">`SN_INFLAG_FORCE_VER`(0 x 00000001) - Überprüfung erzwingt, auch wenn es zum Überschreiben der registrierungseinstellungen für die erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a3efa-109">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="a3efa-110">`SN_INFLAG_INSTALL`(0 x 00000002) – gibt an, dass dies das erste Mal ist das Manifest wird überprüft.</span><span class="sxs-lookup"><span data-stu-id="a3efa-110">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="a3efa-111">`SN_INFLAG_ADMIN_ACCESS`(0 x 00000004) – gibt an, dass der Cache Zugriff nur für Benutzer gewährt wird, die über Administratorrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="a3efa-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="a3efa-112">`SN_INFLAG_USER_ACCESS`(0 x 00000008) – gibt an, dass die Assembly nur auf den aktuellen Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="a3efa-112">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="a3efa-113">`SN_INFLAG_ALL_ACCESS`(0 x 00000010) – gibt an, dass keine Gewährleistung der Einschränkung der Cache bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a3efa-113">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="a3efa-114">`SN_INFLAG_RUNTIME`(0 x 80000000) - reserviert für interne Debuggen.</span><span class="sxs-lookup"><span data-stu-id="a3efa-114">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="a3efa-115">[out] Flags, die angibt, ob die Signatur mit starkem Namen überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="a3efa-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="a3efa-116">Der folgende Wert wird unterstützt:</span><span class="sxs-lookup"><span data-stu-id="a3efa-116">The following value is supported:</span></span>  
  
-   <span data-ttu-id="a3efa-117">`SN_OUTFLAG_WAS_VERIFIED`(0 x 00000001) - dieser Wert wird festgelegt, um `false` um anzugeben, dass die Überprüfung aufgrund der registrierungseinstellungen für die erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="a3efa-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3efa-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a3efa-118">Return Value</span></span>  
 <span data-ttu-id="a3efa-119">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="a3efa-119">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3efa-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3efa-120">Requirements</span></span>  
 <span data-ttu-id="a3efa-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3efa-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3efa-122">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a3efa-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a3efa-123">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a3efa-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3efa-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3efa-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3efa-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3efa-125">See Also</span></span>  
 [<span data-ttu-id="a3efa-126">StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="a3efa-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="a3efa-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3efa-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)