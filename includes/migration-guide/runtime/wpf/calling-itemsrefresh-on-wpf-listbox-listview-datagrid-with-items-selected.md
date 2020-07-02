---
ms.openlocfilehash: 710d1517397f423fa40cc0c4a26c3499aac6179e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620420"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a><span data-ttu-id="2a31b-101">항목이 선택된 WPF ListBox, ListView, 또는 DataGrid에서 Items.Refresh를 호출하면 요소에 중복 항목이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a31b-101">Calling Items.Refresh on a WPF ListBox, ListView, or DataGrid with items selected can cause duplicate items to appear in the element</span></span>

#### <a name="details"></a><span data-ttu-id="2a31b-102">설명</span><span class="sxs-lookup"><span data-stu-id="2a31b-102">Details</span></span>

<span data-ttu-id="2a31b-103">.NET Framework 4.5에서 항목이 <xref:System.Windows.Controls.ListBox?displayProperty=fullName>에 선택되어 있을 때 ListBox.Items.Refresh 코드를 호출하면 선택된 항목이 목록에 중복될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a31b-103">In the .NET Framework 4.5, calling ListBox.Items.Refresh from code while items are selected in a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> can cause the selected items to be duplicated in the list.</span></span> <span data-ttu-id="2a31b-104">유사한 문제가 <xref:System.Windows.Controls.ListView?displayProperty=fullName> 및 <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2a31b-104">A similar issue occurs with <xref:System.Windows.Controls.ListView?displayProperty=fullName> and <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>.</span></span> <span data-ttu-id="2a31b-105">이것은 .NET Framework 4.6에서 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2a31b-105">This is fixed in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2a31b-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="2a31b-106">Suggestion</span></span>

<span data-ttu-id="2a31b-107">이 문제는 <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>를 호출하기 전에 프로그래밍 방식으로 항목 선택을 취소하고 호출이 완료된 후에 다시 선택하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a31b-107">This issue may be worked around by programmatically unselecting items before <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> is called and then re-selecting them after the call is completed.</span></span> <span data-ttu-id="2a31b-108">또는 .NET Framework 4.6에서 이 문제가 수정되어 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a31b-108">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="2a31b-109">이름</span><span class="sxs-lookup"><span data-stu-id="2a31b-109">Name</span></span>    | <span data-ttu-id="2a31b-110">값</span><span class="sxs-lookup"><span data-stu-id="2a31b-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2a31b-111">Scope</span><span class="sxs-lookup"><span data-stu-id="2a31b-111">Scope</span></span>   |<span data-ttu-id="2a31b-112">부</span><span class="sxs-lookup"><span data-stu-id="2a31b-112">Minor</span></span>|
|<span data-ttu-id="2a31b-113">버전</span><span class="sxs-lookup"><span data-stu-id="2a31b-113">Version</span></span>|<span data-ttu-id="2a31b-114">4.5</span><span class="sxs-lookup"><span data-stu-id="2a31b-114">4.5</span></span>|
|<span data-ttu-id="2a31b-115">형식</span><span class="sxs-lookup"><span data-stu-id="2a31b-115">Type</span></span>|<span data-ttu-id="2a31b-116">런타임</span><span class="sxs-lookup"><span data-stu-id="2a31b-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2a31b-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="2a31b-117">Affected APIs</span></span>

-<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|
