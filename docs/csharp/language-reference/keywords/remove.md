---
title: remove (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 66647dee0c4cc728ae5e19457a4a5ef0e7f72248
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="remove-c-reference"></a>remove (C#-Referenz)
Das kontextabhängige Schlüsselwort `remove` definiert einen benutzerdefinierten Ereignisaccessor, der aufgerufen wird, wenn der Clientcode das Abonnement Ihres Ereignisses ([event](../../../csharp/language-reference/keywords/event.md)) aufhebt. Wenn Sie einen benutzerdefinierten `remove`-Accessor bereitstellen, müssen Sie auch einen [add](../../../csharp/language-reference/keywords/add.md)-Accessor angeben.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird ein Ereignis mit den benutzerdefinierten Accessoren [add](../../../csharp/language-reference/keywords/add.md) und `remove` gezeigt. Das vollständige Beispiel finden Sie unter [Vorgehensweise: Implementieren von Schnittstellenereignissen](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-csharp[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/remove_1.cs)]  
  
 Sie müssen normalerweise keine eigenen benutzerdefinierten Ereignisaccessoren bereitstellen. Die Accessoren, die automatisch vom Compiler generiert werden, wenn Sie ein Ereignis deklarieren, sind in den meisten Szenarios ausreichend.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisse](../../../csharp/programming-guide/events/index.md)
