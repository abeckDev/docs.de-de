---
title: "Gewusst wie: Anpassen der Größe des Ziehpunkts auf einer Bildlaufleiste"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e88a7afb9c98179fbcb4a67217edd411d4fe9567
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a>Gewusst wie: Anpassen der Größe des Ziehpunkts auf einer Bildlaufleiste
In diesem Thema wird erläutert, wie festzulegende der <xref:System.Windows.Controls.Primitives.Thumb> des eine <xref:System.Windows.Controls.Primitives.ScrollBar> eine feste Größe und zum Angeben der Mindestgröße für die <xref:System.Windows.Controls.Primitives.Thumb> des eine <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
## <a name="example"></a>Beispiel  
  
## <a name="description"></a>Beschreibung  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.ScrollBar> , besitzt eine <xref:System.Windows.Controls.Primitives.Thumb> mit fester Größe. Im Beispiel wird die <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> Eigenschaft von der <xref:System.Windows.Controls.Primitives.Thumb> auf <xref:System.Double.NaN> und legt die Höhe des der <xref:System.Windows.Controls.Primitives.Thumb>.  Zum Erstellen einer horizontalen <xref:System.Windows.Controls.Primitives.ScrollBar> mit einem <xref:System.Windows.Controls.Primitives.Thumb> , der eine feste Breite hat, legen Sie die Breite der <xref:System.Windows.Controls.Primitives.Thumb>.  
  
## <a name="code"></a>Code  
 [!code-xaml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a>Beschreibung  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.ScrollBar> , besitzt eine <xref:System.Windows.Controls.Primitives.Thumb> mit einer Mindestgröße. Im Beispiel wird den Wert des <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>. Zum Erstellen einer horizontalen <xref:System.Windows.Controls.Primitives.ScrollBar> mit einem <xref:System.Windows.Controls.Primitives.Thumb> , die eine minimale Breite hat, legen Sie die <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.  
  
## <a name="code"></a>Code  
 [!code-xaml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a>Siehe auch  
 [ScrollBar-Stile und -Vorlagen](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)
