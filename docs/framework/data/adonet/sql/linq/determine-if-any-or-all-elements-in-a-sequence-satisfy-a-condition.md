---
description: '자세한 정보: 시퀀스의 모든 요소 또는 모든 요소가 조건을 만족 하는지 확인'
title: 시퀀스에서 일부 또는 모든 요소가 조건을 만족하는지 확인
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: a46cf7e4e213eba830dc203f9266a408103cee80
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786110"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a>시퀀스에서 일부 또는 모든 요소가 조건을 만족하는지 확인

시퀀스의 모든 요소가 조건을 만족하면 <xref:System.Linq.Enumerable.All%2A> 연산자에서는 `true`를 반환합니다.  
  
 시퀀스의 모든 요소가 조건을 만족하면 <xref:System.Linq.Queryable.Any%2A> 연산자에서는 `true`를 반환합니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 적어도 하나의 주문이 있는 고객의 시퀀스를 반환합니다. `Where` / `where` `true` 지정 된에가 있는 경우 절은로 평가 `Customer` `Order` 됩니다.  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a>예제  

 다음 Visual Basic 코드에서는 주문을 하지 않은 고객의 목록을 확인하고 해당 목록에 있는 모든 고객에 대한 연락처 이름을 제공합니다.  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a>예제  

 다음 C# 예제에서는 "C"로 시작하는 `ShipCity`가 있는 주문의 고객 시퀀스를 반환합니다. 또한 반환에는 주문이 없는 고객도 포함됩니다. 기본적으로 <xref:System.Linq.Queryable.All%2A> 연산자는 `true` 빈 시퀀스에 대해를 반환 합니다. 주문이 없는 고객은 연산자를 사용 하 여 콘솔 출력에서 제거 됩니다 `Count` .  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a>참고 항목

- [쿼리 예제](query-examples.md)
