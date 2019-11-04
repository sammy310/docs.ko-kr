---
title: '연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c9db49ae299870479a5cfa6372c25d793a92ff8f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460677"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="28527-102">연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬</span><span class="sxs-lookup"><span data-stu-id="28527-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="28527-103">이 문서에서는 고정 및 맞춤선과 같은 Windows Forms 레이아웃 기능을 사용 하 여 Windows Presentation Foundation (WPF) 컨트롤을 정렬 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28527-103">This article shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28527-104">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="28527-104">Prerequisites</span></span>

<span data-ttu-id="28527-105">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="28527-106">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28527-106">Create the project</span></span>

<span data-ttu-id="28527-107">Visual Studio를 열고 Visual Basic 또는 `ArrangeElementHost`라는 시각적 개체 C# 에서 새 Windows Forms 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28527-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="28527-108">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="28527-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="28527-109">WPF 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="28527-109">Create the WPF control</span></span>

<span data-ttu-id="28527-110">프로젝트에 WPF 컨트롤을 추가한 후 폼에 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28527-110">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="28527-111">프로젝트에 새 WPF <xref:System.Windows.Controls.UserControl>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-111">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="28527-112">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="28527-113">자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="28527-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="28527-114">디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="28527-115">**속성** 창에서 <xref:System.Windows.FrameworkElement.Width%2A> 값을 설정 하 고 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 **200**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="28527-116"><xref:System.Windows.Controls.Control.Background%2A> 속성의 값을 **Blue**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-116">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

5. <span data-ttu-id="28527-117">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-117">Build the project.</span></span>

## <a name="host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="28527-118">레이아웃 패널에서 WPF 컨트롤 호스트</span><span class="sxs-lookup"><span data-stu-id="28527-118">Host WPF controls in a layout panel</span></span>

<span data-ttu-id="28527-119">다른 Windows Forms 컨트롤을 사용하는 것과 동일한 방식으로 레이아웃 패널에서 WPF 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28527-119">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

1. <span data-ttu-id="28527-120">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="28527-120">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="28527-121">**도구 상자**에서 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="28527-121">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="28527-122"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 스마트 태그 패널에서 **마지막 행 제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-122">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="28527-123"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 더 큰 너비와 높이로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-123">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="28527-124">**도구 상자**에서 `UserControl1`를 두 번 클릭 하 여 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 첫 번째 셀에 `UserControl1`의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28527-124">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="28527-125">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="28527-125">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="28527-126">**도구 상자**에서 `UserControl1`를 두 번 클릭 하 여 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 두 번째 셀에 다른 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28527-126">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="28527-127">**문서 개요** 창에서 `tableLayoutPanel1`을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-127">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span>

8. <span data-ttu-id="28527-128">**속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 속성의 값을 **10, 10, 10, 10**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-128">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to **10, 10, 10, 10**.</span></span>

   <span data-ttu-id="28527-129">두 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 모두 새 레이아웃에 맞게 크기가 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="28527-129">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="28527-130">맞춤선을 사용 하 여 WPF 컨트롤 맞춤</span><span class="sxs-lookup"><span data-stu-id="28527-130">Use snaplines to align WPF controls</span></span>

<span data-ttu-id="28527-131">맞춤선을 사용하여 폼에서 컨트롤을 쉽게 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28527-131">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="28527-132">맞춤선을 사용하여 WPF 컨트롤도 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28527-132">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="28527-133">자세한 내용은 [연습: 맞춤선을 사용 하 여 Windows Forms에서 컨트롤 정렬](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="28527-133">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

1. <span data-ttu-id="28527-134">**도구 상자**에서 `UserControl1` 인스턴스를 폼으로 끌어 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 아래의 공간에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="28527-134">From the **Toolbox**, drag an instance of `UserControl1` onto the form, and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="28527-135">`UserControl1` 인스턴스가 `elementHost3`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="28527-135">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="28527-136">맞춤선을 사용하여 `elementHost3`의 왼쪽 가장자리를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 왼쪽 가장자리에 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="28527-136">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="28527-137">맞춤선을 사용하여 `elementHost3`의 크기를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤과 동일한 너비로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-137">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="28527-138">가운데 맞춤선이 컨트롤 사이에 나타날 때까지 `elementHost3`을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-138">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="28527-139">**속성** 창에서 Margin 속성의 값을 **20, 20, 20, 20**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-139">In the **Properties** window, set the value of the Margin property to **20, 20, 20, 20**.</span></span>

6. <span data-ttu-id="28527-140">가운데 맞춤선이 다시 나타날 때까지 `elementHost3`을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에서 멀리 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-140">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="28527-141">이제 가운데 맞춤선이 여백 20을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="28527-141">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="28527-142">왼쪽 가장자리가 `elementHost1`의 왼쪽 가장자리에 맞춰질 때까지 `elementHost3`를 오른쪽으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-142">Move `elementHost3` to the right until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="28527-143">오른쪽 가장자리가 `elementHost2`의 오른쪽 가장자리와 맞춰질 때까지 `elementHost3`의 너비를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-143">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchor-and-dock-wpf-controls"></a><span data-ttu-id="28527-144">WPF 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="28527-144">Anchor and dock WPF controls</span></span>

<span data-ttu-id="28527-145">폼에 호스트된 WPF 컨트롤은 다른 Windows Forms 컨트롤과 동일한 고정 및 도킹 동작을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="28527-145">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

1. <span data-ttu-id="28527-146">`elementHost1`를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-146">Select `elementHost1`.</span></span>

2. <span data-ttu-id="28527-147">**속성** 창에서 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 **Top, Bottom, Left, Right**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-147">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="28527-148"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 더 큰 크기로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-148">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

   <span data-ttu-id="28527-149">`elementHost1` 컨트롤의 크기가 조정되어 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="28527-149">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="28527-150">`elementHost2`를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-150">Select `elementHost2`.</span></span>

5. <span data-ttu-id="28527-151">**속성** 창에서 <xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-151">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="28527-152">`elementHost2` 컨트롤의 크기가 조정되어 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="28527-152">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="28527-153"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-153">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="28527-154"><xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle.Top>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-154">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="28527-155">`elementHost3`를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-155">Select `elementHost3`.</span></span>

9. <span data-ttu-id="28527-156"><xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-156">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="28527-157">`elementHost3` 컨트롤의 크기가 조정되어 폼의 나머지 공간을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="28527-157">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="28527-158">폼의 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="28527-158">Resize the form.</span></span>

    <span data-ttu-id="28527-159"><xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 3개의 크기가 모두 적절하게 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="28527-159">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

    <span data-ttu-id="28527-160">자세한 내용은 [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="28527-160">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="28527-161">참조</span><span class="sxs-lookup"><span data-stu-id="28527-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="28527-162">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="28527-162">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="28527-163">방법: 디자인 타임에 컨트롤을 양식의 가장자리에 맞춤</span><span class="sxs-lookup"><span data-stu-id="28527-163">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="28527-164">연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="28527-164">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="28527-165">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="28527-165">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="28527-166">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="28527-166">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="28527-167">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="28527-167">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
