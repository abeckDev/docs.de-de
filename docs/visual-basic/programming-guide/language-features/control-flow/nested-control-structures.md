---
title: Geschachtelte Steuerungsstrukturen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22adf4086cd494202a540b2ec16310072329b6ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="nested-control-structures-visual-basic"></a>Geschachtelte Steuerungsstrukturen (Visual Basic)
Sie fügen die Steueranweisungen in andere Steueranweisungen, z. B. ein `If...Then...Else` -Block in einem `For...Next` Schleife. Eine steuerungsanweisung, die innerhalb einer anderen Steueranweisung platziert gilt als *geschachtelte*.  
  
## <a name="nesting-levels"></a>Schachteln von Ebenen  
 Steuerungsstrukturen in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] können geschachtelt sein, um wie viele Ebenen wie gewünscht. Es ist üblich, geschachtelte Strukturen durch Festlegen von Einzügen für den Text jeder einzelnen besser lesbar zu machen. Die integrierte Entwicklungsumgebung (IDE)-Umgebung-Editor geschieht automatisch.  
  
 Im folgenden Beispiel wird die Prozedur `sumRows` addiert die positiven Elemente der einzelnen Zeilen der Matrix.  
  
```  
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 Im vorherigen Beispiel das erste `Next` Anweisung schließt die innere `For` Schleife und der letzte `Next` Anweisung schließt die äußere `For` Schleife.  
  
 Ebenso in geschachtelten `If` -Anweisungen, die `End If` Anweisungen gelten automatisch auf die nächste vor `If` Anweisung. Geschachtelte `Do` -Schleifen funktionieren ähnlich, mit der innersten `Loop` Anweisung entsprechen die innerste `Do` Anweisung.  
  
> [!NOTE]
>  Für viele Steuerungsstrukturen werden, wenn Sie ein Schlüsselwort, klicken Sie auf alle Schlüsselwörter in der Struktur hervorgehoben. Z. B. beim Klicken auf `If` in einer `If...Then...Else` Konstruktion, die alle Instanzen von `If`, `Then`, `ElseIf`, `Else`, und `End If` bei der Erstellung werden hervorgehoben. Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu verschieben, drücken Sie STRG + UMSCHALT + nach-oben-Taste oder STRG + UMSCHALT + nach-oben-Taste.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Verschiedene Arten von Steuerungsstrukturen schachteln  
 Sie können eine Art von Steuerelement-Struktur in eine andere Art schachteln. Im folgenden Beispiel wird eine `With` -Block ein `For Each` -Schleife und geschachtelte `If` blockiert innerhalb der `With` Block.  
  
```  
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a>Überlappende Steuerungsstrukturen  
 Steuerungsstrukturen sich nicht überschneiden. Dies bedeutet, dass alle geschachtelten Strukturen vollständig innerhalb der nächsten innersten Struktur enthalten sein muss. Die folgende Anordnung ist beispielsweise ungültig da die `For` -Schleife wird beendet, bevor Sie die innere `With` Block beendet wird.  
  
 ![Grafisches Diagramm einer ungültigen Schachtelung](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")  
Ungültige Schachtelung von für und mit Strukturen  
  
 Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler erkennt solche überlappenden Steuerungsstrukturen und signalisiert einen Fehler während der Kompilierung.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Entscheidungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Weitere Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
