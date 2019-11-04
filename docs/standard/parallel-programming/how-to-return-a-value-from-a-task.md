---
title: '방법: 작업에서 값 반환'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: 495f68114bfe960b8182be4ab76b72043b2d0cc7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141664"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="5b657-102">방법: 작업에서 값 반환</span><span class="sxs-lookup"><span data-stu-id="5b657-102">How to: Return a Value from a Task</span></span>
<span data-ttu-id="5b657-103">다음 예제에서는 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> 형식을 사용하여 <xref:System.Threading.Tasks.Task%601.Result%2A> 속성의 값을 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b657-103">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="5b657-104">이 예제를 실행하려면 C:\Users\Public\Pictures\Sample Pictures\ 디렉터리가 있고 파일을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b657-104">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b657-105">예</span><span class="sxs-lookup"><span data-stu-id="5b657-105">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="5b657-106"><xref:System.Threading.Tasks.Task%601.Result%2A> 속성은 작업이 완료될 때까지 호출 스레드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="5b657-106">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="5b657-107">하나의 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> 결과를 연속 작업에 전달하는 방법을 보려면 [연속 작업을 사용하여 작업 연결](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b657-107">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b657-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b657-108">See also</span></span>

- [<span data-ttu-id="5b657-109">작업 기반 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="5b657-109">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
- [<span data-ttu-id="5b657-110">PLINQ 및 TPL의 람다 식</span><span class="sxs-lookup"><span data-stu-id="5b657-110">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
