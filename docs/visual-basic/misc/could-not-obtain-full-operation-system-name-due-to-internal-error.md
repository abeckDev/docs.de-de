---
title: "Der Name des vollständigen Betriebssystems konnte aufgrund eines internen Fehlers nicht abgerufen werden."
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6e90de5a2fd0699a449e05b9c32e7450b8bdc991
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>Der Name des vollständigen Betriebssystems konnte aufgrund eines internen Fehlers nicht abgerufen werden.
Der Name des vollständigen Betriebssystems konnte aufgrund eines internen Fehlers nicht abgerufen werden. Dies kann dadurch verursacht werden, dass WMI auf dem aktuellen Computer fehlt.  
  
 Beim Aufrufen der `My.Computer.Info.OSFullName` -Eigenschaft ist ein Fehler aufgetreten. Eine mögliche Ursache für diesen Fehler ist, wenn WMI (Windows-Verwaltungsinstrumentation, Windows Management Instrumentation) auf dem aktuellen Computer nicht installiert ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Fügen Sie rund um den Aufruf der `Try...Catch` -Eigenschaft einen `My.Computer.Info.OSFullName` -Block hinzu.  
  
2.  Weitere Informationen zu WMI und wie Sie sie installieren rufen Sie aus, und suchen Sie nach "Windows Management Instrumentation Core".  
  
## <a name="see-also"></a>Siehe auch  
 [My.Computer.Info.OSFullName](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)  
 [Ausnahmen- und Fehlerbehandlung in Visual Basic](http://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)  
 [Try...Catch...Finally-Anweisung](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
