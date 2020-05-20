---
ms.openlocfilehash: cda5df4b673412a7c8c59f80f89c19c13dc81dc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858836"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="a768e-101">DataGrid의 UnloadingRow 이벤트 처리기에서 WPF DataGrid의 선택된 항목에 액세스하면 NullReferenceException이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a768e-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a768e-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a768e-102">Details</span></span>|<span data-ttu-id="a768e-103">.NET Framework 4.5의 버그로 인해 행 제거와 관련된 <xref:System.Windows.Controls.DataGrid> 이벤트의 이벤트 처리기는 <xref:System.Windows.Controls.DataGrid>의 <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> 또는 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> 속성에 액세스하는 경우 <xref:System.NullReferenceException?displayProperty=name>이 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a768e-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=name> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> properties.</span></span>|
|<span data-ttu-id="a768e-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a768e-104">Suggestion</span></span>|<span data-ttu-id="a768e-105">이 문제는 .NET Framework 4.6에서 해결되었으며, 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a768e-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="a768e-106">범위</span><span class="sxs-lookup"><span data-stu-id="a768e-106">Scope</span></span>|<span data-ttu-id="a768e-107">사소함</span><span class="sxs-lookup"><span data-stu-id="a768e-107">Minor</span></span>|
|<span data-ttu-id="a768e-108">Version</span><span class="sxs-lookup"><span data-stu-id="a768e-108">Version</span></span>|<span data-ttu-id="a768e-109">4.5</span><span class="sxs-lookup"><span data-stu-id="a768e-109">4.5</span></span>|
|<span data-ttu-id="a768e-110">형식</span><span class="sxs-lookup"><span data-stu-id="a768e-110">Type</span></span>|<span data-ttu-id="a768e-111">런타임</span><span class="sxs-lookup"><span data-stu-id="a768e-111">Runtime</span></span>|
|<span data-ttu-id="a768e-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a768e-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
