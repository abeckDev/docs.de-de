---
title: ICeeGen::GetSectionCreate-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetSectionCreate
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2ea9cb20b62e1b1fa8e726ba0c49c5e24202530c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="a941b-102">ICeeGen::GetSectionCreate-Methode</span><span class="sxs-lookup"><span data-stu-id="a941b-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="a941b-103">Wird generiert, und ruft einen Codeabschnitt, der mit dem angegebenen Namen und Flagwerte.</span><span class="sxs-lookup"><span data-stu-id="a941b-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="a941b-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a941b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a941b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a941b-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a941b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a941b-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="a941b-107">[in] Ein Zeiger auf eine Zeichenfolge, die den Namen des zu erstellenden Abschnitts angibt.</span><span class="sxs-lookup"><span data-stu-id="a941b-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="a941b-108">[in] Flags, die Optionen angeben.</span><span class="sxs-lookup"><span data-stu-id="a941b-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="a941b-109">[out] Ein Zeiger auf den neu erstellten Codeabschnitt.</span><span class="sxs-lookup"><span data-stu-id="a941b-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a941b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a941b-110">Remarks</span></span>  
 <span data-ttu-id="a941b-111">Rufen Sie `GetSectionCreate` nur bei besonderen Anforderungen, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a941b-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a941b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a941b-112">Requirements</span></span>  
 <span data-ttu-id="a941b-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a941b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a941b-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a941b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a941b-115">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a941b-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a941b-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a941b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a941b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a941b-117">See Also</span></span>  
 [<span data-ttu-id="a941b-118">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a941b-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)