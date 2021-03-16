---
title: '호환성이 손상되는 변경: WinForms 메서드는 이제 ArgumentNullException을 throw함'
description: 일부 Windows Forms 메서드가 Null 인수에 대해 ArgumentNullException을 throw하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 09/18/2020
ms.openlocfilehash: 9d72f8e3320430396132de20c252cd5e8759dce3
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256102"
---
# <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="9a9ee-103">WinForms 메서드는 이제 ArgumentNullException을 throw함</span><span class="sxs-lookup"><span data-stu-id="9a9ee-103">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="9a9ee-104">이제 일부 Windows Forms 메서드에서는 null 인수에 대한 <xref:System.ArgumentNullException>을 throw합니다. 이 인수가 이전에는 <xref:System.NullReferenceException>을 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="9a9ee-104">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

## <a name="change-description"></a><span data-ttu-id="9a9ee-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="9a9ee-105">Change description</span></span>

<span data-ttu-id="9a9ee-106">이전에는 특정 Windows Forms 메서드가 null인 인수를 전달한 경우 <xref:System.NullReferenceException>을 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="9a9ee-106">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="9a9ee-107">.NET 5부터 해당 메서드는 이제 Null 인수에 대한 <xref:System.ArgumentNullException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="9a9ee-107">Starting in .NET 5, these methods now throw an <xref:System.ArgumentNullException> for null arguments, instead.</span></span>

<span data-ttu-id="9a9ee-108"><xref:System.ArgumentNullException> throw는 .NET 런타임의 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9a9ee-108">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="9a9ee-109">또한 인수가 null이고 어떤 인수임을 명확하게 전달하여 디버깅 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="9a9ee-109">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="9a9ee-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="9a9ee-110">Version introduced</span></span>

<span data-ttu-id="9a9ee-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9a9ee-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="9a9ee-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="9a9ee-112">Recommended action</span></span>

<span data-ttu-id="9a9ee-113">해당 메서드 중 하나를 호출하고 코드가 현재 null 인수에 대한 <xref:System.NullReferenceException>을 catch하는 경우에는 <xref:System.ArgumentNullException>를 대신 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="9a9ee-113">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="9a9ee-114">또한 나열된 메서드에 null 인수를 전달하지 않도록 코드를 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9a9ee-114">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="9a9ee-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="9a9ee-115">Affected APIs</span></span>

<span data-ttu-id="9a9ee-116">다음 표에서는 영향을 받는 메서드 및 매개 변수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9a9ee-116">The following table lists the affected methods and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="9a9ee-117">메서드</span><span class="sxs-lookup"><span data-stu-id="9a9ee-117">Method</span></span> | <span data-ttu-id="9a9ee-118">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="9a9ee-118">Parameter name</span></span> | <span data-ttu-id="9a9ee-119">추가된 버전</span><span class="sxs-lookup"><span data-stu-id="9a9ee-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | <span data-ttu-id="9a9ee-120">미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="9a9ee-120">Preview 1</span></span> |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | <span data-ttu-id="9a9ee-121">미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="9a9ee-121">Preview 1</span></span> |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | <span data-ttu-id="9a9ee-122">미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="9a9ee-122">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="9a9ee-123">미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="9a9ee-123">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="9a9ee-124">미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="9a9ee-124">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="9a9ee-125">미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="9a9ee-125">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="9a9ee-126">미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="9a9ee-126">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | <span data-ttu-id="9a9ee-127">미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="9a9ee-127">Preview 1</span></span> |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | <span data-ttu-id="9a9ee-128">Preview 2</span><span class="sxs-lookup"><span data-stu-id="9a9ee-128">Preview 2</span></span> |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | <span data-ttu-id="9a9ee-129">Preview 2</span><span class="sxs-lookup"><span data-stu-id="9a9ee-129">Preview 2</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="9a9ee-130">Preview 5</span><span class="sxs-lookup"><span data-stu-id="9a9ee-130">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="9a9ee-131">Preview 5</span><span class="sxs-lookup"><span data-stu-id="9a9ee-131">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | <span data-ttu-id="9a9ee-132">Preview 5</span><span class="sxs-lookup"><span data-stu-id="9a9ee-132">Preview 5</span></span> |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | <span data-ttu-id="9a9ee-133">Preview 5</span><span class="sxs-lookup"><span data-stu-id="9a9ee-133">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="9a9ee-134">미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="9a9ee-134">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])> | <span data-ttu-id="9a9ee-135">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="9a9ee-135">`owner`, `value`</span></span> | <span data-ttu-id="9a9ee-136">미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="9a9ee-136">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)> | <span data-ttu-id="9a9ee-137">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="9a9ee-137">`owner`, `value`</span></span> | <span data-ttu-id="9a9ee-138">미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="9a9ee-138">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])?displayProperty=nameWithType> | `items` | <span data-ttu-id="9a9ee-139">미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="9a9ee-139">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)?displayProperty=nameWithType> | `value` | <span data-ttu-id="9a9ee-140">미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="9a9ee-140">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="9a9ee-141">미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="9a9ee-141">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="9a9ee-142">미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="9a9ee-142">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListView.SelectedIndexCollection.%23ctor(System.Windows.Forms.ListView)> | `owner` | <span data-ttu-id="9a9ee-143">미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="9a9ee-143">Preview 7</span></span> |
> | <xref:System.Windows.Forms.TreeNodeCollection.Find(System.String,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="9a9ee-144">`key`가 `null`이거나 비어 있는 경우</span><span class="sxs-lookup"><span data-stu-id="9a9ee-144">`key` is `null` or empty</span></span> | <span data-ttu-id="9a9ee-145">미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="9a9ee-145">Preview 8</span></span> |
> | <xref:System.Windows.Forms.ListView.ListViewItemCollection.Find(System.String,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="9a9ee-146">`key`가 `null`이거나 비어 있는 경우</span><span class="sxs-lookup"><span data-stu-id="9a9ee-146">`key` is `null` or empty</span></span> | <span data-ttu-id="9a9ee-147">RC1</span><span class="sxs-lookup"><span data-stu-id="9a9ee-147">RC1</span></span> |
> | <xref:System.Windows.Forms.ScrollableControl.OnPaintBackground(System.Windows.Forms.PaintEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="9a9ee-148">RC1</span><span class="sxs-lookup"><span data-stu-id="9a9ee-148">RC1</span></span> |

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
- `M:System.Windows.Forms.ListViewGroup.System#Runtime#Serialization#ISerializable#GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`
- `M:System.Windows.Forms.VisualStyles.VisualStyleRenderer.#ctor(System.String,System.Int32,System.Int32)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.#ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox,System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.System#Collections#ICollection#CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListView.SelectedIndexCollection.#ctor(System.Windows.Forms.ListView)`
- `M:System.Windows.Forms.TreeNodeCollection.Find(System.String,System.Boolean)`
- `M:System.Windows.Forms.ListView.ListViewItemCollection.Find(System.String,System.Boolean)`
- `M:System.Windows.Forms.ScrollableControl.OnPaintBackground(System.Windows.Forms.PaintEventArgs)`

### Category

Windows Forms

-->
