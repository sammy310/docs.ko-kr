---
title: '메서드 기반 쿼리 구문 예제: 프로젝션(LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0fc2c8f0-1967-4f30-8b20-39b8dccfb82f
ms.openlocfilehash: 2790ed3e7f8fc2fe6a5c920be8a79402692d6282
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147907"
---
# <a name="method-based-query-syntax-examples-projection-linq-to-dataset"></a>메서드 기반 쿼리 구문 예제: 프로젝션(LINQ to DataSet)

이 항목의 예제에서는 <xref:System.Linq.Enumerable.Select%2A> 및 <xref:System.Linq.Enumerable.SelectMany%2A> 메서드에서 메서드 기반 쿼리 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.  
  
 이러한 예제에서 사용되는 `FillDataSet` 메서드는 [데이터집합에 데이터를 로드](loading-data-into-a-dataset.md)하는데 지정됩니다.  
  
 이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.  
  
 이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 자세한 내용은 [방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기](how-to-create-a-linq-to-dataset-project-in-vs.md)를 참조 하세요.  
  
## <a name="select"></a>선택  
  
### <a name="example"></a>예제  

 이 예제에서는 <xref:System.Linq.Enumerable.Select%2A> 메서드를 사용하여 `Name`, `ProductNumber` 및 `ListPrice` 속성을 익명 형식 시퀀스로 프로젝션합니다.  `ListPrice` 속성 이름도 결과 형식에서 `Price`로 바뀝니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## <a name="selectmany"></a>SelectMany  
  
### <a name="example"></a>예제  

 이 예제에서는 <xref:System.Linq.Enumerable.SelectMany%2A> 메서드를 사용하여 `TotalDue`가 500.00보다 작은 모든 주문을 선택합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a>예제  

 이 예제에서는 <xref:System.Linq.Enumerable.SelectMany%2A> 메서드를 사용하여 2002년 10월 1일 이후에 작성된 모든 주문을 선택합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a>참고 항목

- [데이터를 데이터 세트에 로드](loading-data-into-a-dataset.md)
- [LINQ to DataSet 예제](linq-to-dataset-examples.md)
- [표준 쿼리 연산자 개요(C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [표준 쿼리 연산자 개요(Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
