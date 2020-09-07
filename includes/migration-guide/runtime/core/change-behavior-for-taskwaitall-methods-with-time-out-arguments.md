---
ms.openlocfilehash: 9d0791f00db7d830fc5d327af30218a0bbfcb25f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497260"
---
### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a><span data-ttu-id="27b10-101">제한 시간 인수가 있는 Task.WaitAll 메서드에 대한 동작 변경</span><span class="sxs-lookup"><span data-stu-id="27b10-101">Change in behavior for Task.WaitAll methods with time-out arguments</span></span>

#### <a name="details"></a><span data-ttu-id="27b10-102">설명</span><span class="sxs-lookup"><span data-stu-id="27b10-102">Details</span></span>

<span data-ttu-id="27b10-103">.NET Framework 4.5에서 <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> 동작의 일관성이 높아졌습니다. .NET Framework 4에서는 이러한 메서드가 일관되지 않게 동작했었습니다.</span><span class="sxs-lookup"><span data-stu-id="27b10-103"><xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> behavior was made more consistent in .NET Framework 4.5.In the .NET Framework 4, these methods behaved inconsistently.</span></span> <span data-ttu-id="27b10-104">제한 시간이 만료되고 메서드 호출 전에 하나 이상의 작업이 완료되거나 취소되면 이 메서드는 <xref:System.AggregateException?displayProperty=fullName> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="27b10-104">When the time-out expired, if one or more tasks were completed or canceled before the method call, the method threw an <xref:System.AggregateException?displayProperty=fullName> exception.</span></span> <span data-ttu-id="27b10-105">제한 시간이 만료되고 메서드 호출 전에 완료되거나 취소된 작업은 없지만 메서드 호출 후에 하나 이상의 작업이 완료되거나 취소되면 이 메서드는 false를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="27b10-105">When the time-out expired, if no tasks were completed or canceled before the method call, but one or more tasks entered these states after the method call, the method returned false.</span></span><br/><br/><span data-ttu-id="27b10-106">.NET Framework 4.5에서, 시간 제한 간격이 만료될 때 모든 작업이 아직 실행되고 있는 경우 이러한 메서드 오버로드에서 이제 false를 반환하고, 입력 작업이 취소되고(메서드 호출 전후 여부와 상관없이) 다른 작업이 실행되고 있지 않은 경우에만 <xref:System.AggregateException?displayProperty=fullName> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="27b10-106">In the .NET Framework 4.5, these method overloads now return false if any tasks are still running when the time-out interval expired, and they throw an <xref:System.AggregateException?displayProperty=fullName> exception only if an input task was cancelled (regardless of whether it was before or after the method call) and no other tasks are still running.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="27b10-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="27b10-107">Suggestion</span></span>

<span data-ttu-id="27b10-108">.NET Framework 4.6은 대기된 모든 작업이 시간 제한 전에 완료되어야 throw하기 때문에 <xref:System.Threading.Tasks.Task.WaitAll%2A>이 호출되기 전에 취소된 작업을 탐지하는 방법으로 <xref:System.AggregateException?displayProperty=fullName>이 catch된 경우 해당 코드는 대신 <xref:System.Threading.Tasks.Task.IsCanceled%2A> 속성(예: .Any(t = &gt; t.IsCanceled))을 통해 동일한 탐지를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27b10-108">If an <xref:System.AggregateException?displayProperty=fullName> was being caught as a means of detecting a task that was cancelled prior to the <xref:System.Threading.Tasks.Task.WaitAll%2A> call being invoked, that code should instead do the same detection via the  <xref:System.Threading.Tasks.Task.IsCanceled%2A> property (for example: .Any(t =&gt; t.IsCanceled)) since .NET Framework 4.6 will only throw in that case if all awaited tasks are completed prior to the timeout.</span></span>

| <span data-ttu-id="27b10-109">이름</span><span class="sxs-lookup"><span data-stu-id="27b10-109">Name</span></span>    | <span data-ttu-id="27b10-110">값</span><span class="sxs-lookup"><span data-stu-id="27b10-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="27b10-111">Scope</span><span class="sxs-lookup"><span data-stu-id="27b10-111">Scope</span></span>   |<span data-ttu-id="27b10-112">부</span><span class="sxs-lookup"><span data-stu-id="27b10-112">Minor</span></span>|
|<span data-ttu-id="27b10-113">버전</span><span class="sxs-lookup"><span data-stu-id="27b10-113">Version</span></span>|<span data-ttu-id="27b10-114">4.5</span><span class="sxs-lookup"><span data-stu-id="27b10-114">4.5</span></span>|
|<span data-ttu-id="27b10-115">형식</span><span class="sxs-lookup"><span data-stu-id="27b10-115">Type</span></span>|<span data-ttu-id="27b10-116">런타임</span><span class="sxs-lookup"><span data-stu-id="27b10-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="27b10-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="27b10-117">Affected APIs</span></span>

- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)`

-->
