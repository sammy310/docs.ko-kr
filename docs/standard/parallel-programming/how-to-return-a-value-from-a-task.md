---
title: '방법: 작업에서 값 반환'
description: .NET에서 System.Threading.Tasks.Task<TResult> 형식을 사용하여 Result 속성에서 값을 반환하는 방법을 참조하세요.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: 051cef7cac654e4369ec1486884876004370ba0b
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767977"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="c895d-103">방법: 작업에서 값 반환</span><span class="sxs-lookup"><span data-stu-id="c895d-103">How to: Return a Value from a Task</span></span>
<span data-ttu-id="c895d-104">다음 예제에서는 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> 형식을 사용하여 <xref:System.Threading.Tasks.Task%601.Result%2A> 속성의 값을 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c895d-104">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="c895d-105">이 예제를 실행하려면 C:\Users\Public\Pictures\Sample Pictures\ 디렉터리가 있고 파일을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c895d-105">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c895d-106">예제</span><span class="sxs-lookup"><span data-stu-id="c895d-106">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="c895d-107"><xref:System.Threading.Tasks.Task%601.Result%2A> 속성은 작업이 완료될 때까지 호출 스레드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="c895d-107">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="c895d-108">하나의 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> 결과를 연속 작업에 전달하는 방법을 보려면 [연속 작업을 사용하여 작업 연결](chaining-tasks-by-using-continuation-tasks.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c895d-108">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c895d-109">참조</span><span class="sxs-lookup"><span data-stu-id="c895d-109">See also</span></span>

- [<span data-ttu-id="c895d-110">작업 기반 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="c895d-110">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="c895d-111">PLINQ 및 TPL의 람다 식</span><span class="sxs-lookup"><span data-stu-id="c895d-111">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
