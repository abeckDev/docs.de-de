---
title: Paging (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: dfbd282eed19fdfa81a1dda5d06d41a80386feaa
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="paging-entity-sql"></a>Paging (Entity SQL)
Physisches Paging kann ausgeführt werden, mithilfe der [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) und [Grenzwert](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) -Unterklausel in der [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) Klausel. Um physisches Paging deterministisch durchzuführen, sollten Sie SKIP und LIMIT verwenden. Wenn Sie nur die Anzahl der Zeilen in einer Tabelle in einer nicht-deterministische Weise beschränken möchten, verwenden Sie [oben](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md). 
          TOP und SKIP/LIMIT schließen sich gegenseitig aus.  
  
## <a name="top-overview"></a>Übersicht über 'TOP'  
 Der SELECT-Klausel kann hinter dem optionalen ALL/DISTINCT-Modifizierer eine TOP-Unterklausel angefügt werden. Die TOP-Unterklausel gibt an, dass nur der erste Zeilensatz aus dem Abfrageergebnis zurückgegeben wird. Weitere Informationen finden Sie unter [oben](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).  
  
## <a name="skip-and-limit-overview"></a>Übersicht über 'SKIP' und 'LIMIT'  
 SKIP und LIMIT sind Teil der ORDER BY-Klausel. Wenn eine ORDER BY-Klausel den Ausdruck SKIP als Unterklausel enthält, werden die Ergebnisse den Sortierangaben entsprechend sortiert, und das Resultset enthält die Zeilen, die auf den SKIP-Ausdruck folgen. Mit SKIP 5 werden beispielsweise die ersten fünf Zeilen übersprungen und nur die Zeilen ab der sechsten Zeile zurückgegeben. Wenn eine ORDER BY-Klausel den Ausdruck LIMIT als Unterklausel enthält, wird das Abfrageergebnis den Sortierangaben entsprechend sortiert, und die Anzahl der zurückgegebenen Zeilen wird durch den LIMIT-Ausdruck begrenzt. 
          LIMIT 5 z. B. begrenzt das Resultset auf fünf Instanzen oder Zeilen. SKIP und LIMIT müssen nicht gemeinsam verwendet werden; Sie können auch nur SKIP oder nur LIMIT mit der ORDER BY-Klausel verwenden. Weitere Informationen finden Sie unter den folgenden Themen:  
  
-   [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
-   [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
-   [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Vorgehensweise: seitenweise durch Abfrageresultate navigieren](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)
