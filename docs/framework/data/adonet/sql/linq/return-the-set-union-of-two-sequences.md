---
title: 두 시퀀스의 합집합 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 0fe32d8c3c37e99a50ca03262dc6184337b4450e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200207"
---
# <a name="return-the-set-union-of-two-sequences"></a>두 시퀀스의 합집합 반환

<xref:System.Linq.Queryable.Union%2A> 연산자를 사용하여 두 시퀀스의 합집합을 반환합니다.  
  
## <a name="example"></a>예제  

 이 예에서는 <xref:System.Linq.Queryable.Union%2A> 를 사용 하 여 또는가 있는 모든 국가/지역의 시퀀스를 반환 `Customers` 합니다 `Employees` .  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 연산자는 <xref:System.Linq.Queryable.Union%2A> 다중 집합에 대해 순서가 지정 되지 않은 다중 집합의 연결 (SQL의 절 결과 효과적)으로 정의 됩니다 [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) .

자세한 내용과 예제는를 참조 <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType> 하세요.
  
## <a name="see-also"></a>참고 항목

- [쿼리 예제](query-examples.md)
- [표준 쿼리 연산자 변환](standard-query-operator-translation.md)
