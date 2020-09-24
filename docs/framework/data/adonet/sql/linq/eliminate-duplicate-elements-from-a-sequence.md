---
title: 시퀀스에서 중복 요소 제거
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
ms.openlocfilehash: 0dca1a635fd1cc6e48e8ad914909769b2cf0e66d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161375"
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a>시퀀스에서 중복 요소 제거

<xref:System.Linq.Queryable.Distinct%2A> 연산자를 사용하여 시퀀스에서 중복 요소를 제거합니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 <xref:System.Linq.Queryable.Distinct%2A>를 사용하여 고객이 있는 고유한 도시의 시퀀스를 선택합니다.  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a>참고 항목

- [쿼리 예제](query-examples.md)
