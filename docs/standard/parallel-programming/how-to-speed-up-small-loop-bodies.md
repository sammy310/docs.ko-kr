---
title: '방법: 작은 루프 본문 속도 개선'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
ms.openlocfilehash: 2597e37ed5901d704c94ff960bcb4b2c97633392
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722400"
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="f2c1d-102">방법: 작은 루프 본문 속도 개선</span><span class="sxs-lookup"><span data-stu-id="f2c1d-102">How to: Speed Up Small Loop Bodies</span></span>

<span data-ttu-id="f2c1d-103"><xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> 루프에 작은 본문이 있는 경우 C#의 [for](../../csharp/language-reference/keywords/for.md) 루프 및 Visual Basic의 [For](/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) 루프와 같은 동등한 순차 루프보다 성능이 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2c1d-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](../../csharp/language-reference/keywords/for.md) loop in C# and the [For](/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) loop in Visual Basic.</span></span> <span data-ttu-id="f2c1d-104">성능 저하는 데이터 분할과 관련된 오버헤드 및 각 루프 반복에서 대리자를 호출하는 비용으로 인해 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c1d-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="f2c1d-105">이러한 시나리오를 처리하기 위해 <xref:System.Collections.Concurrent.Partitioner> 클래스는 <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> 메서드를 제공합니다. 이 메서드를 통해 대리자가 반복당 한 번이 아니라 파티션당 한 번만 호출되도록 대리자 본문에 대한 순차 루프를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2c1d-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="f2c1d-106">자세한 내용은 [PLINQ 및 TPL에 대한 사용자 지정 파티셔너](custom-partitioners-for-plinq-and-tpl.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f2c1d-106">For more information, see [Custom Partitioners for PLINQ and TPL](custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2c1d-107">예제</span><span class="sxs-lookup"><span data-stu-id="f2c1d-107">Example</span></span>  

 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="f2c1d-108">이 예제에서 설명하는 접근 방식은 루프가 최소한의 작업을 수행하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c1d-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="f2c1d-109">작업이 많은 계산을 포함하게 되면 기본 파티셔너와 함께 <xref:System.Threading.Tasks.Parallel.For%2A> 또는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프를 사용하여 동일하거나 더 나은 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2c1d-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2c1d-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2c1d-110">See also</span></span>

- [<span data-ttu-id="f2c1d-111">데이터 병렬 처리</span><span class="sxs-lookup"><span data-stu-id="f2c1d-111">Data Parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="f2c1d-112">PLINQ 및 TPL에 대한 사용자 지정 파티셔너</span><span class="sxs-lookup"><span data-stu-id="f2c1d-112">Custom Partitioners for PLINQ and TPL</span></span>](custom-partitioners-for-plinq-and-tpl.md)
- [<span data-ttu-id="f2c1d-113">반복기(C#)</span><span class="sxs-lookup"><span data-stu-id="f2c1d-113">Iterators (C#)</span></span>](../../csharp/programming-guide/concepts/iterators.md)
- [<span data-ttu-id="f2c1d-114">반복기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2c1d-114">Iterators (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/iterators.md)
- [<span data-ttu-id="f2c1d-115">PLINQ 및 TPL의 람다 식</span><span class="sxs-lookup"><span data-stu-id="f2c1d-115">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
