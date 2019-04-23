---
title: 두 시퀀스 간의 차집합 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 7edc60c7ab8510aadd9ac273529a88adeb41352a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124282"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="4f866-102">두 시퀀스 간의 차집합 반환</span><span class="sxs-lookup"><span data-stu-id="4f866-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="4f866-103"><xref:System.Linq.Queryable.Except%2A> 연산자를 사용하여 두 시퀀스 간의 차집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4f866-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f866-104">예제</span><span class="sxs-lookup"><span data-stu-id="4f866-104">Example</span></span>  
 <span data-ttu-id="4f866-105">이 예제에서는 <xref:System.Linq.Queryable.Except%2A>을 사용하여 `Customers`는 살지만 `Employees`가 살지 않는 모든 국가의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4f866-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="4f866-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 <xref:System.Linq.Queryable.Except%2A> 작업은 집합에 대해서만 적절하게 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f866-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="4f866-107">다중 집합에 대한 의미 체계는 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f866-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f866-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="4f866-108">See also</span></span>

- [<span data-ttu-id="4f866-109">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="4f866-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="4f866-110">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="4f866-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
