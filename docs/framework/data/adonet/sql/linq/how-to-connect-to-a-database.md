---
title: 'Gewusst wie: Verbinden mit einer Datenbank'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a5447ce64803405668a2d486c7b3071b5ff923cb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-connect-to-a-database"></a>Gewusst wie: Verbinden mit einer Datenbank
Der <xref:System.Data.Linq.DataContext> ist die "Hauptleitung" für die Verbindung zu einer Datenbank, für das Abrufen von Objekten und für das Übergeben von Änderungen. Verwenden Sie die <xref:System.Data.Linq.DataContext> genauso verwenden würden, wie ein [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] <xref:System.Data.SqlClient.SqlConnection>. Tatsächlich wird der <xref:System.Data.Linq.DataContext> mit einer von Ihnen angegebenen Verbindung oder Verbindungszeichenfolge initialisiert. Weitere Informationen finden Sie unter [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).  
  
 Der Zweck des <xref:System.Data.Linq.DataContext> besteht in der Übersetzung Ihrer Objektanforderungen in SQL-Abfragen für die Datenbank und in der anschließenden Zusammenstellung von Objekten aus den Ergebnissen. Der <xref:System.Data.Linq.DataContext> unterstützt [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] durch die Implementierung des gleichen Operatormusters wie bei den standardmäßigen Abfrageoperatoren, z. B. `Where` und `Select`.  
  
> [!IMPORTANT]
>  Der Erhalt einer sicheren Verbindung ist von grundlegender Bedeutung. Weitere Informationen finden Sie unter [Sicherheit in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der <xref:System.Data.Linq.DataContext> zum Herstellen einer Verbindung zur Beispieldatenbank Nordwind und zum Abrufen von Zeilen mit Kunden aus London verwendet.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 Jede Datenbanktabelle wird als `Table`-Auflistung dargestellt, die über die <xref:System.Data.Linq.DataContext.GetTable%2A>-Methode zur Verfügung steht. Zur Identifikation wird hierbei die Entitätsklasse verwendet.  
  
## <a name="example"></a>Beispiel  
 Die bewährte Methode besteht in der Deklaration eines starken <xref:System.Data.Linq.DataContext> anstelle der grundlegenden <xref:System.Data.Linq.DataContext>-Klasse und der <xref:System.Data.Linq.DataContext.GetTable%2A>-Methode. Ein starker <xref:System.Data.Linq.DataContext> deklariert alle `Table`-Auflistungen wie im folgenden Beispiel als Kontextmember.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 Sie können dann die Abfrage von Kunden aus London wie folgt einfacher ausdrücken:  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch  
 [Kommunizieren mit der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
