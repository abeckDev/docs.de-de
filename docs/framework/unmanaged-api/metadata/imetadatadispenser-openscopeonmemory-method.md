---
title: IMetaDataDispenser::OpenScopeOnMemory-Methode
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
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d206863736387df04157ed752a6269b22a884b9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>IMetaDataDispenser::OpenScopeOnMemory-Methode
Öffnet einen Bereich des Arbeitsspeichers, die vorhandenen Metadaten enthält. Diese Methode öffnet, also einen angegebenen Bereich des Arbeitsspeichers, in denen die vorhandenen Daten als Metadaten behandelt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pData`  
 [in] Ein Zeiger, der die Startadresse des Speicherbereichs angibt.  
  
 `cbData`  
 [in] Die Größe des Arbeitsspeicherbereichs in Bytes.  
  
 `dwOpenFlags`  
 [in] Der Wert der [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) Enumeration zum Öffnen den Modus (Lesen, schreiben und so weiter) angeben.  
  
 `riid`  
 [in] Die IID der Metadatenschnittstelle für die gewünschten zurückgegeben werden sollen; der Aufrufer verwendet die Schnittstelle zum Importieren (Lesen) oder Ausgeben von Metadaten (Schreiben).  
  
 Der Wert des `riid` müssen eine der Schnittstellen "Import" oder "Ausgabe" angeben. Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport auf, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.  
  
 `ppIUnk`  
 [out] Der Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Die in-Memory-Kopie der Metadaten kann abgefragt werden, mithilfe der Methoden aus einer der Schnittstellen "Importieren" oder mit Methoden aus dem der "Ausgabe"-Schnittstellen hinzugefügt.  
  
 Die `OpenScopeOnMemory` Methode ist vergleichbar mit der [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) -Methode, mit dem Unterschied, dass die Metadaten von Interesse sind bereits im Arbeitsspeicher und nicht in einer Datei auf dem Datenträger vorhanden ist.  
  
 Wenn der Zielbereich des Arbeitsspeichers keine common Language Runtime (CLR)-Metadaten enthält die `OpenScopeOnMemory` Methode fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
