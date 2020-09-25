---
title: 두 시퀀스 간의 차집합 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 49a8d22377ef1f7d0fde16880a82002754e1bbc4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200331"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="bc216-102">두 시퀀스 간의 차집합 반환</span><span class="sxs-lookup"><span data-stu-id="bc216-102">Return the Set Difference Between Two Sequences</span></span>

<span data-ttu-id="bc216-103"><xref:System.Linq.Queryable.Except%2A> 연산자를 사용하여 두 시퀀스 간의 차집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bc216-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc216-104">예제</span><span class="sxs-lookup"><span data-stu-id="bc216-104">Example</span></span>  

 <span data-ttu-id="bc216-105">이 예에서는 <xref:System.Linq.Queryable.Except%2A> 를 사용 하 여 살고 있지만 살고 있는 모든 국가/지역의 시퀀스를 반환 `Customers` `Employees` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc216-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="bc216-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 <xref:System.Linq.Queryable.Except%2A> 작업은 집합에 대해서만 적절하게 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc216-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="bc216-107">다중 집합에 대한 의미 체계는 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc216-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc216-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc216-108">See also</span></span>

- [<span data-ttu-id="bc216-109">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="bc216-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="bc216-110">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="bc216-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
