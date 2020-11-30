---
title: '방법: 병렬 루프의 예외 처리'
description: .NET에서 병렬 루프의 예외를 처리하는 방법을 알아봅니다. System.AggregateException에서 루프의 모든 예외를 래핑하는 방법의 예제를 참조하세요.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to handle exceptions
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
ms.openlocfilehash: 903db7f7318a9067c31af090490bab6dd70fa0ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734480"
---
# <a name="how-to-handle-exceptions-in-parallel-loops"></a><span data-ttu-id="622fc-104">방법: 병렬 루프의 예외 처리</span><span class="sxs-lookup"><span data-stu-id="622fc-104">How to: Handle Exceptions in Parallel Loops</span></span>

<span data-ttu-id="622fc-105"><xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 오버로드에는 throw될 수 있는 예외를 처리하기 위한 특별한 메커니즘이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="622fc-105">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> overloads do not have any special mechanism to handle exceptions that might be thrown.</span></span> <span data-ttu-id="622fc-106">이런 점에서 일반 `for` 및 `foreach` 루프(Visual Basic의 `For` 및 `For Each`)와 비슷합니다. 처리되지 않은 예외로 인해 현재 실행 중인 모든 반복이 완료되는 즉시 루프가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="622fc-106">In this respect, they resemble regular `for` and `foreach` loops (`For` and `For Each` in Visual Basic); an unhandled exception causes the loop to terminate as soon as all currently running iterations finish.</span></span>
  
 <span data-ttu-id="622fc-107">병렬 루프에 고유한 예외 처리 논리를 추가할 때 비슷한 예외가 여러 스레드에서 동시에 throw되는 경우와 한 스레드에서 throw된 예외로 인해 다른 스레드에서 다른 예외가 throw되는 경우를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="622fc-107">When you add your own exception-handling logic to parallel loops, handle the case in which similar exceptions might be thrown on multiple threads concurrently, and the case in which an exception thrown on one thread causes another exception to be thrown on another thread.</span></span> <span data-ttu-id="622fc-108"><xref:System.AggregateException?displayProperty=nameWithType>에서 루프의 모든 예외를 래핑하여 두 경우 모두를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="622fc-108">You can handle both cases by wrapping all exceptions from the loop in a <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="622fc-109">다음 예제에서는 한 가지 가능한 접근 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="622fc-109">The following example shows one possible approach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="622fc-110">“내 코드만”이 사용하도록 설정된 경우 Visual Studio가 예외를 발생시키는 줄에서 중단하고 "예외가 사용자 코드에서 처리되지 않았다"는 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="622fc-110">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="622fc-111">이 오류는 심각하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="622fc-111">This error is benign.</span></span> <span data-ttu-id="622fc-112">F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="622fc-112">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the example below.</span></span> <span data-ttu-id="622fc-113">첫 번째 오류 지점에서 Visual Studio가 실행을 중단하지 않도록 하려면 **도구, 옵션, 디버깅, 일반** 을 차례로 선택하고 “내 코드만” 확인란의 선택을 취소하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="622fc-113">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="622fc-114">예제</span><span class="sxs-lookup"><span data-stu-id="622fc-114">Example</span></span>  

 <span data-ttu-id="622fc-115">이 예제에서는 모든 예외가 catch되고 나서 throw된 <xref:System.AggregateException?displayProperty=nameWithType>로 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="622fc-115">In this example, all exceptions are caught and then wrapped in an <xref:System.AggregateException?displayProperty=nameWithType> which is thrown.</span></span> <span data-ttu-id="622fc-116">호출자는 처리할 예외를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="622fc-116">The caller can decide which exceptions to handle.</span></span>  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="622fc-117">참조</span><span class="sxs-lookup"><span data-stu-id="622fc-117">See also</span></span>

- [<span data-ttu-id="622fc-118">데이터 병렬 처리</span><span class="sxs-lookup"><span data-stu-id="622fc-118">Data Parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="622fc-119">PLINQ 및 TPL의 람다 식</span><span class="sxs-lookup"><span data-stu-id="622fc-119">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
