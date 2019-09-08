---
title: 두 시퀀스의 합집합 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 1b981d3002cf4a23897ce98927aebe96086f8a4a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781225"
---
# <a name="return-the-set-union-of-two-sequences"></a>두 시퀀스의 합집합 반환
<xref:System.Linq.Queryable.Union%2A> 연산자를 사용하여 두 시퀀스의 합집합을 반환합니다.  
  
## <a name="example"></a>예제  
 이 예에서는 <xref:System.Linq.Queryable.Union%2A> 를 사용 하 여 `Customers` 또는 `Employees`가 있는 모든 국가/지역의 시퀀스를 반환 합니다.  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]연산자는 <xref:System.Linq.Queryable.Union%2A> 다중 집합에 대해 순서가 지정 되지 않은 다중 집합의 연결 (SQL의 [`UNION ALL`](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) 절 결과 효과적)으로 정의 됩니다.

자세한 내용과 예제는를 참조 <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>하세요.
  
## <a name="see-also"></a>참고자료

- [쿼리 예제](query-examples.md)
- [표준 쿼리 연산자 변환](standard-query-operator-translation.md)
