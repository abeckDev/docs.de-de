---
title: CorMethodImpl-Enumeration
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
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e82eb50e4850ffbb4d5fc67d9603a3128cf8bcf6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="cormethodimpl-enumeration"></a>CorMethodImpl-Enumeration
Enthält Werte, die Funktionen zur Implementierung von Methoden beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`miCodeTypeMask`|Flags, die Codetyp beschreiben.|  
|`miIL`|Gibt an, dass die Implementierung der Methode Microsoft intermediate Language (MSIL).|  
|`miNative`|Gibt an, dass die Methodenimplementierung nativ ist.|  
|`miOPTIL`|Gibt an, dass die Implementierung der Methode OPTIL.|  
|`miRuntime`|Gibt an, dass die Implementierung der Methode durch die common Language Runtime bereitgestellt werden.|  
|`miManagedMask`|Flags, die angeben, ob der Code verwaltet oder nicht verwaltet wird.|  
|`miUnmanaged`|Gibt an, dass die Implementierung der Methode nicht verwalteter.|  
|`miManaged`|Gibt an, dass die Implementierung der Methode verwaltet wird.|  
|`miForwardRef`|Gibt an, dass die Methode definiert ist. Dieses Flag wird in erster Linie hinsichtlich der Merge-Szenarien verwendet.|  
|`miPreserveSig`|Gibt an, dass die Methodensignatur für die ein HRESULT-Konvertierung nicht geändert werden kann.|  
|`miInternalCall`|Reserviert für interne Verwendung durch die common Language Runtime.|  
|`miSynchronized`|Gibt an, dass die Methode Singlethread-Methodentext ist.|  
|`miNoInlining`|Gibt an, dass die Methode nicht intern sein kann.|  
|`miAggressiveInlining`|Gibt an, dass die Methode möglichst inline gesetzt werden soll.|  
|`miNoOptimization`|Gibt an, dass die Methode nicht optimiert werden soll.|  
|`miMaxMethodImplVal`|Der gültige Höchstwert für eine `CorMethodImpl`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
