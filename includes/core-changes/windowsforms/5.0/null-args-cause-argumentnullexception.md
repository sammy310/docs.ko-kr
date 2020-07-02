---
ms.openlocfilehash: 00f89e6ae49982917fa7591c3283adec3947eed2
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365653"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="ab3b4-101">WinForms 메서드는 이제 ArgumentNullException을 throw함</span><span class="sxs-lookup"><span data-stu-id="ab3b4-101">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="ab3b4-102">이제 일부 Windows Forms 메서드에서는 null 인수에 대한 <xref:System.ArgumentNullException>을 throw합니다. 이 인수가 이전에는 <xref:System.NullReferenceException>을 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3b4-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ab3b4-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="ab3b4-103">Change description</span></span>

<span data-ttu-id="ab3b4-104">이전에는 특정 Windows Forms 메서드가 null인 인수를 전달한 경우 <xref:System.NullReferenceException>을 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3b4-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="ab3b4-105">.NET 5.0부터 해당 메서드는 이제 null 인수에 대한 <xref:System.ArgumentNullException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3b4-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments, instead.</span></span>

<span data-ttu-id="ab3b4-106"><xref:System.ArgumentNullException> throw는 .NET 런타임의 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ab3b4-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="ab3b4-107">또한 인수가 null이고 어떤 인수임을 명확하게 전달하여 디버깅 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3b4-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ab3b4-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="ab3b4-108">Version introduced</span></span>

<span data-ttu-id="ab3b4-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="ab3b4-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ab3b4-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="ab3b4-110">Recommended action</span></span>

<span data-ttu-id="ab3b4-111">해당 메서드 중 하나를 호출하고 코드가 현재 null 인수에 대한 <xref:System.NullReferenceException>을 catch하는 경우에는 <xref:System.ArgumentNullException>를 대신 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3b4-111">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="ab3b4-112">또한 나열된 메서드에 null 인수를 전달하지 않도록 코드를 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3b4-112">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="ab3b4-113">범주</span><span class="sxs-lookup"><span data-stu-id="ab3b4-113">Category</span></span>

<span data-ttu-id="ab3b4-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ab3b4-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ab3b4-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ab3b4-115">Affected APIs</span></span>

<span data-ttu-id="ab3b4-116">다음 표에서는 영향을 받는 메서드 및 매개 변수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab3b4-116">The following table lists the affected methods and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="ab3b4-117">메서드</span><span class="sxs-lookup"><span data-stu-id="ab3b4-117">Method</span></span> | <span data-ttu-id="ab3b4-118">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="ab3b4-118">Parameter name</span></span> | <span data-ttu-id="ab3b4-119">추가된 버전</span><span class="sxs-lookup"><span data-stu-id="ab3b4-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | <span data-ttu-id="ab3b4-120">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="ab3b4-120">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | <span data-ttu-id="ab3b4-121">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="ab3b4-121">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | <span data-ttu-id="ab3b4-122">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="ab3b4-122">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="ab3b4-123">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="ab3b4-123">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="ab3b4-124">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="ab3b4-124">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="ab3b4-125">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="ab3b4-125">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="ab3b4-126">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="ab3b4-126">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | <span data-ttu-id="ab3b4-127">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="ab3b4-127">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | <span data-ttu-id="ab3b4-128">5.0 미리 보기 2</span><span class="sxs-lookup"><span data-stu-id="ab3b4-128">5.0 Preview 2</span></span> |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | <span data-ttu-id="ab3b4-129">5.0 미리 보기 2</span><span class="sxs-lookup"><span data-stu-id="ab3b4-129">5.0 Preview 2</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="ab3b4-130">5.0 미리 보기 5</span><span class="sxs-lookup"><span data-stu-id="ab3b4-130">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="ab3b4-131">5.0 미리 보기 5</span><span class="sxs-lookup"><span data-stu-id="ab3b4-131">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | <span data-ttu-id="ab3b4-132">5.0 미리 보기 5</span><span class="sxs-lookup"><span data-stu-id="ab3b4-132">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | <span data-ttu-id="ab3b4-133">5.0 미리 보기 5</span><span class="sxs-lookup"><span data-stu-id="ab3b4-133">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="ab3b4-134">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="ab3b4-134">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])> | <span data-ttu-id="ab3b4-135">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="ab3b4-135">`owner`, `value`</span></span> | <span data-ttu-id="ab3b4-136">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="ab3b4-136">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)> | <span data-ttu-id="ab3b4-137">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="ab3b4-137">`owner`, `value`</span></span> | <span data-ttu-id="ab3b4-138">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="ab3b4-138">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])?displayProperty=nameWithType> | `items` | <span data-ttu-id="ab3b4-139">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="ab3b4-139">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)?displayProperty=nameWithType> | `value` | <span data-ttu-id="ab3b4-140">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="ab3b4-140">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="ab3b4-141">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="ab3b4-141">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="ab3b4-142">`destination`q\`</span><span class="sxs-lookup"><span data-stu-id="ab3b4-142">`destination`q\`</span></span> | <span data-ttu-id="ab3b4-143">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="ab3b4-143">5.0 Preview 6</span></span> |

<!-- 

#### Affected APIs

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
- `M:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`
- `M:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)`

-->
