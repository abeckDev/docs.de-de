---
title: "Gewusst wie: Zurückgeben von \"Rowsets\""
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
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c2a11ae83be1c7f75c5bc440c5f8162877106b07
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-return-rowsets"></a>Gewusst wie: Zurückgeben von "Rowsets"
In diesem Beispiel wird ein Rowset von der Datenbank zurückgegeben. Er enthält einen Eingabeparameter, um das Ergebnis zu filtern.  
  
 Wenn Sie eine gespeicherte Prozedur, die ein Rowset zurückgibt ausführen, verwenden Sie eine *Ergebnis* -Klasse, die die Rückgabe aus der gespeicherten Prozedur speichert. Weitere Informationen finden Sie unter [Analysieren von LINQ to SQL-Quellcode](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine gespeicherte Prozedur dargestellt, die Zeilen mit Kunden zurückgibt und anhand eines Eingabeparameters nur die Zeilen zurückgibt, die „London“ als Ort für den Kunden enthalten. Dieses Beispiel setzt eine zählbare `CustomersByCityResult`-Klasse voraus.  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
