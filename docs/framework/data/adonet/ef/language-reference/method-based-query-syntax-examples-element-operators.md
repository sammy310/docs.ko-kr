---
title: '메서드 기반 쿼리 구문 예제: 요소 연산자'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 3656ea6d2d9602c3790ab4113b5c2f153b4f7c73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760560"
---
# <a name="method-based-query-syntax-examples-element-operators"></a>메서드 기반 쿼리 구문 예제: 요소 연산자
이 항목의 예제에 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Linq.Enumerable.First%2A> 쿼리 메서드는 [AdventureWorks Sales 모델](https://archive.codeplex.com/?p=msftdbprodsamples) 메서드 기반 쿼리 구문을 사용 하 여 합니다. 이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.  
  
 이 항목의 예제에서는 다음 `using` / `Imports` 문:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a>First  
  
### <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Linq.Enumerable.First%2A> 메서드 'caroline'를 사용 하 여 시작 하는 첫 번째 전자 메일 주소를 찾을 수 있습니다.  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a>참고자료

- [LINQ to Entities에서 쿼리](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
