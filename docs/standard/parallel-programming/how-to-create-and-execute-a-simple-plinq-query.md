---
title: '방법: 간단한 PLINQ 쿼리 만들기 및 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
ms.openlocfilehash: 67863346046b0c400529b87355c11f97d0c3f01f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827089"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a><span data-ttu-id="0c2dc-102">방법: 간단한 PLINQ 쿼리 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="0c2dc-102">How to: Create and Execute a Simple PLINQ Query</span></span>

<span data-ttu-id="0c2dc-103">이 문서의 예제에서는 소스 시퀀스에 대해 <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> 확장 메서드를 사용하여 단순한 병렬 LINQ(Language-Integrated Query) 쿼리를 만들고 <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithType> 메서드를 사용하여 쿼리를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-103">The example in this article shows how to create a simple Parallel Language Integrated Query (LINQ) query by using the <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> extension method on the source sequence and executing the query by using the <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithType> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c2dc-104">이 문서에서는 람다 식을 사용하여 PLINQ에 대리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="0c2dc-105">C# 또는 Visual Basic의 람다 식을 잘 모르는 경우 [PLINQ 및 TPL의 람다 식](lambda-expressions-in-plinq-and-tpl.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c2dc-106">예제</span><span class="sxs-lookup"><span data-stu-id="0c2dc-106">Example</span></span>  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 <span data-ttu-id="0c2dc-107">이 예제에서는 결과 시퀀스의 순서가 중요하지 않은 경우에 병렬 LINQ 쿼리를 만들고 실행하는 기본 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-107">This example demonstrates the basic pattern for creating and executing any Parallel LINQ query when the ordering of the result sequence is not important.</span></span> <span data-ttu-id="0c2dc-108">순서가 지정되지 않은 쿼리는 일반적으로 순서가 지정된 쿼리보다 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-108">Unordered queries are generally faster than ordered queries.</span></span> <span data-ttu-id="0c2dc-109">쿼리에서는 소스를 여러 스레드에서 비동기적으로 실행되는 작업으로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-109">The query partitions the source into tasks that are executed asynchronously on multiple threads.</span></span> <span data-ttu-id="0c2dc-110">각 작업이 완료되는 순서는 파티션의 요소를 처리하는 데 관련된 작업의 양뿐만 아니라 운영 체제에서 각 스레드를 예약하는 방식과 같은 외부 요소에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-110">The order in which each task completes depends not only on the amount of work involved to process the elements in the partition, but also on external factors such as how the operating system schedules each thread.</span></span> <span data-ttu-id="0c2dc-111">이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-111">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="0c2dc-112">속도 향상에 대한 자세한 내용은 [PLINQ의 속도 향상 이해](understanding-speedup-in-plinq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-112">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span> <span data-ttu-id="0c2dc-113">쿼리의 요소 순서를 유지하는 방법에 대한 자세한 내용은 [방법: PLINQ 쿼리의 순서 제어](how-to-control-ordering-in-a-plinq-query.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c2dc-113">For more information about how to preserve the ordering of elements in a query, see [How to: Control Ordering in a PLINQ Query](how-to-control-ordering-in-a-plinq-query.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c2dc-114">참조</span><span class="sxs-lookup"><span data-stu-id="0c2dc-114">See also</span></span>

- [<span data-ttu-id="0c2dc-115">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="0c2dc-115">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
