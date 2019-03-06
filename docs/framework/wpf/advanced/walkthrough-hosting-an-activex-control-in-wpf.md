---
title: '연습: WPF에서 ActiveX 컨트롤 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 31e1098a5c3157351bebd2c19dd6ee986d2fbe78
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363945"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="7753f-102">연습: WPF에서 ActiveX 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="7753f-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="7753f-103">브라우저를 사용 하 여 향상 된 상호 작용을 사용 하도록 설정 하려면 사용할 수 있습니다 [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] 컨트롤에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-103">To enable improved interaction with browsers, you can use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="7753f-104">이 연습에서는 호스팅하는 방법을 보여 줍니다.는 [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 의 컨트롤로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-104">This walkthrough demonstrates how you can host the [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>

 <span data-ttu-id="7753f-105">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-105">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="7753f-106">프로젝트 만들기.</span><span class="sxs-lookup"><span data-stu-id="7753f-106">Creating the project.</span></span>

-   <span data-ttu-id="7753f-107">ActiveX 컨트롤을 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-107">Creating the ActiveX control.</span></span>

-   <span data-ttu-id="7753f-108">WPF 페이지에서 ActiveX 컨트롤 호스팅.</span><span class="sxs-lookup"><span data-stu-id="7753f-108">Hosting the ActiveX control on a WPF Page.</span></span>

 <span data-ttu-id="7753f-109">이 연습을 완료 하는 경우 사용 하는 방법을 이해할 [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] 컨트롤에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-109">When you have completed this walkthrough, you will understand how to use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7753f-110">전제 조건</span><span class="sxs-lookup"><span data-stu-id="7753f-110">Prerequisites</span></span>
 <span data-ttu-id="7753f-111">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-111">You need the following components to complete this walkthrough:</span></span>

-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] <span data-ttu-id="7753f-112">Visual Studio를 설치한 컴퓨터에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-112">installed on the computer where Visual Studio is installed.</span></span>

-   <span data-ttu-id="7753f-113">Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="7753f-113">Visual Studio 2010.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="7753f-114">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="7753f-114">Creating the Project</span></span>

#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="7753f-115">프로젝트를 만들고 설정하려면</span><span class="sxs-lookup"><span data-stu-id="7753f-115">To create and set up the project</span></span>

1.  <span data-ttu-id="7753f-116">이라는 WPF 응용 프로그램 프로젝트를 만듭니다 `HostingAxInWpf`합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>

2.  <span data-ttu-id="7753f-117">Windows Forms 컨트롤 라이브러리 프로젝트를 솔루션에 추가 하 고 프로젝트 이름을 `WmpAxLib`입니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>

3.  <span data-ttu-id="7753f-118">WmpAxLib 프로젝트에서 wmp.dll 라고 하는 Windows Media Player 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>

4.  <span data-ttu-id="7753f-119">엽니다는 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-119">Open the **Toolbox**.</span></span>

5.  <span data-ttu-id="7753f-120">마우스 오른쪽 단추로 클릭 합니다 **도구 상자**를 클릭 하 고 **선택 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>

6.  <span data-ttu-id="7753f-121">클릭 합니다 **COM 구성 요소** 탭을 선택 합니다 **Windows Media Player** 컨트롤을 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>

     <span data-ttu-id="7753f-122">Windows Media Player 컨트롤이 추가 되는 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-122">The Windows Media Player control is added to the **Toolbox**.</span></span>

7.  <span data-ttu-id="7753f-123">솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 합니다 **UserControl1** 파일을 선택한 다음 클릭 **이름 바꾸기**합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>

8.  <span data-ttu-id="7753f-124">이름을 변경할 `WmpAxControl.vb` 또는 `WmpAxControl.cs`언어에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>

9. <span data-ttu-id="7753f-125">모든 참조 이름을 묻는 클릭 **예**합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-125">If you are prompted to rename all references, click **Yes**.</span></span>

## <a name="creating-the-activex-control"></a><span data-ttu-id="7753f-126">ActiveX 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="7753f-126">Creating the ActiveX Control</span></span>
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] <span data-ttu-id="7753f-127">자동으로 생성을 <xref:System.Windows.Forms.AxHost> 에 대 한 래퍼 클래스를 [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] 컨트롤이 디자인 화면에 추가 되는 경우를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-127">automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] control when the control is added to a design surface.</span></span> <span data-ttu-id="7753f-128">다음 절차는 AxInterop.WMPLib.dll 이라는 관리 되는 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>

#### <a name="to-create-the-activex-control"></a><span data-ttu-id="7753f-129">ActiveX 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="7753f-129">To create the ActiveX control</span></span>

1.  <span data-ttu-id="7753f-130">Windows Forms 디자이너에서 WmpAxControl.vb 또는 WmpAxControl.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>

2.  <span data-ttu-id="7753f-131">**도구 상자**, Windows Media Player 컨트롤이 디자인 화면에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>

3.  <span data-ttu-id="7753f-132">속성 창에서 Windows Media Player 컨트롤의 값을 설정 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>입니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

4.  <span data-ttu-id="7753f-133">WmpAxLib 컨트롤 라이브러리 프로젝트를 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="7753f-133">Build the WmpAxLib control library project.</span></span>

## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="7753f-134">WPF 페이지에서 ActiveX 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="7753f-134">Hosting the ActiveX Control on a WPF Page</span></span>

#### <a name="to-host-the-activex-control"></a><span data-ttu-id="7753f-135">ActiveX 컨트롤을 호스트 하려면</span><span class="sxs-lookup"><span data-stu-id="7753f-135">To host the ActiveX control</span></span>

1.  <span data-ttu-id="7753f-136">HostingAxInWpf 프로젝트에서 생성 된에 대 한 참조를 추가 [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] 상호 운용성 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="7753f-136">In the HostingAxInWpf project, add a reference to the generated [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] interoperability assembly.</span></span>

     <span data-ttu-id="7753f-137">이 어셈블리 AxInterop.WMPLib.dll 이름이 고은 Windows Media Player 컨트롤이 가져올 때 WmpAxLib 프로젝트의 디버그 폴더에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>

2.  <span data-ttu-id="7753f-138">WindowsFormsIntegration.dll 이라는 WindowsFormsIntegration 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3.  <span data-ttu-id="7753f-139">에 대 한 참조를 추가 합니다 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] System.Windows.Forms.dll 라고 하는 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>

4.  <span data-ttu-id="7753f-140">WPF Designer의 MainWindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-140">Open MainWindow.xaml in the WPF Designer.</span></span>

5.  <span data-ttu-id="7753f-141">이름 합니다 <xref:System.Windows.Controls.Grid> 요소 `grid1`합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6.  <span data-ttu-id="7753f-142">디자인 뷰 또는 XAML 뷰에서 선택 된 <xref:System.Windows.Window> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

7.  <span data-ttu-id="7753f-143">속성 창에서 클릭 합니다 **이벤트** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-143">In the Properties window, click the **Events** tab.</span></span>

8.  <span data-ttu-id="7753f-144">두 번 클릭 하 여 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

9. <span data-ttu-id="7753f-145">처리 하는 다음 코드를 삽입 합니다 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     <span data-ttu-id="7753f-146">이 코드의 인스턴스를 만듭니다는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 하 고 인스턴스를 추가 합니다 `AxWindowsMediaPlayer` 해당 자식 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="7753f-147">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7753f-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7753f-148">참고자료</span><span class="sxs-lookup"><span data-stu-id="7753f-148">See also</span></span>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="7753f-149">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="7753f-149">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="7753f-150">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="7753f-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="7753f-151">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="7753f-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
