---
title: "Übersicht über das TrackBar-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e62fc49a8a08c79138df080246b99b6fe891162e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="trackbar-control-overview-windows-forms"></a>Übersicht über das TrackBar-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.TrackBar> -Steuerelement (manchmal auch "Schiebereglersteuerung" genannt) wird verwendet, zum Navigieren durch eine große Menge an Informationen oder für eine numerische Einstellung visuell anpassen. Die <xref:System.Windows.Forms.TrackBar> Steuerelement besteht aus zwei Teilen: dem Ziehpunkt, auch bekannt als ein Schieberegler, und die Teilstriche. Der Ziehpunkt ist der Teil, das angepasst werden kann. Entspricht die Position der <xref:System.Windows.Forms.TrackBar.Value%2A> Eigenschaft. Die Teilstriche sind visuelle Indikatoren, die in regelmäßigen Abständen angeordnet sind. Die Trackbar verschiebt, die Sie angeben, und horizontal oder vertikal ausgerichtet werden können. Beispielsweise können Sie die Trackleiste verwenden, können Sie den Cursor Blink Rate oder mit dem Mauszeiger Geschwindigkeit für ein System steuern.  
  
## <a name="key-properties"></a>Wichtige Eigenschaften  
 Wichtigsten Eigenschaften der <xref:System.Windows.Forms.TrackBar> Steuerelement sind <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, und <xref:System.Windows.Forms.TrackBar.Maximum%2A>. <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>Gibt den Abstand der Teilstriche. <xref:System.Windows.Forms.TrackBar.Minimum%2A>und <xref:System.Windows.Forms.TrackBar.Maximum%2A> sind die kleinsten und größten Werte, die auf der Trackleiste dargestellt werden können.  
  
 Zwei wichtige Eigenschaften sind <xref:System.Windows.Forms.TrackBar.SmallChange%2A> und <xref:System.Windows.Forms.TrackBar.LargeChange%2A>. Der Wert, der die <xref:System.Windows.Forms.TrackBar.SmallChange%2A> Eigenschaft ist die Anzahl von Positionen Ziehpunkt bewegt wird, müssen die links oder nach-rechts-Taste gedrückt. Der Wert, der die <xref:System.Windows.Forms.TrackBar.LargeChange%2A> Eigenschaft ist die Anzahl von Positionen Ziehpunkt bewegt wird, nachdem die Bild-auf oder Bild-ab-Taste gedrückt, oder als Antwort auf Maus klickt auf der Trackleiste auf beiden Seiten des Ziehpunkts.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.TrackBar>  
 [TrackBar-Steuerelement](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)
