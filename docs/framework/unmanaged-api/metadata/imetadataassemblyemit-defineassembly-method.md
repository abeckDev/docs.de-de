---
title: IMetaDataAssemblyEmit::DefineAssembly-Methode
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
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 35bc85cdc4380ee112b7095866c05e5d7639200b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>IMetaDataAssemblyEmit::DefineAssembly-Methode
Erstellt eine `Assembly` Struktur, die Metadaten für die angegebene Assembly und gibt das zugeordnete Metadatentoken zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,   
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pbPublicKey`  
 [in] Der öffentliche Schlüssel, der den Herausgeber der Assembly oder NULL angibt, wenn die Assembly keinen starken Namen aufweist.  
  
 `cbPublicKey`  
 [in] Die Größe in Bytes des `pbPublicKey`.  
  
 `uHashAlgId`  
 [in] Der Bezeichner des Hashalgorithmus für die Verschlüsselung von Dateien in der Assembly oder NULL, wenn der SHA-1-Algorithmus angegeben werden.  
  
 `szName`  
 [in] Der lesbare Name der Assembly. Dieser Wert darf 1024 Zeichen nicht überschreiten.  
  
 `pMetaData`  
 [in] Ein Zeiger auf eine ASSEMBLYMETADATA-Instanz, die die Version, Plattform und Gebietsschema für die Assembly enthält.  
  
 `dwAssemblyFlags`  
 [in] Eine Kombination von [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) Werte, die Funktionen der Assembly zu beschreiben.  
  
 `pmda`  
 [out] Ein Zeiger auf das Metadatentoken.  
  
## <a name="remarks"></a>Hinweise  
 Nur ein `Assembly` Metadatenstruktur innerhalb eines Manifests definiert werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
