---
title: -Highentropyva (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12d40e5acda73786ee88d16bacd9bc5f69400be8
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-highentropyva-visual-basic"></a>-Highentropyva (Visual Basic)
Gibt an, ob eine ausführbare 64-Bit- oder eine ausführbare Datei, die durch die markiert ist die [/Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) Compileroption unterstützt Adresse Space Layout Randomization (ASLR) mit hohen Entropie.  
  
## <a name="syntax"></a>Syntax  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Dies ist optional. Die Option ist standardmäßig deaktiviert, oder wenn Sie angeben, `-highentropyva-`. Die Option ist bei der Angabe `-highentropyva` oder `-highentropyva+`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie diese Option angeben, können kompatible Versionen der Windows-Kernel je höher der Grad der Entropie verwenden, wenn der Kernel die Adresse Speicherplatz Layout eines Prozesses im Rahmen des ASLR Einzelteilen. Wenn der Kernel je höher der Grad der Entropie verwendet wird, kann eine größere Anzahl von Adressen Speicherbereiche, z. B. Stapel und Heaps zugeordnet werden. Daher ist es schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.  
  
 Wenn die Option auf der ausführbaren Zieldatei und Module aktiviert ist muss, der es abhängt Zeigerwerte verarbeiten, die größer als 4 Gigabyte (GB) sind, wenn diese Module als 64-Bit-Prozesse ausgeführt werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
