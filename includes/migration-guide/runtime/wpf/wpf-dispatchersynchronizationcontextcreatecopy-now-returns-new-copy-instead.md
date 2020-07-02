---
ms.openlocfilehash: fc6066fd0b23d299158114cb397934041b99ba47
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620463"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a><span data-ttu-id="b383b-101">이제 WPF DispatcherSynchronizationContext.CreateCopy는 현재 인스턴스 대신 새 복사본을 반환</span><span class="sxs-lookup"><span data-stu-id="b383b-101">WPF DispatcherSynchronizationContext.CreateCopy now returns a new copy instead of the current instance</span></span>

#### <a name="details"></a><span data-ttu-id="b383b-102">설명</span><span class="sxs-lookup"><span data-stu-id="b383b-102">Details</span></span>

<span data-ttu-id="b383b-103">.NET Framework 4에서 <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy>는 주로 성능 최적화로서 현재 인스턴스에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b383b-103">In the .NET Framework 4, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> returned a reference to the current instance, primarily as a performance optimization.</span></span> <span data-ttu-id="b383b-104">.NET Framework 4.5에서는 처음으로 동일한 참조가 실행 스레드를 올바른 동기화 컨텍스트에 나타내도록 마무리하는 것을 가능하게 하는 새 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b383b-104">In the .NET Framework 4.5, it returns a new instance which makes it possible for the first time to conclude that equal references indicate the executing thread is in the correct synchronization context.</span></span>  <span data-ttu-id="b383b-105">이러한 참조의 ID를 확인하는 코드가 영향을 받기는 어렵지만, 변경 내용 때문에 <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy>를 호출하는 코드는 .NET Framework 4.5 이상으로의 마이그레이션 과정에서 테스트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b383b-105">It is unlikely that code that checks the identity of these references will be affected, but because of the change, code that calls <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> should be tested as part of migration to the .NET Framework 4.5 or newer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b383b-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="b383b-106">Suggestion</span></span>

<span data-ttu-id="b383b-107"><xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy>는 새로운 <xref:System.Threading.SynchronizationContext?displayProperty=fullName> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b383b-107">Be aware that <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> will now return a new <xref:System.Threading.SynchronizationContext?displayProperty=fullName> object.</span></span> <span data-ttu-id="b383b-108">이전에는 이러한 방식으로 생성된 참조의 동등성을 사용한 코드는 적절한 컨텍스트에 있는지 실제로 확인되지 않았지만 .NET Framework 4.5 이상에 대해 빌드할 때는 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="b383b-108">Previously, code that used equivalence of references generated this way was not actually checking whether it was in the proper context, but does when built against .NET Framework 4.5 or later.</span></span>  <span data-ttu-id="b383b-109">문제가 발생할 가능성은 작지만 발생하는 경우 영향을 받은 코드 경로를 실행하는 것으로 확인하기에 충분할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b383b-109">While unlikely to cause issues, exercising the affected code paths should be enough to determine if this poses any problem.</span></span>

| <span data-ttu-id="b383b-110">이름</span><span class="sxs-lookup"><span data-stu-id="b383b-110">Name</span></span>    | <span data-ttu-id="b383b-111">값</span><span class="sxs-lookup"><span data-stu-id="b383b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b383b-112">Scope</span><span class="sxs-lookup"><span data-stu-id="b383b-112">Scope</span></span>   |<span data-ttu-id="b383b-113">부</span><span class="sxs-lookup"><span data-stu-id="b383b-113">Minor</span></span>|
|<span data-ttu-id="b383b-114">버전</span><span class="sxs-lookup"><span data-stu-id="b383b-114">Version</span></span>|<span data-ttu-id="b383b-115">4.5</span><span class="sxs-lookup"><span data-stu-id="b383b-115">4.5</span></span>|
|<span data-ttu-id="b383b-116">형식</span><span class="sxs-lookup"><span data-stu-id="b383b-116">Type</span></span>|<span data-ttu-id="b383b-117">런타임</span><span class="sxs-lookup"><span data-stu-id="b383b-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b383b-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="b383b-118">Affected APIs</span></span>

-<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType></li></ul>|
