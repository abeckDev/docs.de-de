---
title: 'Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c5ef33be9841b5c74b6ae2448daf56079489b61
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a>Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung
Mit visueller Vererbung können Sie die Steuerelemente auf dem Basisformular anzeigen und neue Steuerelemente hinzufügen. In dieser exemplarischen Vorgehensweise erstellen Sie ein Basisformular und kompilieren es in eine Klassenbibliothek. Sie importieren diese Klassenbibliothek in ein anderes Projekt und erstellen ein neues Formular, das vom Basisformular erbt. Bei dieser exemplarischen Vorgehensweise lernen Sie Folgendes:  
  
-   Erstellen eines Klassenbibliotheksprojekts, das ein Basisformular enthält.  
  
-   Hinzufügen einer Schaltfläche mit Eigenschaften, die abgeleitete Klassen des Basisformulars ändern können.  
  
-   Hinzufügen einer Schaltfläche, die von Erben des Basisformulars nicht geändert werden kann.  
  
-   Erstellen eines Projekts, das ein Formular enthält, das von `BaseForm` erbt.  
  
 Schließlich wird in dieser exemplarischen Vorgehensweise der Unterschied zwischen privaten und geschützten Steuerelementen in einem geerbten Formular gezeigt.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
> [!CAUTION]
>  Nicht alle Steuerelemente unterstützen visuelle Vererbung von einem Basisformular. Die folgenden Steuerelemente unterstützen das in dieser exemplarischen Vorgehensweise beschriebene Szenario nicht:  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  Diese Steuerelemente im geerbten Formular sind immer schreibgeschützt, unabhängig von den verwendeten Modifizierern (`private`, `protected` oder `public`).  
  
## <a name="scenario-steps"></a>Szenarioschritte  
 Der erste Schritt ist das Erstellen des Basisformulars.  
  
#### <a name="to-create-a-class-library-project-containing-a-base-form"></a>So erstellen Sie ein Klassenbibliotheksprojekt, das ein Basisformular enthält  
  
1.  Aus der **Datei** im Menü Wählen Sie **neu**, und klicken Sie dann **Projekt** So öffnen die **neues Projekt** (Dialogfeld).  
  
2.  Erstellen Sie eine Windows Forms-Anwendung mit dem Namen `BaseFormLibrary`.  
  
3.  So erstellen Sie eine Klassenbibliothek anstelle einer standardmäßigen Windows Forms-Anwendung in **Projektmappen-Explorer**, mit der rechten Maustaste die **BaseFormLibrary** Projektknoten, und wählen Sie dann **Eigenschaften**.  
  
4.  Ändern Sie in den Eigenschaften für das Projekt, das **Ausgabetyp** aus **Windows-Anwendung** auf **-Klassenbibliothek**.  
  
5.  Aus der **Datei** Menü wählen **alle speichern** um das Projekt und die Dateien am Standardspeicherort zu speichern.  
  
 Mit den nächsten zwei Verfahren werden dem Basisformular Schaltflächen hinzugefügt. Zur Demonstration der visuellen Vererbung weisen Sie den Schaltflächen verschiedene Zugriffsebenen zu, indem Sie ihre `Modifiers`Eigenschaften festlegen.  
  
#### <a name="to-add-a-button-that-inheritors-of-the-base-form-can-modify"></a>So fügen Sie eine Schaltfläche hinzu, die von Erben des Basisformulars geändert werden kann  
  
1.  Open **Form1** im Designer.  
  
2.  Auf der **alle Windows Forms** auf der Registerkarte die **Toolbox**, doppelklicken Sie auf **Schaltfläche** auf dem Formular eine Schaltfläche hinzuzufügen. Verwenden Sie die Maus, um die Position und Größe der Schaltfläche anzupassen.  
  
3.  Legen Sie im "Eigenschaftenfenster" die folgenden Eigenschaften der Schaltfläche fest:  
  
    -   Legen Sie die **Text** Eigenschaft **Say Hello**.  
  
    -   Legen Sie die **(Name)** Eigenschaft **BtnProtected**.  
  
    -   Legen Sie die**Modifizierer** Eigenschaft **geschützte**. Dies ermöglicht es, die von erben Forms **Form1** beim Ändern der Eigenschaften von **BtnProtected**.  
  
4.  Doppelklicken Sie auf die **Say Hello** Schaltfläche zum Hinzufügen eines ereignishandlers für das **klicken Sie auf** Ereignis.  
  
5.  Fügen Sie dem Ereignishandler folgende Codezeile hinzu:  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### <a name="to-add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a>So fügen Sie eine Schaltfläche hinzu, die von Erben des Basisformulars nicht geändert werden kann  
  
1.  Wechseln zur Entwurfsansicht durch Klicken auf die **Form1.vb [Entwurf], Form1.cs [Entwurf] oder Form1.jsl [Design]** Registerkarte oben im Code-Editor, oder drücken Sie F7.  
  
2.  Fügen Sie eine zweite Schaltfläche hinzu, und legen Sie deren Eigenschaften wie folgt fest:  
  
    -   Legen Sie die **Text** Eigenschaft **Say Goodbye**.  
  
    -   Legen Sie die **(Name)** Eigenschaft **BtnPrivate**.  
  
    -   Legen Sie die **Modifizierer** Eigenschaft **Private**. Dies macht es unmöglich für Formulare, die von erben **Form1** beim Ändern der Eigenschaften von **BtnPrivate**.  
  
3.  Doppelklicken Sie auf die **Say Goodbye** Schaltfläche zum Hinzufügen eines ereignishandlers für das **klicken Sie auf** Ereignis. Platzieren Sie die folgende Codezeile in der Ereignisprozedur:  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  Aus der **erstellen** Menü Wählen Sie **BaseFormLibrary** um die Klassenbibliothek zu erstellen.  
  
     Nachdem die Bibliothek erstellt wurde, können Sie ein neues Projekt erstellen, das von dem Formular erbt, das Sie gerade erstellt haben.  
  
#### <a name="to-create-a-project-containing-a-form-that-inherits-from-the-base-form"></a>So erstellen Sie ein Projekt, das ein Formular enthält, das vom Basisformular erbt  
  
1.  Aus der **Datei** im Menü Wählen Sie **hinzufügen** und dann **neues Projekt** So öffnen die **neues Projekt hinzufügen** (Dialogfeld).  
  
2.  Erstellen Sie eine Windows Forms-Anwendung mit dem Namen `InheritanceTest`.  
  
#### <a name="to-add-an-inherited-form"></a>So fügen Sie ein geerbtes Formular hinzu  
  
1.  In **Projektmappen-Explorer**, mit der rechten Maustaste die **InheritanceTest** -Projekt, wählen **hinzufügen**, und wählen Sie dann**neues Element**.  
  
2.  In der **neues Element hinzufügen** wählen Sie im Dialogfeld die **Windows Forms** Kategorie (Wenn Sie eine Liste der Kategorien haben) und wählen Sie dann die **geerbtes Formular** Vorlage.  
  
3.  Lassen Sie den Standardnamen des `Form2` , und klicken Sie dann auf **hinzufügen**.  
  
4.  In der **Vererbungsauswahl** wählen Sie im Dialogfeld **Form1** aus der **BaseFormLibrary** Projekt wie das Formular erbt, und klicken Sie auf **OK** .  
  
     Dies erstellt ein Formular in der **InheritanceTest** -Projekt, das das Formular im abgeleitet **BaseFormLibrary**.  
  
5.  Öffnen Sie das geerbte Formular (**Form2**) im Designer, indem Sie darauf doppelklicken, wenn er nicht bereits geöffnet ist.  
  
     Im Designer haben die geerbten Schaltflächen ein Symbol (![von VisualBasicInheritanceSymbol](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "VbInheritanceGlyph")) in der oberen Ecke angezeigt.  
  
6.  Wählen Sie die **Say Hello** Schaltfläche, und beobachten Sie die Ziehpunkte. Da diese Schaltfläche geschützt ist, können die Erben sie verschieben, ihre Größe ändern, ihre Beschriftung ändern und andere Änderungen vornehmen.  
  
7.  Wählen Sie die Private **Say Goodbye** Schaltfläche, und beachten Sie, dass keine Ziehpunkte sind. Darüber hinaus wird in der **Eigenschaften** Fenster die Eigenschaften dieser Schaltfläche werden abgeblendet, um anzugeben, kann nicht geändert werden.  
  
8.  Bei Verwendung von [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]:  
  
    1.  In **Projektmappen-Explorer**, mit der rechten Maustaste **Form1** in der **InheritanceTest** Projekt, und wählen Sie dann **löschen**. Klicken Sie im angezeigten Meldungsfeld auf **OK** zu bestätigen.  
  
    2.  Öffnen Sie die Datei "Program.cs", und ändern Sie die Zeile `Application.Run(new Form1());` in `Application.Run(new Form2());`.  
  
9. In **Projektmappen-Explorer**, mit der rechten Maustaste die **InheritanceTest** Projekt, und wählen Sie **als Startprojekt festlegen**.  
  
10. In **Projektmappen-Explorer**, mit der rechten Maustaste die **InheritanceTest** Projekt, und wählen Sie **Eigenschaften**.  
  
11. In der **InheritanceTest** Eigenschaftenseiten, Festlegen der **Startobjekt** das geerbte Formular sein (**Form2**).  
  
12. Drücken Sie F5, um die Anwendung auszuführen, und beobachten Sie das Verhalten des geerbten Formulars.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Die Vererbung bei Benutzersteuerelementen funktioniert größtenteils auf die gleiche Weise. Öffnen Sie ein neues Klassenbibliotheksprojekt, und fügen Sie ein Benutzersteuerelement hinzu. Platzieren Sie konstituierende Steuerelemente darauf, und kompilieren Sie das Projekt. Öffnen Sie ein weiteres, neues Klassenbibliotheksprojekt, und fügen Sie einen Verweis auf die kompilierte Klassenbibliothek hinzu. Auch versuchen, ein geerbtes Steuerelement hinzufügen (über die **neue Elemente hinzufügen** Dialogfeld) für das Projekt und Verwenden der **Vererbungsauswahl**. Fügen Sie ein Benutzersteuerelement hinzu, und ändern Sie die `Inherits`-Anweisung (`:` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]). Weitere Informationen finden Sie unter [wie: erben von Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erben von Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [Visuelle Vererbung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
