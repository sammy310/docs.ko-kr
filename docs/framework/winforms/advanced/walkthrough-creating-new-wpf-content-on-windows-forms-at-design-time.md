---
title: Windows Forms에서 새 WPF 콘텐츠 만들기
titleSuffix: ''
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 69a0598b05d1b2bff84b203317d6d5a166ce109d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746396"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="ed674-102">연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기</span><span class="sxs-lookup"><span data-stu-id="ed674-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="ed674-103">이 문서에서는 Windows Forms 기반 응용 프로그램에서 사용할 WPF (Windows Presentation Foundation) 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ed674-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="ed674-104">Prerequisites</span></span>

<span data-ttu-id="ed674-105">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="ed674-106">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-106">Create the project</span></span>

<span data-ttu-id="ed674-107">Visual Studio를 열고 Visual Basic 또는 시각적 개체 C# `HostingWpf`에 새 **Windows Forms 앱 (.NET Framework)** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-107">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="ed674-108">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="ed674-109">새 WPF 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="ed674-109">Create a new WPF control</span></span>

<span data-ttu-id="ed674-110">새 WPF 컨트롤을 만들고 프로젝트에 추가하는 작업은 다른 항목을 프로젝트에 추가하는 것만큼 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-110">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="ed674-111">Windows Forms 디자이너은 *복합 컨트롤*또는 *사용자 정의*컨트롤 이라는 특정 종류의 컨트롤에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-111">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="ed674-112">WPF 사용자 정의 컨트롤에 대한 자세한 내용은 <xref:System.Windows.Controls.UserControl>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed674-112">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="ed674-113">WPF용 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 형식은 Windows Forms에서 제공하는 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>이라는 사용자 정의 컨트롤 형식과 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-113">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="ed674-114">새 WPF 컨트롤을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-114">To create a new WPF control:</span></span>

1. <span data-ttu-id="ed674-115">**솔루션 탐색기**에서 새 **WPF 사용자 정의 컨트롤 라이브러리 (.NET Framework)** 프로젝트를 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-115">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="ed674-116">컨트롤 라이브러리의 기본 이름인 `WpfControlLibrary1`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-116">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="ed674-117">기본 컨트롤 이름은 `UserControl1.xaml`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-117">The default control name is `UserControl1.xaml`.</span></span>

   <span data-ttu-id="ed674-118">새 컨트롤을 추가 하면 다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-118">Adding the new control has the following effects:</span></span>

   - <span data-ttu-id="ed674-119">UserControl1.xaml 파일이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-119">File UserControl1.xaml is added.</span></span>

   - <span data-ttu-id="ed674-120">UserControl1.xaml.cs (또는 UserControl1) 파일이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-120">File UserControl1.xaml.cs (or UserControl1.xaml.vb) is added.</span></span> <span data-ttu-id="ed674-121">이 파일에는 이벤트 처리기 및 기타 구현에 대한 코드 숨김이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-121">This file contains the code-behind for event handlers and other implementation.</span></span>

   - <span data-ttu-id="ed674-122">WPF 어셈블리에 대한 참조가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-122">References to WPF assemblies are added.</span></span>

   - <span data-ttu-id="ed674-123">파일 UserControl1은 Visual Studio 용 WPF 디자이너에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-123">File UserControl1.xaml opens in the WPF Designer for Visual Studio.</span></span>

2. <span data-ttu-id="ed674-124">디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-124">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="ed674-125">**속성** 창에서 <xref:System.Windows.FrameworkElement.Width%2A> 값을 설정 하 고 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 **200**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-125">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="ed674-126">**도구 상자**에서 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤을 디자인 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-126">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="ed674-127">**속성** 창에서 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 값을 **Hosted Content**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-127">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ed674-128">일반적으로 더 복잡한 WPF 콘텐츠를 호스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-128">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="ed674-129"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤은 여기서 설명 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-129">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="ed674-130">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-130">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="ed674-131">Windows Form에 WPF 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="ed674-131">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="ed674-132">폼에서 새 WPF 컨트롤을 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-132">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="ed674-133">Windows Forms은 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 사용 하 여 WPF 콘텐츠를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-133">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="ed674-134">Windows Form에 WPF 컨트롤을 추가 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-134">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="ed674-135">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-135">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="ed674-136">**도구 상자**에서 **WPFUserControlLibrary WPF User Controls**이라는 레이블이 지정 된 탭을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-136">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="ed674-137">`UserControl1` 인스턴스를 폼으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-137">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="ed674-138">WPF 컨트롤을 호스트할 폼에 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-138">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="ed674-139"><xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 이름은 `elementHost1` 하 고 **속성** 창에서 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성이 **UserControl1**로 설정 된 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-139">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="ed674-140">WPF 어셈블리에 대한 참조가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-140">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="ed674-141">`elementHost1` 컨트롤에는 사용 가능한 호스팅 옵션을 표시하는 스마트 태그 패널이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-141">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="ed674-142">**ElementHost Tasks** 스마트 태그 패널에서 **부모 컨테이너에서 도킹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-142">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="ed674-143">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-143">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed674-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ed674-144">Next steps</span></span>

<span data-ttu-id="ed674-145">Windows Forms와 WPF는 서로 다른 기술이지만 긴밀하게 상호 운용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-145">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="ed674-146">응용 프로그램에서 다양 한 모양과 동작을 제공 하려면 다음을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-146">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="ed674-147">WPF 페이지에서 Windows Forms 컨트롤을 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-147">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="ed674-148">자세한 내용은 [연습: WPF에서 Windows Forms 컨트롤 호스팅](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed674-148">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="ed674-149">WPF 콘텐츠에 Windows Forms 시각적 스타일을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-149">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="ed674-150">자세한 내용은 [방법: 혼합 애플리케이션에서 비주얼 스타일 사용](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed674-150">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="ed674-151">WPF 콘텐츠의 스타일을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ed674-151">Change the style of your WPF content.</span></span> <span data-ttu-id="ed674-152">자세한 내용은 [연습: WPF 콘텐츠 스타일](walkthrough-styling-wpf-content.md)지정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed674-152">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ed674-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed674-153">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="ed674-154">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="ed674-154">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="ed674-155">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="ed674-155">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="ed674-156">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="ed674-156">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
