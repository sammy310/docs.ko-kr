---
description: '자세한 정보: 시퀀스에서 중복 요소 제거'
title: 시퀀스에서 중복 요소 제거
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
ms.openlocfilehash: f371fc27794361e3ea92d342f845996d9291d30c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786097"
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a>시퀀스에서 중복 요소 제거

<xref:System.Linq.Queryable.Distinct%2A> 연산자를 사용하여 시퀀스에서 중복 요소를 제거합니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 <xref:System.Linq.Queryable.Distinct%2A>를 사용하여 고객이 있는 고유한 도시의 시퀀스를 선택합니다.  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a>참고 항목

- [쿼리 예제](query-examples.md)
