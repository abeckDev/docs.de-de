---
title: Dokumentieren von Code mit XML (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ddb1f366002c4f0c675c591d83aab1b31ef8f602
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>Dokumentieren von Code mit XML (Visual Basic)
In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], dokumentieren Sie den Code mit XML  
  
## <a name="xml-documentation-comments"></a>XML-Dokumentationskommentare  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]bietet eine einfache Möglichkeit zum automatischen Erstellen von XML-Dokumentation für Projekte. Sie können automatisch generiert ein XML-Skelett für Ihre Typen und Member, und geben Sie dann für jeden Parameter und andere Hinweise Zusammenfassungen, beschreibende-Dokumentation. Die XML-Dokumentation wird automatisch in eine XML-Datei mit dem gleichen Namen wie das Projekt und die Erweiterung ".xml" ausgegeben, mit der entsprechenden Konfiguration. Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
 Die XML-Datei kann verwendet werden oder anderweitige als XML. Diese Datei befindet sich im gleichen Verzeichnis wie die Ausgabe .exe oder .dll-Datei des Projekts.  
  
 XML-Dokumentation beginnt mit `'''`. Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:  
  
-   Die Dokumentation muss wohlgeformtes XML sein. Wenn das XML nicht wohlgeformt ist, wird eine Warnung ausgegeben, und die Dokumentationsdatei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.  
  
-   Entwickler können ihren eigenen Satz von Tags erstellen. Es ist ein empfohlene Satz von Tags (finden Sie in diesem Thema unter "Verwandte Abschnitte"). Einige der empfohlenen Tags haben eine besondere Bedeutung:  
  
    -   Das \<param>-Tag wird verwendet, um Parameter zu beschreiben. Wenn es verwendet wird, überprüft der Compiler, ob der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.  
  
    -   Das `cref`-Attribut kann an jedes Tag angefügt werden, um einen Verweis auf ein Codeelement bereitzustellen. Der Compiler stellt sicher, dass diese Codeelement vorhanden ist. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus. Der Compiler berücksichtigt auch alle `Imports` Anweisungen bei der Suche für einen Typ beschrieben, die der `cref` Attribut.  
  
    -   Die \<Zusammenfassung >-Tag wird verwendet, von IntelliSense im [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] zusätzliche Informationen über einen Typ oder Member angezeigt.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen zum Erstellen einer XML-Datei mit dem Dokumentationskommentare finden Sie unter den folgenden Themen:  
  
-   [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [Verarbeiten der XML-Datei](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [Gewusst wie: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [XML-Tools in Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a>Siehe auch  
 [Entwickeln von Anwendungen mit Visual Basic](../../../visual-basic/developing-apps/index.md)  
 [Visual Basic-Programmierhandbuch](../../../visual-basic/programming-guide/index.md)
