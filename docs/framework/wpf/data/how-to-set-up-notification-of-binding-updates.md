---
title: "Gewusst wie: Einrichten von Benachrichtigungen über Bindungsaktualisierungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a07337e99e985bfbc0a5dbc5f2d231ee36cf1422
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-up-notification-of-binding-updates"></a>Gewusst wie: Einrichten von Benachrichtigungen über Bindungsaktualisierungen
In diesem Beispiel wird erläutert, wie Sie Benachrichtigungen einrichten können, die Sie darüber informieren, wenn die Eigenschaft „Bindungsziel (Ziel)“ oder „Bindungsquelle (Quelle)“ einer Bindung aktualisiert wurde.  
  
## <a name="example"></a>Beispiel  
 Bei jeder Aktualisierung der Bindungsquelle oder des Bindungsziels löst [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ein Datenaktualisierungsereignis aus. Intern veranlasst dieses Ereignis die Benutzeroberfläche (User Interface, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]), eine Aktualisierung durchzuführen, weil sich die gebundenen Daten geändert haben. Beachten Sie, dass für diese Ereignisse zu arbeiten, und auch für die unidirektionale oder bidirektionale Bindung ordnungsgemäß funktioniert, Sie der Klasse mit implementieren müssen die <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle. Weitere Informationen finden Sie unter [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
 Legen Sie die <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> oder <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> -Eigenschaft (oder beides), `true` in der Bindung. Der Handler, den Sie zur Überwachung dieses Ereignisses bereitstellen, muss direkt an das Element angefügt werden, über dessen Änderungen Sie informiert werden möchten. Oder er muss an den Gesamtdatenkontext angefügt werden, wenn Sie über Änderungen am Kontext informiert werden möchten.  
  
 Im folgenden Beispiel wird erläutert, wie Sie Benachrichtigungen für die Aktualisierung einer Zieleigenschaft einrichten.  
  
 [!code-xaml[DirectionalBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 Anschließend können Sie zur Behandlung des Ereignisses einen Handler auf Grundlage des EventHandler\<T>-Delegaten einrichten, in diesem Beispiel *OnTargetUpdated*:  
  
 [!code-csharp[DirectionalBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 Parameter des Ereignisses können zur Ermittlung von Details über die geänderte Eigenschaft (z. B. den Typ oder das jeweilige Element, wenn derselbe Handler an mehrere Elemente angefügt ist) verwendet werden. Diese Details können hilfreich sein, wenn es für ein einzelnes Element mehrere gebundene Eigenschaften gibt.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
