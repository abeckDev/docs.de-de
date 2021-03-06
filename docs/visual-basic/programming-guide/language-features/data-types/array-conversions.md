---
title: Arraykonvertierungen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 40dc9805157dd0bc991ca2375c3436aa6b6e09a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="array-conversions-visual-basic"></a>Arraykonvertierungen (Visual Basic)
Sie können einen Arraytyp in einen anderen Arraytyp konvertieren, falls Sie die folgenden Bedingungen erfüllen:  
  
-   **Gleich Rang.** Der Rang der beiden Arrays müssen identisch sein, also verfügen, müssen die gleiche Anzahl von Dimensionen. Die Länge der jeweiligen Dimensionen müssen jedoch nicht identisch sein.  
  
-   **Datentyp des Elements.** Die Datentypen der Elemente beider Arrays, müssen es sich um Verweistypen sein. Sie können nicht konvertiert ein `Integer` array an eine `Long` array oder sogar ein `Object` array, da mindestens ein Werttyp ist. Weitere Informationen finden Sie unter [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
-   **Konvertibilität.** Eine Konvertierung, erweiternd oder einschränkend, muss zwischen den Elementtypen der beiden Arrays möglich sein. Ein Beispiel, das diese Anforderung ein Fehler auftritt, wird eine versuchte Konvertierung zwischen einem `String` und Array einer Klasse abgeleitet <xref:System.Attribute?displayProperty=nameWithType>. Diese beiden Typen haben nichts gemeinsam, und keine Konvertierung jeglicher Art, die zwischen ihnen vorhanden ist.  
  
 Eine Konvertierung von einem Arraytyp ist erweiternde oder einschränkende je nach gibt an, ob die Konvertierung der entsprechenden Elemente erweiternde oder einschränkende ist. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Die Konvertierung in einem Objektarray  
 Beim Deklarieren einer `Object` Array ohne initialisieren, dessen Elementtyp ist `Object` solange er nicht initialisiert ist. Wenn Sie es auf ein Array von einer bestimmten Klasse festlegen, dauert es für den Typ dieser Klasse. Der zugrunde liegende Typ ist jedoch weiterhin `Object`, und Sie können Sie später in ein anderes Array einer unabhängigen Klasse festlegen. Da von allen Klassen abgeleitet werden `Object`, Sie können der Arrayelementtyp beliebiger Klassen in jeder anderen Klasse ändern.  
  
 Im folgenden Beispiel keine Konvertierungen zwischen Typen `student` und `String`, aber beide abgeleitet `Object`, sodass alle Zuweisungen gültig sind.  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a>Zugrunde liegender Typ eines Arrays  
 Wenn Sie ursprünglich ein Array mit einer bestimmten Klasse deklarieren, wird dessen zugrunde liegendem Elementtyp dieser Klasse. Wenn Sie anschließend auf ein Array von einer anderen Klasse festlegen, muss eine Konvertierung zwischen den beiden Klassen sein.  
  
 Im folgenden Beispiel `students` ist ein `student` Array. Da keine zwischen Konvertierungen `String` und `student`, die letzte Anweisung schlägt fehl.  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Konvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
