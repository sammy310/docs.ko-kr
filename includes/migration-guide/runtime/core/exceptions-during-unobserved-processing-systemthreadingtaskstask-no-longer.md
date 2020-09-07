---
ms.openlocfilehash: bae211e5684dc1fbbb1d7e69c928e37c1c532096
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497736"
---
### <a name="exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a><span data-ttu-id="bd4a1-101">System.Threading.Tasks.Task의 관찰되지 않은 처리 중에 예외는 더 이상 종료자 스레드를 전파하지 않습니다</span><span class="sxs-lookup"><span data-stu-id="bd4a1-101">Exceptions during unobserved processing in System.Threading.Tasks.Task no longer propagate on finalizer thread</span></span>

#### <a name="details"></a><span data-ttu-id="bd4a1-102">설명</span><span class="sxs-lookup"><span data-stu-id="bd4a1-102">Details</span></span>

<span data-ttu-id="bd4a1-103"><xref:System.Threading.Tasks.Task?displayProperty=fullName> 클래스는 비동기 작업을 나타내기 때문에 비동기 처리를 하는 동안 발생하는 심각하지 않은 예외를 모두 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4a1-103">Because the <xref:System.Threading.Tasks.Task?displayProperty=fullName> class represents an asynchronous operation, it catches all non-severe exceptions that occur during asynchronous processing.</span></span> <span data-ttu-id="bd4a1-104">.NET Framework 4.5에서는 예외가 관찰되지 않고 코드가 작업에서 대기하지 않으면 예외는 더 이상 종료자 스레드에서 전파되지 않고 가비지 수집 도중 프로세스와 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4a1-104">In the .NET Framework 4.5, if an exception is not observed and your code never waits on the task, the exception will no longer propagate on the finalizer thread and crash the process during garbage collection.</span></span> <span data-ttu-id="bd4a1-105">이러한 변경으로 인해 관찰되지 않은 비동기 처리를 수행하기 위해 Task 클래스를 사용하는 애플리케이션의 안정성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd4a1-105">This change enhances the reliability of applications that use the Task class to perform unobserved asynchronous processing.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bd4a1-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="bd4a1-106">Suggestion</span></span>

<span data-ttu-id="bd4a1-107">응용 프로그램이 종료자 스레드를 전파하는 관찰되지 않은 비동기 예외에 종속되는 경우 이전의 동작을 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> 이벤트에 대한 적절한 처리기를 제공하거나 [런타임 구성 요소](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)를 설정하여 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd4a1-107">If an app depends on unobserved asynchronous exceptions propagating to the finalizer thread, the previous behavior can be restored by providing an appropriate handler for the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event, or by setting a [runtime configuration element](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).</span></span>

| <span data-ttu-id="bd4a1-108">이름</span><span class="sxs-lookup"><span data-stu-id="bd4a1-108">Name</span></span>    | <span data-ttu-id="bd4a1-109">값</span><span class="sxs-lookup"><span data-stu-id="bd4a1-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bd4a1-110">Scope</span><span class="sxs-lookup"><span data-stu-id="bd4a1-110">Scope</span></span>   |<span data-ttu-id="bd4a1-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bd4a1-111">Edge</span></span>|
|<span data-ttu-id="bd4a1-112">버전</span><span class="sxs-lookup"><span data-stu-id="bd4a1-112">Version</span></span>|<span data-ttu-id="bd4a1-113">4.5</span><span class="sxs-lookup"><span data-stu-id="bd4a1-113">4.5</span></span>|
|<span data-ttu-id="bd4a1-114">형식</span><span class="sxs-lookup"><span data-stu-id="bd4a1-114">Type</span></span>|<span data-ttu-id="bd4a1-115">런타임</span><span class="sxs-lookup"><span data-stu-id="bd4a1-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="bd4a1-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="bd4a1-116">Affected APIs</span></span>

- <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600},System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}},System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Start?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Threading.Tasks.Task.Run(System.Action)`
- `M:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)`
- `M:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})`
- `M:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)`
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{``0})``
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{``0},System.Threading.CancellationToken)``
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{System.Threading.Tasks.Task{``0}})``
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{System.Threading.Tasks.Task{``0}},System.Threading.CancellationToken)``
- `M:System.Threading.Tasks.Task.Start`
- `M:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)`

-->
