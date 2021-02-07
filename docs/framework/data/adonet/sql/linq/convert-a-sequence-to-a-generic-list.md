---
description: '자세한 정보: 시퀀스를 제네릭 목록으로 변환'
title: 제네릭 목록으로 시퀀스 변환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: e9832fd366f22b77674fb4c83f6af7ce89a552c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663120"
---
# <a name="convert-a-sequence-to-a-generic-list"></a>제네릭 목록으로 시퀀스 변환

<xref:System.Linq.Enumerable.ToList%2A>를 사용하여 시퀀스에서 제네릭 목록을 만듭니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 <xref:System.Linq.Enumerable.ToList%2A>를 사용하여 제네릭 <xref:System.Collections.Generic.List%601>에 대한 쿼리를 즉시 평가합니다.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>참고 항목

- [쿼리 예제](query-examples.md)
