---
ms.openlocfilehash: fc0eec26073c299887b4748d0ad37e21c7294e84
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81274930"
---
### <a name="winforms-apis-now-throw-argumentnullexception"></a><span data-ttu-id="482d9-101">WinForms API는 이제 ArgumentNullException을 throw함</span><span class="sxs-lookup"><span data-stu-id="482d9-101">WinForms APIs now throw ArgumentNullException</span></span>

<span data-ttu-id="482d9-102">이제 일부 Windows Forms 메서드에서는 null 인수에 대한 <xref:System.ArgumentNullException>을 throw합니다. 이 인수가 이전에는 <xref:System.NullReferenceException>을 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="482d9-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="482d9-103">Change description</span></span>

<span data-ttu-id="482d9-104">이전에는 특정 Windows Forms 메서드가 null인 인수를 전달한 경우 <xref:System.NullReferenceException>을 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="482d9-105">.NET 5.0부터 해당 메서드는 이제 null 인수에 대한 <xref:System.ArgumentNullException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments instead.</span></span>

<span data-ttu-id="482d9-106"><xref:System.ArgumentNullException> throw는 .NET 런타임의 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="482d9-107">또한 인수가 null이고 어떤 인수임을 명확하게 전달하여 디버깅 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="482d9-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="482d9-108">Version introduced</span></span>

<span data-ttu-id="482d9-109">.NET 5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="482d9-109">.NET 5.0 Preview 1</span></span>\
<span data-ttu-id="482d9-110">.NET 5.0 미리 보기 2</span><span class="sxs-lookup"><span data-stu-id="482d9-110">.NET 5.0 Preview 2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="482d9-111">권장 조치</span><span class="sxs-lookup"><span data-stu-id="482d9-111">Recommended action</span></span>

<span data-ttu-id="482d9-112">해당 메서드 중 하나를 호출하고 코드가 현재 null 인수에 대한 <xref:System.NullReferenceException>을 catch하는 경우에는 <xref:System.ArgumentNullException>를 대신 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-112">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="482d9-113">또한 나열된 메서드에 null 인수를 전달하지 않도록 코드를 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-113">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="482d9-114">범주</span><span class="sxs-lookup"><span data-stu-id="482d9-114">Category</span></span>

<span data-ttu-id="482d9-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="482d9-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="482d9-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="482d9-116">Affected APIs</span></span>

<span data-ttu-id="482d9-117">.NET 5.0 미리 보기 1부터:</span><span class="sxs-lookup"><span data-stu-id="482d9-117">Starting in .NET 5.0 Preview 1:</span></span>

- <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)>
- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType>

<span data-ttu-id="482d9-118">.NET 5.0 미리 보기 2부터:</span><span class="sxs-lookup"><span data-stu-id="482d9-118">Starting in .NET 5.0 Preview 2:</span></span>

- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType>
- <span data-ttu-id="482d9-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType>(<xref:System.IO.Stream> 매개 변수만 해당)</span><span class="sxs-lookup"><span data-stu-id="482d9-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (for the <xref:System.IO.Stream> parameter only)</span></span>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Control.ControlCollection.#ctor(System.Windows.Forms.Control)`
- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.TableLayoutControlCollection.#ctor(System.Windows.Forms.TableLayoutPanel)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)`
- `M:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)`
- `M:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)`

-->
