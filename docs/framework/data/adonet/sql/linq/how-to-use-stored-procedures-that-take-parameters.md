---
title: "如何：使用采用参数的存储过程"
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
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fbd4e0b7534a213f56c5c6ba60208d3024535bd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a>如何：使用采用参数的存储过程
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 将输出参数映射到引用参数，并且对于值类型，它将参数声明为可以为 null。  
  
 有关如何在返回行集的查询中使用输入的参数的示例，请参阅[如何： 返回行集](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)。  
  
## <a name="example"></a>示例  
 下面的示例带有单个输入参数（客户 ID）并返回一个输出参数（该客户的总销售额）。  
  
```  
CREATE PROCEDURE [dbo].[CustOrderTotal]   
@CustomerID nchar(5),  
@TotalSales money OUTPUT  
AS  
SELECT @TotalSales = SUM(OD.UNITPRICE*(1-OD.DISCOUNT) * OD.QUANTITY)  
FROM ORDERS O, "ORDER DETAILS" OD  
where O.CUSTOMERID = @CustomerID AND O.ORDERID = OD.ORDERID  
```  
  
 [!code-csharp[DLinqSprox#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#2)]
 [!code-vb[DLinqSprox#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#2)]  
  
## <a name="example"></a>示例  
 您将按如下方式调用此存储过程：  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>另请参阅  
 [存储的过程](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [使用可以为 null 的类型](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [可以为 null 的值类型](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
