---
title: "Gewusst wie: Erstellen von ListViewItems mit einem Kontrollkästchen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be87183efd8101233bd5cbda49d556d09802b630
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a>Gewusst wie: Erstellen von ListViewItems mit einem Kontrollkästchen
In diesem Beispiel wird gezeigt, wie eine Spalte des anzuzeigenden <xref:System.Windows.Controls.CheckBox> Steuerelemente in eine <xref:System.Windows.Controls.ListView> -Steuerelements, verwendet eine <xref:System.Windows.Controls.GridView>.  
  
## <a name="example"></a>Beispiel  
 Um eine Spalte zu erstellen, enthält <xref:System.Windows.Controls.CheckBox> Steuerelemente in eine <xref:System.Windows.Controls.ListView>, erstellen eine <xref:System.Windows.DataTemplate> , enthält eine <xref:System.Windows.Controls.CheckBox>. Legen Sie dann die <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> von einer <xref:System.Windows.Controls.GridViewColumn> auf die <xref:System.Windows.DataTemplate>.  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.DataTemplate> , enthält eine <xref:System.Windows.Controls.CheckBox>. Im Beispiel bindet der <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> Eigenschaft von der <xref:System.Windows.Controls.CheckBox> auf die <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> Eigenschaftswert, der die <xref:System.Windows.Controls.ListViewItem> , die Sie enthält. Aus diesem Grund, wenn die <xref:System.Windows.Controls.ListViewItem> , enthält die <xref:System.Windows.Controls.CheckBox> ausgewählt ist, die <xref:System.Windows.Controls.CheckBox> aktiviert ist.  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer Spalte des <xref:System.Windows.Controls.CheckBox> Steuerelemente. Zu der Spalte, die im Beispiel wird die <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> Eigenschaft von der <xref:System.Windows.Controls.GridViewColumn> auf der <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
