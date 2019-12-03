---
ms.openlocfilehash: add3ff8faed2e7fab245e5b6f1b9158b7bdd06f5
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567360"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a><span data-ttu-id="27b19-101">도구 설명이 표시되면 CellFormatting 이벤트가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27b19-101">CellFormatting event not raised if tooltip is shown</span></span>

<span data-ttu-id="27b19-102">이제 마우스로 가리키는 경우와 키보드를 통해 선택하는 경우 <xref:System.Windows.Forms.DataGridView>에 셀 텍스트 및 오류의 도구 설명이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b19-102">A <xref:System.Windows.Forms.DataGridView> now shows a cell's text and error tooltips when hovered by a mouse and when selected via the keyboard.</span></span> <span data-ttu-id="27b19-103">도구 설명이 표시되는 경우 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 이벤트는 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27b19-103">If a tooltip is shown, the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event is not raised.</span></span>

#### <a name="change-description"></a><span data-ttu-id="27b19-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="27b19-104">Change description</span></span>

<span data-ttu-id="27b19-105">.NET Core 3.1 이전에는, 셀을 마우스로 가리킬 때 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> 속성이 `true`(으)로 설정된 <xref:System.Windows.Forms.DataGridView>에서 셀 텍스트 및 오류에 대한 도구 설명이 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27b19-105">Prior to .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that had the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` showed a tooltip for a cell's text and errors when the cell was hovered by a mouse.</span></span> <span data-ttu-id="27b19-106">키보드에서 셀을 선택한 경우(예: Tab 키, 바로 가기 키 또는 화살표 탐색 사용) 도구 설명이 표시되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="27b19-106">Tooltips were not shown when a cell was selected via the keyboard (for example, by using the Tab key, shortcut keys, or arrow navigation).</span></span> <span data-ttu-id="27b19-107">사용자가 셀을 편집한 후 <xref:System.Windows.Forms.DataGridView>이(가) 아직 편집 모드 상태인 동안 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> 속성이 설정되지 않은 셀을 마우스로 가리키는 경우, <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트가 발생하여 셀에 표시할 셀 텍스트의 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27b19-107">If the user edited a cell, and then, while the <xref:System.Windows.Forms.DataGridView> was still in edit mode, hovered over a cell that did not have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set, a <xref:System.Windows.Forms.DataGridView.CellFormatting> event was raised to format the cell's text for display in the cell.</span></span>

<span data-ttu-id="27b19-108">.NET Core 3.1부터 접근성 표준을 충족하기 위해, <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> 속성이 `true`(으)로 설정된 <xref:System.Windows.Forms.DataGridView>에서 셀을 가리킬 때뿐 아니라, 키보드에서 선택한 경우에도 셀 텍스트 및 오류의 도구 설명이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b19-108">To meet accessibility standards, starting in .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that has the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` shows tooltips for a cell's text and errors not only when the cell is hovered, but also when it's selected via the keyboard.</span></span> <span data-ttu-id="27b19-109">이 변경으로 인해 <xref:System.Windows.Forms.DataGridView>이(가) 편집 모드에 있는 동안 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> 속성이 설정되지 않은 셀을 가리키는 경우에는 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트가 발생되지 *않습니다*.</span><span class="sxs-lookup"><span data-stu-id="27b19-109">As a consequence of this change, the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is *not* raised when cells that don't have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set are hovered while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span> <span data-ttu-id="27b19-110">가리킨 셀의 내용이 셀에 표시되지 않고 도구 설명으로 표시되므로 이 이벤트가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27b19-110">The event is not raised because the content of the hovered cell is shown as a tooltip instead of being displayed in the cell.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="27b19-111">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="27b19-111">Version introduced</span></span>

<span data-ttu-id="27b19-112">3.1</span><span class="sxs-lookup"><span data-stu-id="27b19-112">3.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="27b19-113">권장 작업</span><span class="sxs-lookup"><span data-stu-id="27b19-113">Recommended action</span></span>

<span data-ttu-id="27b19-114"><xref:System.Windows.Forms.DataGridView>이(가) 편집 모드에 있는 동안 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트에 종속된 모든 코드를 리팩터링합니다.</span><span class="sxs-lookup"><span data-stu-id="27b19-114">Refactor any code that depends on the <xref:System.Windows.Forms.DataGridView.CellFormatting> event while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span>

#### <a name="category"></a><span data-ttu-id="27b19-115">범주</span><span class="sxs-lookup"><span data-stu-id="27b19-115">Category</span></span>

<span data-ttu-id="27b19-116">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="27b19-116">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="27b19-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="27b19-117">Affected APIs</span></span>

<span data-ttu-id="27b19-118">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27b19-118">Not detectable via API analysis.</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
