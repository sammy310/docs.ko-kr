---
ms.openlocfilehash: 06c699281c8890ac65be1d282b72b54774acc280
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620475"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a><span data-ttu-id="f6f66-101">WPF DataTemplate 요소가 UIA에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6f66-101">WPF DataTemplate elements are now visible to UIA</span></span>

#### <a name="details"></a><span data-ttu-id="f6f66-102">설명</span><span class="sxs-lookup"><span data-stu-id="f6f66-102">Details</span></span>

<span data-ttu-id="f6f66-103">이전에는 <xref:System.Windows.DataTemplate?displayProperty=fullName> 요소가 UI 자동화에 표시되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f6f66-103">Previously, <xref:System.Windows.DataTemplate?displayProperty=fullName> elements were invisible to UI Automation.</span></span> <span data-ttu-id="f6f66-104">4\.5부터는 UI 자동화가 이러한 요소를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f66-104">Beginning in 4.5, UI Automation will detect these elements.</span></span> <span data-ttu-id="f6f66-105">이것은 대부분의 사례에 유용하지만 <xref:System.Windows.DataTemplate?displayProperty=fullName> 요소를 포함하지 않는 UIA 트리에 의존하는 테스트를 중단시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6f66-105">This is useful in many cases, but can break tests that depend on UIA trees not containing <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f6f66-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="f6f66-106">Suggestion</span></span>

<span data-ttu-id="f6f66-107">이 응용 프로그램에 대한 UI 자동화 테스트는 이전에 보이지 않던 <xref:System.Windows.DataTemplate?displayProperty=fullName> 요소를 포함하는 UIA 트리에 대해 업데이트가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6f66-107">UI Automation tests for this app may need updated to account for the UIA tree now including previously invisible <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span> <span data-ttu-id="f6f66-108">예를 들어 일부 요소가 서로 옆에 있도록 예상하는 테스트는 이제 이전에 요소 간에 보이지 않던 UIA 요소를 예상해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6f66-108">For example, tests that expect some elements to be next to each other may now need to expect previously invisible UIA elements in between.</span></span> <span data-ttu-id="f6f66-109">또는 UIA 요소에 대한 특정 개수 또는 인덱스를 사용하는 테스트는 새 값으로 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6f66-109">Or tests that rely on certain counts or indexes for UIA elements may need updated with new values.</span></span>

| <span data-ttu-id="f6f66-110">이름</span><span class="sxs-lookup"><span data-stu-id="f6f66-110">Name</span></span>    | <span data-ttu-id="f6f66-111">값</span><span class="sxs-lookup"><span data-stu-id="f6f66-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f6f66-112">Scope</span><span class="sxs-lookup"><span data-stu-id="f6f66-112">Scope</span></span>   |<span data-ttu-id="f6f66-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f6f66-113">Edge</span></span>|
|<span data-ttu-id="f6f66-114">버전</span><span class="sxs-lookup"><span data-stu-id="f6f66-114">Version</span></span>|<span data-ttu-id="f6f66-115">4.5</span><span class="sxs-lookup"><span data-stu-id="f6f66-115">4.5</span></span>|
|<span data-ttu-id="f6f66-116">형식</span><span class="sxs-lookup"><span data-stu-id="f6f66-116">Type</span></span>|<span data-ttu-id="f6f66-117">런타임</span><span class="sxs-lookup"><span data-stu-id="f6f66-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f6f66-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f6f66-118">Affected APIs</span></span>

-<xref:System.Windows.DataTemplate.%23ctor></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)></li></ul>|
