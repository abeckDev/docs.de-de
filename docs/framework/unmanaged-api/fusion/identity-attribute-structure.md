---
title: IDENTITY_ATTRIBUTE-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDENTITY_ATTRIBUTE
api_location: fusion.dll
api_type: COM
f1_keywords: IDENTITY_ATTRIBUTE
helpviewer_keywords: IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3fc4d9f7a95a3283d87f036163592f43e87dd053
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="identityattribute-structure"></a><span data-ttu-id="c76a9-102">IDENTITY_ATTRIBUTE-Struktur</span><span class="sxs-lookup"><span data-stu-id="c76a9-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="c76a9-103">Enthält Informationen über Bildattribute Metadaten über eine [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="c76a9-103">Contains metadata attribute information about an [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c76a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c76a9-104">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="c76a9-105">Member</span><span class="sxs-lookup"><span data-stu-id="c76a9-105">Members</span></span>  
  
|<span data-ttu-id="c76a9-106">Member</span><span class="sxs-lookup"><span data-stu-id="c76a9-106">Member</span></span>|<span data-ttu-id="c76a9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c76a9-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="c76a9-108">Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namespace ist das Attribut.</span><span class="sxs-lookup"><span data-stu-id="c76a9-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="c76a9-109">Ein Zeiger auf eine Null-terminierte Zeichenfolge, die den Namen des Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="c76a9-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="c76a9-110">Ein Zeiger auf eine Null-terminierte Zeichenfolge, die den Wert des Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="c76a9-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c76a9-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c76a9-111">Remarks</span></span>  
 <span data-ttu-id="c76a9-112">Die `IDENTITY_ATTRIBUTE` Struktur enthält drei Zeigern auf Null endende Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="c76a9-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="c76a9-113">Diese drei Zeichenfolgen beschreiben ein Attribut.</span><span class="sxs-lookup"><span data-stu-id="c76a9-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="c76a9-114">Eine Instanz von einem `IDENTITY_ATTRIBUTE` Struktur bezieht sich auf einer Instanz von einer [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="c76a9-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="c76a9-115">Die `IDENTITY_ATTRIBUTE` Struktur enthält die tatsächlichen Zeichenfolgen, und die entsprechende `IDENTITY_ATTRIBUTE_BLOB` Struktur enthält die Offsets, die drei Zeichenfolgen aufgelistet, die der `IDENTITY_ATTRIBUTE` Struktur.</span><span class="sxs-lookup"><span data-stu-id="c76a9-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c76a9-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c76a9-116">Requirements</span></span>  
 <span data-ttu-id="c76a9-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c76a9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c76a9-118">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="c76a9-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c76a9-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c76a9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c76a9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c76a9-120">See Also</span></span>  
 [<span data-ttu-id="c76a9-121">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c76a9-121">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [<span data-ttu-id="c76a9-122">IDENTITY_ATTRIBUTE_BLOB-Struktur</span><span class="sxs-lookup"><span data-stu-id="c76a9-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [<span data-ttu-id="c76a9-123">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="c76a9-123">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)