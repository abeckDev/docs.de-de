---
title: ICorDebugRemoteTarget-Schnittstelle
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
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fcfdab2857745dee7c40823ad25592de5dc833ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugremotetarget-interface"></a>ICorDebugRemoteTarget-Schnittstelle
Stellt Methoden bereit, die es Entwicklern ermöglichen, Silverlight-basierte Anwendungen in der Umgebung der Common Language Runtime (CLR) zu debuggen.  
  
## <a name="syntax"></a>Syntax  
  
```  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ICorDebugRemoteTarget::GetHostName-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|Gibt den Hostnamen oder die IP-Adresse eines Remotecomputers zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Debuggen im gemischten Modus (verwalteter und nativer Code) wird unter Windows 95, Windows 98 und Windows Me sowie auf Nicht-x86-Plattformen (z. B. IA-64 und AMD64) nicht unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl  
  
 **Bibliothek:** : CorGuids.lib  
  
 **.NET Framework-Versionen:** 3.5 SP1  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugRemote-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
