---
title: 두 시퀀스의 교집합 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 944d0b2efe1e74f901a493d1c3202d0f180d599d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792711"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="e8932-102">두 시퀀스의 교집합 반환</span><span class="sxs-lookup"><span data-stu-id="e8932-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="e8932-103"><xref:System.Linq.Queryable.Intersect%2A> 연산자를 사용하여 두 시퀀스의 교집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e8932-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8932-104">예제</span><span class="sxs-lookup"><span data-stu-id="e8932-104">Example</span></span>  
 <span data-ttu-id="e8932-105">이 예에서는 <xref:System.Linq.Queryable.Intersect%2A> 를 사용 하 여와 `Employees` 라이브 모두 `Customers` 에 있는 모든 국가/지역의 시퀀스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8932-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries/regions in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="e8932-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 <xref:System.Linq.Queryable.Intersect%2A> 작업은 집합에 대해서만 적절하게 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8932-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="e8932-107">다중 집합에 대한 의미 체계는 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8932-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8932-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8932-108">See also</span></span>

- [<span data-ttu-id="e8932-109">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="e8932-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="e8932-110">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="e8932-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
