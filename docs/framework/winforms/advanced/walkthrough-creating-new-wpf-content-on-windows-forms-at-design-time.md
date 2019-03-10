---
title: '연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: ed48db399ba47f0e6be96f7bca33d3892b19e433
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707913"
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="cf842-102">연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기</span><span class="sxs-lookup"><span data-stu-id="cf842-102">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>

<span data-ttu-id="cf842-103">이 항목에서는 Windows Forms 기반 응용 프로그램에서 사용할 WPF(Windows Presentation Foundation) 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-103">This topic shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="cf842-104">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="cf842-105">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-105">Create the project.</span></span>

- <span data-ttu-id="cf842-106">새 WPF 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-106">Create a new WPF control.</span></span>

- <span data-ttu-id="cf842-107">새 WPF 컨트롤을 Windows Form에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="cf842-108">WPF 컨트롤이 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cf842-109">전제 조건</span><span class="sxs-lookup"><span data-stu-id="cf842-109">Prerequisites</span></span>

<span data-ttu-id="cf842-110">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="cf842-111">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="cf842-111">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="cf842-112">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="cf842-112">Creating the Project</span></span>

<span data-ttu-id="cf842-113">첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-113">The first step is to create the Windows Forms project.</span></span> <span data-ttu-id="cf842-114">Visual Studio를 열고 새 **Windows Forms 앱 (.NET Framework)** Visual Basic 또는 Visual C# 프로젝트 `HostingWpf`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-114">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="cf842-115">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="creating-a-new-wpf-control"></a><span data-ttu-id="cf842-116">새 WPF 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="cf842-116">Creating a New WPF Control</span></span>

<span data-ttu-id="cf842-117">새 WPF 컨트롤을 만들고 프로젝트에 추가하는 작업은 다른 항목을 프로젝트에 추가하는 것만큼 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-117">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="cf842-118">Windows Forms 디자이너는 특정 종류의 명명 된 컨트롤을 사용 하 여 작동 *복합 컨트롤*, 또는 *사용자 정의 컨트롤*합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-118">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="cf842-119">WPF 사용자 정의 컨트롤에 대한 자세한 내용은 <xref:System.Windows.Controls.UserControl>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf842-119">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="cf842-120">WPF용 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 형식은 Windows Forms에서 제공하는 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>이라는 사용자 정의 컨트롤 형식과 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-120">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

### <a name="to-create-a-new-wpf-control"></a><span data-ttu-id="cf842-121">새 WPF 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf842-121">To create a new WPF control</span></span>

1. <span data-ttu-id="cf842-122">**솔루션 탐색기**, 새 **WPF 사용자 정의 컨트롤 라이브러리 (.NET Framework)** 프로젝트를 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-122">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="cf842-123">컨트롤 라이브러리의 기본 이름인 `WpfControlLibrary1`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-123">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="cf842-124">기본 컨트롤 이름은 `UserControl1.xaml`입니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-124">The default control name is `UserControl1.xaml`.</span></span>

     <span data-ttu-id="cf842-125">새 컨트롤을 추가 하면 다음과 같은 같은 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-125">Adding the new control has the following effects:</span></span>

    - <span data-ttu-id="cf842-126">UserControl1.xaml 파일이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-126">File UserControl1.xaml is added.</span></span>

    - <span data-ttu-id="cf842-127">UserControl1.xaml.cs 또는 UserControl1.xaml.vb 파일이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-127">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="cf842-128">이 파일에는 이벤트 처리기 및 기타 구현에 대한 코드 숨김이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-128">This file contains the code-behind for event handlers and other implementation.</span></span>

    - <span data-ttu-id="cf842-129">WPF 어셈블리에 대한 참조가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-129">References to WPF assemblies are added.</span></span>

    - <span data-ttu-id="cf842-130">UserControl1.xaml 파일이 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-130">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>

2. <span data-ttu-id="cf842-131">디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-131">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="cf842-132">자세한 내용은 [방법: 선택 하 고 디자인 화면에서 요소를 이동](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-132">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="cf842-133">에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 **200**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-133">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="cf842-134">**도구 상자**를 끌어를 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤을 디자인 화면으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-134">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="cf842-135">에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.Controls.TextBox.Text%2A> 속성을 **Hosted Content**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-135">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf842-136">일반적으로 더 복잡한 WPF 콘텐츠를 호스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-136">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="cf842-137"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤은 여기서 설명 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-137">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="cf842-138">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-138">Build the project.</span></span>

## <a name="adding-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="cf842-139">Windows Form에 WPF 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="cf842-139">Adding a WPF Control to a Windows Form</span></span>

<span data-ttu-id="cf842-140">폼에서 새 WPF 컨트롤을 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-140">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="cf842-141">Windows Forms에서 사용 하 여 <xref:System.Windows.Forms.Integration.ElementHost> WPF 콘텐츠를 호스트 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-141">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

### <a name="to-add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="cf842-142">Windows Form에 WPF 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="cf842-142">To add a WPF control to a Windows Form</span></span>

1. <span data-ttu-id="cf842-143">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-143">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="cf842-144">에 **도구 상자**, 레이블이 지정 된 탭을 찾으려면 **WPFUserControlLibrary WPF 사용자 정의 컨트롤**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-144">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="cf842-145">`UserControl1` 인스턴스를 폼으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-145">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="cf842-146">WPF 컨트롤을 호스트할 폼에 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-146">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="cf842-147"><xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 이름이 `elementHost1` 및를 **속성** 보시 창 해당 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성이 **UserControl1**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-147">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="cf842-148">WPF 어셈블리에 대한 참조가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-148">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="cf842-149">`elementHost1` 컨트롤에는 사용 가능한 호스팅 옵션을 표시하는 스마트 태그 패널이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-149">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="cf842-150">에 **ElementHost 작업** 스마트 태그 패널 **부모 컨테이너에서 도킹**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-150">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="cf842-151">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-151">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cf842-152">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cf842-152">Next Steps</span></span>

<span data-ttu-id="cf842-153">Windows Forms와 WPF는 서로 다른 기술이지만 긴밀하게 상호 운용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-153">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="cf842-154">다양 한 모양과 응용 프로그램에서 동작을 제공 하려면 다음을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-154">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="cf842-155">WPF 페이지에서 Windows Forms 컨트롤을 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-155">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="cf842-156">자세한 내용은 [연습: WPF에서 호스팅하는 Windows Forms 컨트롤](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-156">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="cf842-157">WPF 콘텐츠에 Windows Forms 시각적 스타일을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-157">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="cf842-158">자세한 내용은 [방법: 하이브리드 응용 프로그램에서 비주얼 스타일 사용](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-158">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="cf842-159">WPF 콘텐츠의 스타일을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-159">Change the style of your WPF content.</span></span> <span data-ttu-id="cf842-160">자세한 내용은 [연습: WPF 콘텐츠 스타일 지정](walkthrough-styling-wpf-content.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf842-160">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf842-161">참고자료</span><span class="sxs-lookup"><span data-stu-id="cf842-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="cf842-162">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="cf842-162">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="cf842-163">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="cf842-163">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="cf842-164">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="cf842-164">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
