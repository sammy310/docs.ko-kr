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
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a><span data-ttu-id="d74a8-103">시퀀스에서 일부 또는 모든 요소가 조건을 만족하는지 확인</span><span class="sxs-lookup"><span data-stu-id="d74a8-103">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>

<span data-ttu-id="d74a8-104">시퀀스의 모든 요소가 조건을 만족하면 <xref:System.Linq.Enumerable.All%2A> 연산자에서는 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d74a8-104">The <xref:System.Linq.Enumerable.All%2A> operator returns `true` if all elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="d74a8-105">시퀀스의 모든 요소가 조건을 만족하면 <xref:System.Linq.Queryable.Any%2A> 연산자에서는 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d74a8-105">The <xref:System.Linq.Queryable.Any%2A> operator returns `true` if any element in a sequence satisfies a condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d74a8-106">예제</span><span class="sxs-lookup"><span data-stu-id="d74a8-106">Example</span></span>  

 <span data-ttu-id="d74a8-107">다음 예제에서는 적어도 하나의 주문이 있는 고객의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d74a8-107">The following example returns a sequence of customers that have at least one order.</span></span> <span data-ttu-id="d74a8-108">`Where` / `where` `true` 지정 된에가 있는 경우 절은로 평가 `Customer` `Order` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d74a8-108">The `Where`/`where` clause evaluates to `true` if the given `Customer` has any `Order`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="d74a8-109">예제</span><span class="sxs-lookup"><span data-stu-id="d74a8-109">Example</span></span>  

 <span data-ttu-id="d74a8-110">다음 Visual Basic 코드에서는 주문을 하지 않은 고객의 목록을 확인하고 해당 목록에 있는 모든 고객에 대한 연락처 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d74a8-110">The following Visual Basic code determines the list of customers who have not placed orders, and ensures that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a><span data-ttu-id="d74a8-111">예제</span><span class="sxs-lookup"><span data-stu-id="d74a8-111">Example</span></span>  

 <span data-ttu-id="d74a8-112">다음 C# 예제에서는 "C"로 시작하는 `ShipCity`가 있는 주문의 고객 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d74a8-112">The following C# example returns a sequence of customers whose orders have a `ShipCity` beginning with "C".</span></span> <span data-ttu-id="d74a8-113">또한 반환에는 주문이 없는 고객도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d74a8-113">Also included in the return are customers who have no orders.</span></span> <span data-ttu-id="d74a8-114">기본적으로 <xref:System.Linq.Queryable.All%2A> 연산자는 `true` 빈 시퀀스에 대해를 반환 합니다. 주문이 없는 고객은 연산자를 사용 하 여 콘솔 출력에서 제거 됩니다 `Count` .</span><span class="sxs-lookup"><span data-stu-id="d74a8-114">(By design, the <xref:System.Linq.Queryable.All%2A> operator returns `true` for an empty sequence.) Customers with no orders are eliminated in the console output by using the `Count` operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="d74a8-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d74a8-115">See also</span></span>

- [<span data-ttu-id="d74a8-116">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="d74a8-116">Query Examples</span></span>](query-examples.md)
