---
title: '방법: DataContext 수준 필터링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: 343cffa9b1c034068e5abcc652e936f89ee6a992
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084585"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="cb650-102">방법: DataContext 수준 필터링</span><span class="sxs-lookup"><span data-stu-id="cb650-102">How to: Filter at the DataContext Level</span></span>
<span data-ttu-id="cb650-103">`EntitySets` 수준에서 `DataContext`를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb650-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="cb650-104">이러한 필터는 <xref:System.Data.Linq.DataContext> 인스턴스로 수행되는 모든 쿼리에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb650-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb650-105">예제</span><span class="sxs-lookup"><span data-stu-id="cb650-105">Example</span></span>  
 <span data-ttu-id="cb650-106">다음 예제에서는 <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> 기준으로 고객의 미리 로드된 주문을 필터링하기 위해 `ShippedDate`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb650-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="cb650-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="cb650-107">See also</span></span>

- [<span data-ttu-id="cb650-108">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="cb650-108">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
