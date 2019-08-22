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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e3fb6e42270cc0a530646b656470ec99fcfc7f1f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666242"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="5bfec-102">연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기</span><span class="sxs-lookup"><span data-stu-id="5bfec-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="5bfec-103">이 문서에서는 Windows Forms 기반 응용 프로그램에서 사용할 WPF (Windows Presentation Foundation) 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5bfec-104">전제 조건</span><span class="sxs-lookup"><span data-stu-id="5bfec-104">Prerequisites</span></span>

<span data-ttu-id="5bfec-105">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="5bfec-106">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-106">Create the project</span></span>

<span data-ttu-id="5bfec-107">첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-107">The first step is to create the Windows Forms project.</span></span> <span data-ttu-id="5bfec-108">Visual Studio를 열고 Visual Basic 또는 시각적 개체 C# `HostingWpf`에 새 **Windows Forms 앱 (.NET Framework)** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-108">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="5bfec-109">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-109">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="5bfec-110">새 WPF 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="5bfec-110">Create a new WPF control</span></span>

<span data-ttu-id="5bfec-111">새 WPF 컨트롤을 만들고 프로젝트에 추가하는 작업은 다른 항목을 프로젝트에 추가하는 것만큼 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-111">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="5bfec-112">Windows Forms 디자이너은 *복합 컨트롤*또는 *사용자 정의*컨트롤 이라는 특정 종류의 컨트롤에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-112">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="5bfec-113">WPF 사용자 정의 컨트롤에 대한 자세한 내용은 <xref:System.Windows.Controls.UserControl>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bfec-113">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="5bfec-114">WPF용 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 형식은 Windows Forms에서 제공하는 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>이라는 사용자 정의 컨트롤 형식과 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-114">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="5bfec-115">새 WPF 컨트롤을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-115">To create a new WPF control:</span></span>

1. <span data-ttu-id="5bfec-116">**솔루션 탐색기**에서 새 **WPF 사용자 정의 컨트롤 라이브러리 (.NET Framework)** 프로젝트를 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-116">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="5bfec-117">컨트롤 라이브러리의 기본 이름인 `WpfControlLibrary1`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-117">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="5bfec-118">기본 컨트롤 이름은 `UserControl1.xaml`입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-118">The default control name is `UserControl1.xaml`.</span></span>

   <span data-ttu-id="5bfec-119">새 컨트롤을 추가 하면 다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-119">Adding the new control has the following effects:</span></span>

   - <span data-ttu-id="5bfec-120">UserControl1.xaml 파일이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-120">File UserControl1.xaml is added.</span></span>

   - <span data-ttu-id="5bfec-121">UserControl1.xaml.cs (또는 UserControl1) 파일이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-121">File UserControl1.xaml.cs (or UserControl1.xaml.vb) is added.</span></span> <span data-ttu-id="5bfec-122">이 파일에는 이벤트 처리기 및 기타 구현에 대한 코드 숨김이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-122">This file contains the code-behind for event handlers and other implementation.</span></span>

   - <span data-ttu-id="5bfec-123">WPF 어셈블리에 대한 참조가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-123">References to WPF assemblies are added.</span></span>

   - <span data-ttu-id="5bfec-124">파일 UserControl1은 Visual Studio 용 WPF 디자이너에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-124">File UserControl1.xaml opens in the WPF Designer for Visual Studio.</span></span>

2. <span data-ttu-id="5bfec-125">디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-125">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="5bfec-126">**속성** 창에서 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성의 값을 **200**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-126">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="5bfec-127">**도구 상자**에서 컨트롤을 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 디자인 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-127">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="5bfec-128">**속성** 창에서 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 값을 **Hosted Content**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-128">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5bfec-129">일반적으로 더 복잡한 WPF 콘텐츠를 호스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-129">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="5bfec-130"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤은 여기서 설명 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-130">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="5bfec-131">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-131">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="5bfec-132">Windows Form에 WPF 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="5bfec-132">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="5bfec-133">폼에서 새 WPF 컨트롤을 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-133">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="5bfec-134">Windows Forms는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 사용 하 여 WPF 콘텐츠를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-134">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="5bfec-135">Windows Form에 WPF 컨트롤을 추가 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-135">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="5bfec-136">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-136">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="5bfec-137">**도구 상자**에서 **WPFUserControlLibrary WPF User Controls**이라는 레이블이 지정 된 탭을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-137">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="5bfec-138">`UserControl1` 인스턴스를 폼으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-138">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="5bfec-139">WPF 컨트롤을 호스트할 폼에 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-139">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="5bfec-140">컨트롤 <xref:System.Windows.Forms.Integration.ElementHost> `elementHost1` 의 이름이이 고 **속성** 창에서 해당 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성이 **UserControl1**로 설정 된 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-140">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="5bfec-141">WPF 어셈블리에 대한 참조가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-141">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="5bfec-142">`elementHost1` 컨트롤에는 사용 가능한 호스팅 옵션을 표시하는 스마트 태그 패널이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-142">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="5bfec-143">**ElementHost Tasks** 스마트 태그 패널에서 **부모 컨테이너에서 도킹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-143">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="5bfec-144">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-144">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5bfec-145">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5bfec-145">Next steps</span></span>

<span data-ttu-id="5bfec-146">Windows Forms와 WPF는 서로 다른 기술이지만 긴밀하게 상호 운용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-146">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="5bfec-147">응용 프로그램에서 다양 한 모양과 동작을 제공 하려면 다음을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-147">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="5bfec-148">WPF 페이지에서 Windows Forms 컨트롤을 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-148">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="5bfec-149">자세한 내용은 [연습: WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)에서 Windows Forms 컨트롤 호스팅.</span><span class="sxs-lookup"><span data-stu-id="5bfec-149">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="5bfec-150">WPF 콘텐츠에 Windows Forms 시각적 스타일을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-150">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="5bfec-151">자세한 내용은 [방법: 하이브리드 응용 프로그램](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)에서 비주얼 스타일을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-151">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="5bfec-152">WPF 콘텐츠의 스타일을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfec-152">Change the style of your WPF content.</span></span> <span data-ttu-id="5bfec-153">자세한 내용은 [연습: WPF 콘텐츠](walkthrough-styling-wpf-content.md)스타일 지정</span><span class="sxs-lookup"><span data-stu-id="5bfec-153">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5bfec-154">참고자료</span><span class="sxs-lookup"><span data-stu-id="5bfec-154">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="5bfec-155">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="5bfec-155">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="5bfec-156">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="5bfec-156">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="5bfec-157">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="5bfec-157">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
