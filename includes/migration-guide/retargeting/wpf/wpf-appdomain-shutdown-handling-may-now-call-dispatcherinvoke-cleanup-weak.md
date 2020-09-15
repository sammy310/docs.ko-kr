---
ms.openlocfilehash: 8b804d23247b95381f3ff83bc12c32215a420fb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614960"
---
### <a name="wpf-appdomain-shutdown-handling-may-now-call-dispatcherinvoke-in-cleanup-of-weak-events"></a><span data-ttu-id="5f1a7-101">WPF AppDomain 종료 처리가 이제 약한 이벤트 정리에서 Dispatcher.Invoke를 호출할 수 있음</span><span class="sxs-lookup"><span data-stu-id="5f1a7-101">WPF AppDomain Shutdown Handling May Now Call Dispatcher.Invoke in Cleanup of Weak Events</span></span>

#### <a name="details"></a><span data-ttu-id="5f1a7-102">설명</span><span class="sxs-lookup"><span data-stu-id="5f1a7-102">Details</span></span>

<span data-ttu-id="5f1a7-103">.NET Framework 4.7.1 이전 버전에서 WPF는 잠재적으로 AppDomain 종료 중에 .NET 종료자 스레드에 대한 <xref:System.Windows.Threading.Dispatcher?displayProperty=nameWithType>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f1a7-103">In .NET Framework 4.7.1 and earlier versions, WPF potentially creates a <xref:System.Windows.Threading.Dispatcher?displayProperty=nameWithType> on the .NET finalizer thread during AppDomain shutdown.</span></span>  <span data-ttu-id="5f1a7-104">이 문제는 .NET Framework 4.7.2 이상 버전에서 스레드 인식되는 약한 이벤트를 정리하여 수정했습니다.</span><span class="sxs-lookup"><span data-stu-id="5f1a7-104">This was fixed in .NET Framework 4.7.2 and later versions by making the cleanup of weak events thread-aware.</span></span>  <span data-ttu-id="5f1a7-105">이로 인해 WPF는 <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType>를 호출하여 정리 프로세스를 완료할 수도 있습니다. 특정 애플리케이션에는 이러한 종료자 타이밍 변경으로 인해 잠재적으로 AppDomain 또는 프로세스 종료 중에 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f1a7-105">Due to this, WPF may call <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> to complete the cleanup process.In certain applications, this change in finalizer timing can potentially cause exceptions during AppDomain or process shutdown.</span></span>  <span data-ttu-id="5f1a7-106">이런 현상은 일반적으로 프로세스 또는 AppDomain 종료 전에 작업자 스레드에서 실행되는 디스패처를 올바르게 종료하지 않는 애플리케이션에서 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5f1a7-106">This is generally seen in applications that do not correctly shut down dispatchers running on worker threads prior to process or AppDomain shutdown.</span></span>  <span data-ttu-id="5f1a7-107">이러한 애플리케이션은 주의하여 디스패처 수명을 올바르게 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f1a7-107">Such applications should take care to properly manage the lifetime of dispatchers.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5f1a7-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="5f1a7-108">Suggestion</span></span>

<span data-ttu-id="5f1a7-109">.NET Framework 4.7.2 이상 버전에서 개발자는 정리 변경으로 인해 발생할 수 있는 타이밍 문제를 완화(제거하지는 않음)하는 데 도움이 되도록 이 수정을 사용하지 않도록 설정할 수 있습니다. 정리에서 이 변경을 사용하지 않도록 설정하려면 다음 AppContext 플래그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f1a7-109">In .NET Framework 4.7.2 and later versions, developers can disable this fix in order to help alleviate (but not eliminate) timing issues that may occur due to the cleanup change.To disable the change in cleanup, use the following AppContext flag.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotInvokeInWeakEventTableShutdownListener=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="5f1a7-110">이름</span><span class="sxs-lookup"><span data-stu-id="5f1a7-110">Name</span></span>    | <span data-ttu-id="5f1a7-111">값</span><span class="sxs-lookup"><span data-stu-id="5f1a7-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5f1a7-112">Scope</span><span class="sxs-lookup"><span data-stu-id="5f1a7-112">Scope</span></span>   | <span data-ttu-id="5f1a7-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5f1a7-113">Edge</span></span>        |
| <span data-ttu-id="5f1a7-114">버전</span><span class="sxs-lookup"><span data-stu-id="5f1a7-114">Version</span></span> | <span data-ttu-id="5f1a7-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="5f1a7-115">4.7.2</span></span>       |
| <span data-ttu-id="5f1a7-116">형식</span><span class="sxs-lookup"><span data-stu-id="5f1a7-116">Type</span></span>    | <span data-ttu-id="5f1a7-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="5f1a7-117">Retargeting</span></span> |
