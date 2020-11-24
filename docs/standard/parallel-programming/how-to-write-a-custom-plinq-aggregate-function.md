---
title: '방법: 사용자 지정 PLINQ 집계 함수 작성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
ms.openlocfilehash: d04f90e9c763c8ddba5ba07b650ffb878869ff3a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825470"
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a><span data-ttu-id="1eb00-102">방법: 사용자 지정 PLINQ 집계 함수 작성</span><span class="sxs-lookup"><span data-stu-id="1eb00-102">How to: Write a Custom PLINQ Aggregate Function</span></span>
<span data-ttu-id="1eb00-103">이 예제는 <xref:System.Linq.ParallelEnumerable.Aggregate%2A> 메서드를 사용하여 소스 시퀀스에 사용자 지정 집계 함수를 적용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1eb00-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.Aggregate%2A> method to apply a custom aggregation function to a source sequence.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="1eb00-104">이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eb00-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="1eb00-105">속도 향상에 대한 자세한 내용은 [PLINQ의 속도 향상 이해](understanding-speedup-in-plinq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eb00-105">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eb00-106">예제</span><span class="sxs-lookup"><span data-stu-id="1eb00-106">Example</span></span>  
 <span data-ttu-id="1eb00-107">다음 예제는 정수 시퀀스의 표준 편차를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="1eb00-107">The following example calculates the standard deviation of a sequence of integers.</span></span>  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 <span data-ttu-id="1eb00-108">이 예제에서는 PLINQ에 고유한 집계 표준 쿼리 연산자의 오버로드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1eb00-108">This example uses an overload of the Aggregate standard query operator that is unique to PLINQ.</span></span> <span data-ttu-id="1eb00-109">이 오버로드는 세 번째 입력 매개 변수로 추가 <xref:System.Func%603?displayProperty=nameWithType>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1eb00-109">This overload takes an extra <xref:System.Func%603?displayProperty=nameWithType> as the third input parameter.</span></span> <span data-ttu-id="1eb00-110">이 대리자는 집계 결과에 대한 최종 계산을 수행하기 전에 모든 스레드의 결과를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="1eb00-110">This delegate combines the results from all threads before it performs the final calculation on the aggregated results.</span></span> <span data-ttu-id="1eb00-111">이 예제에서는 모든 스레드의 합계를 함께 더합니다.</span><span class="sxs-lookup"><span data-stu-id="1eb00-111">In this example we add together the sums from all the threads.</span></span>  
  
 <span data-ttu-id="1eb00-112">람다 식 본문이 단일식으로 구성된 경우 <xref:System.Func%602?displayProperty=nameWithType> 대리자의 반환 값은 식의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1eb00-112">Note that when a lambda expression body consists of a single expression, the return value of the <xref:System.Func%602?displayProperty=nameWithType> delegate is the value of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb00-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1eb00-113">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="1eb00-114">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="1eb00-114">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
