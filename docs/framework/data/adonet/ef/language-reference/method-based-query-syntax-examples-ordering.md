---
title: '메서드 기반 쿼리 구문 예제: 순서 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5d21b178-d731-471a-8534-1f8184a2ef06
ms.openlocfilehash: e213046955c2c4e720c56adb96da29078ea3c48d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760573"
---
# <a name="method-based-query-syntax-examples-ordering"></a>메서드 기반 쿼리 구문 예제: 순서 지정
이 항목의 예제에 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Linq.Enumerable.ThenBy%2A> 쿼리 메서드는 [AdventureWorks Sales 모델](https://archive.codeplex.com/?p=msftdbprodsamples) 메서드 기반 쿼리 구문을 사용 하 여 합니다. 이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.  
  
 이 항목의 예제에서는 다음을 사용 `using` / `Imports` 문:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="thenby"></a>ThenBy  
  
### <a name="example"></a>예제  
 다음 메서드 기반 쿼리 구문 예제에서는 <xref:System.Linq.Queryable.OrderBy%2A> 및 <xref:System.Linq.Queryable.ThenBy%2A>를 사용하여 연락처 목록을 성을 기준으로 정렬한 다음 이름을 기준으로 정렬하여 반환합니다.  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby_mq)]
 [!code-vb[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby_mq)]  
  
## <a name="thenbydescending"></a>ThenByDescending  
  
### <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Linq.Queryable.OrderBy%2A> 및 <xref:System.Linq.Queryable.ThenByDescending%2A> 메서드를 사용하여 먼저 가격을 기준으로 정렬한 다음 제품 이름을 내림차순으로 정렬합니다.  
  
 [!code-csharp[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescending_mq)]
 [!code-vb[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescending_mq)]  
  
## <a name="see-also"></a>참고자료

- [LINQ to Entities에서 쿼리](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
