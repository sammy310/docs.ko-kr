---
ms.openlocfilehash: 25ce391f917bd270d4d9a75f608e4a8ec763d15c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496491"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a><span data-ttu-id="eea85-101">Items.Clear는 SelectedItems에서 중복 항목을 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eea85-101">Items.Clear does not remove duplicates from SelectedItems</span></span>

#### <a name="details"></a><span data-ttu-id="eea85-102">설명</span><span class="sxs-lookup"><span data-stu-id="eea85-102">Details</span></span>

<span data-ttu-id="eea85-103">선택기(다중 항목 선택 가능)의 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> 컬렉션에 중복 항목이 있을 경우 동일한 항목이 두 번 이상 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="eea85-103">Suppose a Selector (with multiple selection enabled) has duplicates in its <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> collection - the same item appears more than once.</span></span>  <span data-ttu-id="eea85-104">데이터 소스에서 해당 항목을 제거하면(예: Items.Clear를 호출하여) <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> 컬렉션에서 제거할 수 없으며, 첫 번째 인스턴스만 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="eea85-104">Removing those items from the data source (e.g. by calling Items.Clear) fails to remove them from <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; only the first instance is removed.</span></span> <span data-ttu-id="eea85-105">또한 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>에 더 이상 데이터 소소에 없는 항목이 있기 때문에, <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>(예: SelectedItems.Clear())을 계속 사용하면 <xref:System.ArgumentException?displayProperty=fullName>과 같은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eea85-105">Furthermore, subsequent use of <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (e.g. SelectedItems.Clear()) can encounter problems such as <xref:System.ArgumentException?displayProperty=fullName>, because <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contains items that are no longer in the data source.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="eea85-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="eea85-106">Suggestion</span></span>

<span data-ttu-id="eea85-107">가능한 경우 .NET Framework 4.6.2로 업그레이드하세요.</span><span class="sxs-lookup"><span data-stu-id="eea85-107">Upgrade if possible to .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="eea85-108">이름</span><span class="sxs-lookup"><span data-stu-id="eea85-108">Name</span></span>    | <span data-ttu-id="eea85-109">값</span><span class="sxs-lookup"><span data-stu-id="eea85-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="eea85-110">Scope</span><span class="sxs-lookup"><span data-stu-id="eea85-110">Scope</span></span>   |<span data-ttu-id="eea85-111">부</span><span class="sxs-lookup"><span data-stu-id="eea85-111">Minor</span></span>|
|<span data-ttu-id="eea85-112">버전</span><span class="sxs-lookup"><span data-stu-id="eea85-112">Version</span></span>|<span data-ttu-id="eea85-113">4.5</span><span class="sxs-lookup"><span data-stu-id="eea85-113">4.5</span></span>|
|<span data-ttu-id="eea85-114">형식</span><span class="sxs-lookup"><span data-stu-id="eea85-114">Type</span></span>|<span data-ttu-id="eea85-115">런타임</span><span class="sxs-lookup"><span data-stu-id="eea85-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="eea85-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="eea85-116">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.MultiSelector.SelectedItems`

-->
