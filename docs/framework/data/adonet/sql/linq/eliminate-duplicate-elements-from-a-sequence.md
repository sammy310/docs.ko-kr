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
# <a name="eliminate-duplicate-elements-from-a-sequence"></a><span data-ttu-id="0f910-102">시퀀스에서 중복 요소 제거</span><span class="sxs-lookup"><span data-stu-id="0f910-102">Eliminate Duplicate Elements from a Sequence</span></span>

<span data-ttu-id="0f910-103"><xref:System.Linq.Queryable.Distinct%2A> 연산자를 사용하여 시퀀스에서 중복 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0f910-103">Use the <xref:System.Linq.Queryable.Distinct%2A> operator to eliminate duplicate elements from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f910-104">예제</span><span class="sxs-lookup"><span data-stu-id="0f910-104">Example</span></span>  

 <span data-ttu-id="0f910-105">다음 예제에서는 <xref:System.Linq.Queryable.Distinct%2A>를 사용하여 고객이 있는 고유한 도시의 시퀀스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f910-105">The following example uses <xref:System.Linq.Queryable.Distinct%2A> to select a sequence of the unique cities that have customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a><span data-ttu-id="0f910-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f910-106">See also</span></span>

- [<span data-ttu-id="0f910-107">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="0f910-107">Query Examples</span></span>](query-examples.md)
