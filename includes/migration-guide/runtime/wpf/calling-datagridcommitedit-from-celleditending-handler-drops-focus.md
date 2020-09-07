---
ms.openlocfilehash: c78122a2fe69c78625d6cb7fa9ddf41c49c2e737
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496884"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="9b609-101">CellEditEnding 처리기에서 DataGrid.CommitEdit를 호출하면 포커스가 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="9b609-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

#### <a name="details"></a><span data-ttu-id="9b609-102">설명</span><span class="sxs-lookup"><span data-stu-id="9b609-102">Details</span></span>

<span data-ttu-id="9b609-103"><xref:System.Windows.Controls.DataGrid?displayProperty=fullName>의 <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> 이벤트 처리기 중 하나에서 <xref:System.Windows.Controls.DataGrid.CommitEdit>을 호출하면 <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>가 포커스를 잃게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b609-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> to lose focus.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9b609-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="9b609-104">Suggestion</span></span>

<span data-ttu-id="9b609-105">이 버그는 .NET Framework 4.5.2에서 수정되었으므로 .NET Framework를 업그레이드하여 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b609-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="9b609-106">또는 <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>을 호출한 후에 <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>을 명시적으로 다시 선택하여 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b609-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span></span>

| <span data-ttu-id="9b609-107">이름</span><span class="sxs-lookup"><span data-stu-id="9b609-107">Name</span></span>    | <span data-ttu-id="9b609-108">값</span><span class="sxs-lookup"><span data-stu-id="9b609-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9b609-109">Scope</span><span class="sxs-lookup"><span data-stu-id="9b609-109">Scope</span></span>   |<span data-ttu-id="9b609-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9b609-110">Edge</span></span>|
|<span data-ttu-id="9b609-111">버전</span><span class="sxs-lookup"><span data-stu-id="9b609-111">Version</span></span>|<span data-ttu-id="9b609-112">4.5</span><span class="sxs-lookup"><span data-stu-id="9b609-112">4.5</span></span>|
|<span data-ttu-id="9b609-113">형식</span><span class="sxs-lookup"><span data-stu-id="9b609-113">Type</span></span>|<span data-ttu-id="9b609-114">런타임</span><span class="sxs-lookup"><span data-stu-id="9b609-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="9b609-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="9b609-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.CommitEdit`
- `M:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)`

-->
