---
ms.openlocfilehash: 7ac0cac53ab2fa7657d0ae58f11d9e777631acc9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620439"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="edb5d-101">DataGrid의 UnloadingRow 이벤트 처리기에서 WPF DataGrid의 선택된 항목에 액세스하면 NullReferenceException이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb5d-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="edb5d-102">설명</span><span class="sxs-lookup"><span data-stu-id="edb5d-102">Details</span></span>

<span data-ttu-id="edb5d-103">.NET Framework 4.5의 버그로 인해 행 제거와 관련된 <xref:System.Windows.Controls.DataGrid> 이벤트의 이벤트 처리기는 <xref:System.Windows.Controls.DataGrid>의 <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> 또는 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> 속성에 액세스하는 경우 <xref:System.NullReferenceException?displayProperty=fullName>이 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb5d-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=fullName> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> properties.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="edb5d-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="edb5d-104">Suggestion</span></span>

<span data-ttu-id="edb5d-105">이 문제는 .NET Framework 4.6에서 해결되었으며, 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb5d-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="edb5d-106">이름</span><span class="sxs-lookup"><span data-stu-id="edb5d-106">Name</span></span>    | <span data-ttu-id="edb5d-107">값</span><span class="sxs-lookup"><span data-stu-id="edb5d-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="edb5d-108">Scope</span><span class="sxs-lookup"><span data-stu-id="edb5d-108">Scope</span></span>   |<span data-ttu-id="edb5d-109">부</span><span class="sxs-lookup"><span data-stu-id="edb5d-109">Minor</span></span>|
|<span data-ttu-id="edb5d-110">버전</span><span class="sxs-lookup"><span data-stu-id="edb5d-110">Version</span></span>|<span data-ttu-id="edb5d-111">4.5</span><span class="sxs-lookup"><span data-stu-id="edb5d-111">4.5</span></span>|
|<span data-ttu-id="edb5d-112">형식</span><span class="sxs-lookup"><span data-stu-id="edb5d-112">Type</span></span>|<span data-ttu-id="edb5d-113">런타임</span><span class="sxs-lookup"><span data-stu-id="edb5d-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="edb5d-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="edb5d-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
