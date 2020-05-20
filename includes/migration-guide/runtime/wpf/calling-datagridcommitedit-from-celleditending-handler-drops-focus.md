---
ms.openlocfilehash: e2d63d85adce64db6e00b62ec17f55ae71ce3052
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803274"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="deb93-101">CellEditEnding 처리기에서 DataGrid.CommitEdit를 호출하면 포커스가 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="deb93-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

|   |   |
|---|---|
|<span data-ttu-id="deb93-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="deb93-102">Details</span></span>|<span data-ttu-id="deb93-103"><xref:System.Windows.Controls.DataGrid?displayProperty=name>의 <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> 이벤트 처리기 중 하나에서 <xref:System.Windows.Controls.DataGrid.CommitEdit>을 호출하면 <xref:System.Windows.Controls.DataGrid?displayProperty=name>가 포커스를 잃게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="deb93-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=name>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=name> to lose focus.</span></span>|
|<span data-ttu-id="deb93-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="deb93-104">Suggestion</span></span>|<span data-ttu-id="deb93-105">이 버그는 .NET Framework 4.5.2에서 수정되었으므로 .NET Framework를 업그레이드하여 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb93-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="deb93-106">또는 <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>을 호출한 후에 <xref:System.Windows.Controls.DataGrid?displayProperty=name>을 명시적으로 다시 선택하여 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb93-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=name> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>.</span></span>|
|<span data-ttu-id="deb93-107">범위</span><span class="sxs-lookup"><span data-stu-id="deb93-107">Scope</span></span>|<span data-ttu-id="deb93-108">가장자리</span><span class="sxs-lookup"><span data-stu-id="deb93-108">Edge</span></span>|
|<span data-ttu-id="deb93-109">Version</span><span class="sxs-lookup"><span data-stu-id="deb93-109">Version</span></span>|<span data-ttu-id="deb93-110">4.5</span><span class="sxs-lookup"><span data-stu-id="deb93-110">4.5</span></span>|
|<span data-ttu-id="deb93-111">형식</span><span class="sxs-lookup"><span data-stu-id="deb93-111">Type</span></span>|<span data-ttu-id="deb93-112">런타임</span><span class="sxs-lookup"><span data-stu-id="deb93-112">Runtime</span></span>|
|<span data-ttu-id="deb93-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="deb93-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
