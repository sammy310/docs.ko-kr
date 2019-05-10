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
ms.openlocfilehash: a8f690438136450cb12dbcf5e17ddfcca617457e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211438"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="82b46-102">연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬</span><span class="sxs-lookup"><span data-stu-id="82b46-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="82b46-103">이 연습에서는 기준 위치 지정 및 맞춤선과 같은 Windows Forms 레이아웃 기능을 사용하여 WPF(Windows Presentation Foundation) 컨트롤을 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-103">This walkthrough shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

<span data-ttu-id="82b46-104">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="82b46-105">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-105">Create the project.</span></span>

- <span data-ttu-id="82b46-106">WPF 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-106">Create the WPF control.</span></span>

- <span data-ttu-id="82b46-107">레이아웃 패널에서 WPF 컨트롤을 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-107">Host WPF controls in a layout panel.</span></span>

- <span data-ttu-id="82b46-108">맞춤선을 사용하여 WPF 컨트롤을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-108">Use snaplines to align WPF controls.</span></span>

- <span data-ttu-id="82b46-109">WPF 컨트롤을 고정 및 도킹합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-109">Anchor and dock WPF controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="82b46-110">전제 조건</span><span class="sxs-lookup"><span data-stu-id="82b46-110">Prerequisites</span></span>

<span data-ttu-id="82b46-111">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-111">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="82b46-112">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-112">Create the project</span></span>

<span data-ttu-id="82b46-113">Visual Studio를 열고 Visual Basic 또는 시각적 개체에서 새 Windows Forms 응용 프로그램 프로젝트를 만듭니다 C# 이라는 `ArrangeElementHost`합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-113">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="82b46-114">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-114">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="82b46-115">WPF 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="82b46-115">Create the WPF control</span></span>

<span data-ttu-id="82b46-116">프로젝트에 WPF 컨트롤을 추가한 후 폼에 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-116">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="82b46-117">프로젝트에 새 WPF <xref:System.Windows.Controls.UserControl>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-117">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="82b46-118">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-118">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="82b46-119">자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-119">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="82b46-120">디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-120">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="82b46-121">자세한 내용은 [방법: 선택 하 고 디자인 화면에서 요소를 이동](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-121">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="82b46-122">에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 `200`입니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-122">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="82b46-123"><xref:System.Windows.Controls.Control.Background%2A> 속성 값을 `Blue`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-123">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>

5. <span data-ttu-id="82b46-124">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-124">Build the project.</span></span>

## <a name="hosting-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="82b46-125">레이아웃 패널에서 WPF 컨트롤 호스트</span><span class="sxs-lookup"><span data-stu-id="82b46-125">Hosting WPF Controls in a Layout Panel</span></span>
 <span data-ttu-id="82b46-126">다른 Windows Forms 컨트롤을 사용하는 것과 동일한 방식으로 레이아웃 패널에서 WPF 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-126">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

#### <a name="to-host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="82b46-127">레이아웃 패널에서 WPF 컨트롤을 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="82b46-127">To host WPF controls in a layout panel</span></span>

1. <span data-ttu-id="82b46-128">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-128">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="82b46-129">에 **도구 상자**를 끌어를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-129">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="82b46-130">에 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 스마트 태그 패널에서 선택 **마지막 행 제거**합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-130">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="82b46-131"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 더 큰 너비와 높이로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-131">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="82b46-132">에 **도구 상자**, 두 번 클릭 `UserControl1` 의 인스턴스를 만들 `UserControl1` 의 첫 번째 셀에는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-132">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

     <span data-ttu-id="82b46-133">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-133">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="82b46-134">에 **도구 상자**를 두 번 클릭 `UserControl1` 의 두 번째 셀에 다른 인스턴스를 만들 수는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-134">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="82b46-135">에 **문서 개요** 창에서 `tableLayoutPanel1`합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-135">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span> <span data-ttu-id="82b46-136">자세한 내용은 [문서 개요 창](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf)합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-136">For more information, see [Document Outline Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf).</span></span>

8. <span data-ttu-id="82b46-137">에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 `10, 10, 10, 10`입니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-137">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to `10, 10, 10, 10`.</span></span>

     <span data-ttu-id="82b46-138">두 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 모두 새 레이아웃에 맞게 크기가 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-138">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="using-snaplines-to-align-wpf-controls"></a><span data-ttu-id="82b46-139">맞춤선을 사용하여 WPF 컨트롤 맞춤</span><span class="sxs-lookup"><span data-stu-id="82b46-139">Using Snaplines to Align WPF Controls</span></span>
 <span data-ttu-id="82b46-140">맞춤선을 사용하여 폼에서 컨트롤을 쉽게 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-140">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="82b46-141">맞춤선을 사용하여 WPF 컨트롤도 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-141">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="82b46-142">자세한 내용은 [연습: Snaplines를 사용 하 여 Forms Windows에서 컨트롤 정렬](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-142">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

#### <a name="to-use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="82b46-143">맞춤선을 사용하여 WPF 컨트롤을 맞추려면</span><span class="sxs-lookup"><span data-stu-id="82b46-143">To use snaplines to align WPF controls</span></span>

1. <span data-ttu-id="82b46-144">**도구 상자**의 인스턴스를 끕니다 `UserControl1` 폼 아래 공간에 배치 하는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-144">From the **Toolbox**, drag an instance of `UserControl1` onto the form and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

     <span data-ttu-id="82b46-145">`UserControl1` 인스턴스가 `elementHost3`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-145">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="82b46-146">맞춤선을 사용하여 `elementHost3`의 왼쪽 가장자리를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 왼쪽 가장자리에 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-146">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="82b46-147">맞춤선을 사용하여 `elementHost3`의 크기를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤과 동일한 너비로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-147">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="82b46-148">가운데 맞춤선이 컨트롤 사이에 나타날 때까지 `elementHost3`을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-148">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="82b46-149">에 **속성** 여백 속성의 값을 설정 하는 창 `20, 20, 20, 20`합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-149">In the **Properties** window, set the value of the Margin property to `20, 20, 20, 20`.</span></span>

6. <span data-ttu-id="82b46-150">가운데 맞춤선이 다시 나타날 때까지 `elementHost3`을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에서 멀리 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-150">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="82b46-151">이제 가운데 맞춤선이 여백 20을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-151">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="82b46-152">왼쪽 가장자리가 `elementHost1`의 왼쪽 가장자리와 맞춰질 때까지 `elementHost3`을 오른쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-152">Move `elementHost3` to the right, until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="82b46-153">오른쪽 가장자리가 `elementHost2`의 오른쪽 가장자리와 맞춰질 때까지 `elementHost3`의 너비를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-153">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchoring-and-docking-wpf-controls"></a><span data-ttu-id="82b46-154">WPF 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="82b46-154">Anchoring and Docking WPF Controls</span></span>
 <span data-ttu-id="82b46-155">폼에 호스트된 WPF 컨트롤은 다른 Windows Forms 컨트롤과 동일한 고정 및 도킹 동작을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-155">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

#### <a name="to-anchor-and-dock-wpf-controls"></a><span data-ttu-id="82b46-156">WPF 컨트롤을 고정 및 도킹하려면</span><span class="sxs-lookup"><span data-stu-id="82b46-156">To anchor and dock WPF controls</span></span>

1. <span data-ttu-id="82b46-157">`elementHost1`를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-157">Select `elementHost1`.</span></span>

2. <span data-ttu-id="82b46-158">에 **속성** 창에서 합니다 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 **위쪽, 아래쪽, 왼쪽, 오른쪽**합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-158">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="82b46-159"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 더 큰 크기로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-159">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

     <span data-ttu-id="82b46-160">`elementHost1` 컨트롤의 크기가 조정되어 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-160">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="82b46-161">`elementHost2`를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-161">Select `elementHost2`.</span></span>

5. <span data-ttu-id="82b46-162">에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>입니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-162">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

     <span data-ttu-id="82b46-163">`elementHost2` 컨트롤의 크기가 조정되어 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-163">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="82b46-164"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-164">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="82b46-165"><xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle.Top>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-165">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="82b46-166">`elementHost3`를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-166">Select `elementHost3`.</span></span>

9. <span data-ttu-id="82b46-167"><xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-167">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

     <span data-ttu-id="82b46-168">`elementHost3` 컨트롤의 크기가 조정되어 폼의 나머지 공간을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-168">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="82b46-169">폼의 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-169">Resize the form.</span></span>

     <span data-ttu-id="82b46-170"><xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 3개의 크기가 모두 적절하게 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-170">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

     <span data-ttu-id="82b46-171">자세한 내용은 [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82b46-171">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="82b46-172">참고자료</span><span class="sxs-lookup"><span data-stu-id="82b46-172">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="82b46-173">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="82b46-173">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="82b46-174">방법: 디자인 타임에 컨트롤을 폼의 가장자리에 맞춤</span><span class="sxs-lookup"><span data-stu-id="82b46-174">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="82b46-175">연습: 맞춤선을 사용 하 여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="82b46-175">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="82b46-176">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="82b46-176">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="82b46-177">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="82b46-177">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="82b46-178">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="82b46-178">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
