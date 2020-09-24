---
title: 제네릭 목록으로 시퀀스 변환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 79e3ddaff0234dfb5f91e36bacd3279afa9ec265
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164391"
---
# <a name="convert-a-sequence-to-a-generic-list"></a>제네릭 목록으로 시퀀스 변환

<xref:System.Linq.Enumerable.ToList%2A>를 사용하여 시퀀스에서 제네릭 목록을 만듭니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 <xref:System.Linq.Enumerable.ToList%2A>를 사용하여 제네릭 <xref:System.Collections.Generic.List%601>에 대한 쿼리를 즉시 평가합니다.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>참고 항목

- [쿼리 예제](query-examples.md)
