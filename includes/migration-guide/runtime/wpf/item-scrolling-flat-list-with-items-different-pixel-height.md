---
ms.openlocfilehash: d23d7821e19b9d7f2db13a6bfdf868a8414cf721
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496876"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a><span data-ttu-id="68ef4-101">픽셀 높이가 다른 항목을 포함하는 단순 목록 항목 스크롤</span><span class="sxs-lookup"><span data-stu-id="68ef4-101">Item-scrolling a flat list with items of different pixel-height</span></span>

#### <a name="details"></a><span data-ttu-id="68ef4-102">설명</span><span class="sxs-lookup"><span data-stu-id="68ef4-102">Details</span></span>

<span data-ttu-id="68ef4-103"><xref:System.Windows.Controls.ItemsControl?displayProperty=fullName>이 가상화(<code>IsVirtualizing=true</code>) 및 항목 스크롤(<code>ScrollUnit=Item</code>)을 사용하여 컬렉션을 표시하고 해당 높이(픽셀)가 인접 항목과 다른 항목을 표시하기 위해 컨트롤이 스크롤되는 경우 <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>은 컬렉션의 모든 항목을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="68ef4-103">When an <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> displays a collection using virtualization (<code>IsVirtualizing=true</code>) and item- scrolling (<code>ScrollUnit=Item</code>), and when the control scrolls to display an item whose height in pixels differs from its neighbors, the <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> iterates over all items in the collection.</span></span> <span data-ttu-id="68ef4-104">이와 같은 반복 중에 UI는 응답하지 않습니다. 컬렉션의 크기가 큰 경우 중단으로 인식될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68ef4-104">The UI is unresponsive during this iteration; if the collection is large, this can be perceived as a hang.</span></span> <span data-ttu-id="68ef4-105">이 반복은 이전 .NET Framework 릴리스에서도 다른 상황에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="68ef4-105">The iteration occurs in other circumstances, even in previous .NET Framework releases.</span></span> <span data-ttu-id="68ef4-106">예를 들어 픽셀 높이가 다른 항목이 나타나는 경우 픽셀 스크롤할 때(<code>ScrollUnit=Pixel</code>) 및 하위 항목 수가 인접 항목과 다른 항목이 나타나는 경우 계층적 데이터를 항목 스크롤할 때(예: 그룹화가 사용되는 <xref:System.Windows.Controls.TreeView?displayProperty=fullName> 또는 <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName>) 발생합니다. 항목 스크롤을 사용하고 픽셀 높이가 다른 경우 계층 구조 데이터의 레이아웃에서 버그를 수정하기 위해 .NET Framework 4.6.1에 반복이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="68ef4-106">For example, it occurs when pixel-scrolling (<code>ScrollUnit=Pixel</code>) upon encountering an item with different pixel height, and when item-scrolling hierarchical data (such as a <xref:System.Windows.Controls.TreeView?displayProperty=fullName> or an <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> with grouping enabled) upon encountering an item with a different number of descendant items than its neighbors.For the case of item-scrolling and different pixel height, the iteration was introduced in .NET Framework 4.6.1 to fix bugs in the layout of hierarchical data.</span></span>  <span data-ttu-id="68ef4-107">데이터가 단일 구조(계층 구조 아님)인 경우 반복이 필요하지 않으며 이 경우 .NET Framework 4.6.2가 반복을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68ef4-107">It is not needed if the data is flat (no hierarchy), and .NET Framework 4.6.2 does not do it in that case.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="68ef4-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="68ef4-108">Suggestion</span></span>

<span data-ttu-id="68ef4-109">반복이 .NET Framework 4.6.1에서 발생하지만 이전 릴리스에서는 발생하지 않는 경우, 즉, <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName>이 항목의 픽셀 높이가 서로 다른 항목의 단순 목록을 항목 스크롤하는 경우 다음과 같은 두 가지 방법으로 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68ef4-109">If the iteration occurs in .NET Framework 4.6.1 but not in earlier releases - that is, if the <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> is item- scrolling a flat list with items of different pixel height - there are two remedies:</span></span><ol><li><span data-ttu-id="68ef4-110">.NET Framework 4.6.2를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="68ef4-110">Install .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="68ef4-111">.NET Framework 4.6.1용 핫픽스 HR 1605를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="68ef4-111">Install hotfix HR 1605 for .NET Framework 4.6.1.</span></span></li></ol>

| <span data-ttu-id="68ef4-112">이름</span><span class="sxs-lookup"><span data-stu-id="68ef4-112">Name</span></span>    | <span data-ttu-id="68ef4-113">값</span><span class="sxs-lookup"><span data-stu-id="68ef4-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="68ef4-114">Scope</span><span class="sxs-lookup"><span data-stu-id="68ef4-114">Scope</span></span>   |<span data-ttu-id="68ef4-115">부</span><span class="sxs-lookup"><span data-stu-id="68ef4-115">Minor</span></span>|
|<span data-ttu-id="68ef4-116">버전</span><span class="sxs-lookup"><span data-stu-id="68ef4-116">Version</span></span>|<span data-ttu-id="68ef4-117">4.6.1</span><span class="sxs-lookup"><span data-stu-id="68ef4-117">4.6.1</span></span>|
|<span data-ttu-id="68ef4-118">형식</span><span class="sxs-lookup"><span data-stu-id="68ef4-118">Type</span></span>|<span data-ttu-id="68ef4-119">런타임</span><span class="sxs-lookup"><span data-stu-id="68ef4-119">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="68ef4-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="68ef4-120">Affected APIs</span></span>

- <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.VirtualizingStackPanel`

-->
