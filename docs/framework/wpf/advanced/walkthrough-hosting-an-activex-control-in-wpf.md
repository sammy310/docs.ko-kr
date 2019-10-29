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
ms.openlocfilehash: 959bc7942eaae91c0a7a72124f6ab1ab92a3553f
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040831"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="46141-102">연습: WPF에서 ActiveX 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="46141-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="46141-103">브라우저와의 상호 작용을 개선 하기 위해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 프로그램에서 Microsoft ActiveX 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46141-103">To enable improved interaction with browsers, you can use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="46141-104">이 연습에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지의 컨트롤로 Microsoft Windows Media Player를 호스트 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46141-104">This walkthrough demonstrates how you can host the Microsoft Windows Media Player as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>

 <span data-ttu-id="46141-105">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46141-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="46141-106">프로젝트 만들기.</span><span class="sxs-lookup"><span data-stu-id="46141-106">Creating the project.</span></span>

- <span data-ttu-id="46141-107">ActiveX 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46141-107">Creating the ActiveX control.</span></span>

- <span data-ttu-id="46141-108">WPF 페이지에서 ActiveX 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="46141-108">Hosting the ActiveX control on a WPF Page.</span></span>

 <span data-ttu-id="46141-109">이 연습을 완료 하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 프로그램에서 Microsoft ActiveX 컨트롤을 사용 하는 방법을 이해 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46141-109">When you have completed this walkthrough, you will understand how to use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="46141-110">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="46141-110">Prerequisites</span></span>
 <span data-ttu-id="46141-111">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-111">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="46141-112">Visual Studio가 설치 된 컴퓨터에 Microsoft Windows Media Player 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46141-112">Microsoft Windows Media Player installed on the computer where Visual Studio is installed.</span></span>

- <span data-ttu-id="46141-113">Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="46141-113">Visual Studio 2010.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="46141-114">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="46141-114">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="46141-115">프로젝트를 만들고 설정하려면</span><span class="sxs-lookup"><span data-stu-id="46141-115">To create and set up the project</span></span>

1. <span data-ttu-id="46141-116">`HostingAxInWpf`이라는 WPF 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46141-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>

2. <span data-ttu-id="46141-117">Windows Forms 컨트롤 라이브러리 프로젝트를 솔루션에 추가 하 고 프로젝트 이름을 `WmpAxLib`합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>

3. <span data-ttu-id="46141-118">WmpAxLib 프로젝트에서 이름이 wmp 인 Windows Media Player 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>

4. <span data-ttu-id="46141-119">**도구 상자**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="46141-119">Open the **Toolbox**.</span></span>

5. <span data-ttu-id="46141-120">**도구 상자**를 마우스 오른쪽 단추로 클릭 한 다음 **항목 선택**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>

6. <span data-ttu-id="46141-121">**COM 구성 요소** 탭을 클릭 하 고 **Windows Media Player** 컨트롤을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>

     <span data-ttu-id="46141-122">Windows Media Player 컨트롤이 **도구 상자**에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46141-122">The Windows Media Player control is added to the **Toolbox**.</span></span>

7. <span data-ttu-id="46141-123">솔루션 탐색기에서 **UserControl1** 파일을 마우스 오른쪽 단추로 클릭 한 다음 **이름 바꾸기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>

8. <span data-ttu-id="46141-124">언어에 따라 이름을 `WmpAxControl.vb` 또는 `WmpAxControl.cs`로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>

9. <span data-ttu-id="46141-125">모든 참조의 이름을 바꾸라는 메시지가 표시 되 면 **예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-125">If you are prompted to rename all references, click **Yes**.</span></span>

## <a name="creating-the-activex-control"></a><span data-ttu-id="46141-126">ActiveX 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="46141-126">Creating the ActiveX Control</span></span>
<span data-ttu-id="46141-127">Visual Studio는 컨트롤이 디자인 화면에 추가 될 때 Microsoft ActiveX 컨트롤에 대 한 <xref:System.Windows.Forms.AxHost> 래퍼 클래스를 자동으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-127">Visual Studio automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a Microsoft ActiveX control when the control is added to a design surface.</span></span> <span data-ttu-id="46141-128">다음 절차에서는 AxInterop 라는 관리 되는 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46141-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>

### <a name="to-create-the-activex-control"></a><span data-ttu-id="46141-129">ActiveX 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="46141-129">To create the ActiveX control</span></span>

1. <span data-ttu-id="46141-130">Windows Forms 디자이너에서 WmpAxControl 또는 WmpAxControl.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="46141-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="46141-131">**도구 상자**에서 Windows Media Player 컨트롤을 디자인 화면에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>

3. <span data-ttu-id="46141-132">속성 창에서 Windows Media Player 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성 값을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

4. <span data-ttu-id="46141-133">WmpAxLib 컨트롤 라이브러리 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-133">Build the WmpAxLib control library project.</span></span>

## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="46141-134">WPF 페이지에서 ActiveX 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="46141-134">Hosting the ActiveX Control on a WPF Page</span></span>

### <a name="to-host-the-activex-control"></a><span data-ttu-id="46141-135">ActiveX 컨트롤을 호스팅하려면</span><span class="sxs-lookup"><span data-stu-id="46141-135">To host the ActiveX control</span></span>

1. <span data-ttu-id="46141-136">HostingAxInWpf 프로젝트에서 생성 된 ActiveX 상호 운용성 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-136">In the HostingAxInWpf project, add a reference to the generated ActiveX interoperability assembly.</span></span>

     <span data-ttu-id="46141-137">이 어셈블리의 이름은 WMPLib이 고 Windows Media Player 컨트롤을 가져올 때 WmpAxLib 프로젝트의 Debug 폴더에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="46141-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>

2. <span data-ttu-id="46141-138">Windows양식 통합 어셈블리에 참조를 추가 합니다 .이 어셈블리에는 Windows Integration .dll 이라는 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46141-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="46141-139">이름이 System.object 인 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>

4. <span data-ttu-id="46141-140">WPF 디자이너에서 Mainwindow.xaml를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="46141-140">Open MainWindow.xaml in the WPF Designer.</span></span>

5. <span data-ttu-id="46141-141"><xref:System.Windows.Controls.Grid> 요소의 이름을 `grid1`합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. <span data-ttu-id="46141-142">디자인 뷰 또는 XAML 뷰에서 <xref:System.Windows.Window> 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

7. <span data-ttu-id="46141-143">속성 창에서 **이벤트** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-143">In the Properties window, click the **Events** tab.</span></span>

8. <span data-ttu-id="46141-144"><xref:System.Windows.FrameworkElement.Loaded> 이벤트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

9. <span data-ttu-id="46141-145"><xref:System.Windows.FrameworkElement.Loaded> 이벤트를 처리 하는 다음 코드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     <span data-ttu-id="46141-146">이 코드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤의 인스턴스를 만들고 `AxWindowsMediaPlayer` 컨트롤의 인스턴스를 자식으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="46141-147">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="46141-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46141-148">참조</span><span class="sxs-lookup"><span data-stu-id="46141-148">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="46141-149">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="46141-149">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="46141-150">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="46141-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="46141-151">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="46141-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
