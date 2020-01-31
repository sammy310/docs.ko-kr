---
title: Windows Forms에서 3D WPF 복합 컨트롤 호스팅
titleSuffix: ''
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: aaa726ac90fd75a12054c18be6ec08a1372c1128
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794206"
---
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="6a30e-102">연습: Windows Forms에서 3D WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="6a30e-102">Walkthrough: Host a 3D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="6a30e-103">이 연습에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤을 만들고 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 사용 하 여 Windows Forms 컨트롤과 폼에서 호스트 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in Windows Forms controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="6a30e-104">이 연습에서는 두 개의 자식 컨트롤을 포함 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="6a30e-105"><xref:System.Windows.Controls.UserControl> 3 차원 (3D) 원뿔을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3D) cone.</span></span> <span data-ttu-id="6a30e-106">3D 개체 렌더링은 Windows Forms 보다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용 하는 것이 훨씬 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-106">Rendering 3D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with Windows Forms.</span></span> <span data-ttu-id="6a30e-107">따라서 Windows Forms에서 3D 그래픽을 만들기 위해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 클래스를 호스트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3D graphics in Windows Forms.</span></span>

<span data-ttu-id="6a30e-108">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="6a30e-109">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>만들기</span><span class="sxs-lookup"><span data-stu-id="6a30e-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="6a30e-110">Windows Forms 호스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="6a30e-111">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6a30e-112">전제 조건</span><span class="sxs-lookup"><span data-stu-id="6a30e-112">Prerequisites</span></span>

<span data-ttu-id="6a30e-113">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="6a30e-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="6a30e-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="6a30e-115">UserControl 만들기</span><span class="sxs-lookup"><span data-stu-id="6a30e-115">Create the UserControl</span></span>

1. <span data-ttu-id="6a30e-116">`HostingWpfUserControlInWf`이라는 **WPF 사용자 정의 컨트롤 라이브러리** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="6a30e-117">WPF 디자이너에서 UserControl1을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-117">Open UserControl1.xaml in the WPF Designer.</span></span>

3. <span data-ttu-id="6a30e-118">생성 된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="6a30e-119">이 코드는 두 개의 자식 컨트롤을 포함 하는 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="6a30e-120">첫 번째 자식 컨트롤은 <xref:System.Windows.Controls.Label?displayProperty=nameWithType> 컨트롤입니다. 두 번째는 3D 원추를 표시 하는 <xref:System.Windows.Controls.Viewport3D> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="6a30e-121">호스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="6a30e-121">Create the host project</span></span>

1. <span data-ttu-id="6a30e-122">`WpfUserControlHost` 이라는 **Windows Forms 앱 (.NET Framework)** 프로젝트를 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-122">Add a **Windows Forms App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span>

2. <span data-ttu-id="6a30e-123">**솔루션 탐색기**에서 windows integration .Dll 이라는 windows양식 통합 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-123">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="6a30e-124">다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-124">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="6a30e-125">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="6a30e-125">PresentationCore</span></span>

    - <span data-ttu-id="6a30e-126">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="6a30e-126">PresentationFramework</span></span>

    - <span data-ttu-id="6a30e-127">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="6a30e-127">WindowsBase</span></span>

4. <span data-ttu-id="6a30e-128">`HostingWpfUserControlInWf` 프로젝트에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-128">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="6a30e-129">솔루션 탐색기에서 `WpfUserControlHost` 프로젝트를 시작 프로젝트로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-129">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="6a30e-130">UserControl 호스트</span><span class="sxs-lookup"><span data-stu-id="6a30e-130">Host the UserControl</span></span>

1. <span data-ttu-id="6a30e-131">Windows Forms 디자이너에서 Form1을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-131">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="6a30e-132">속성 창 **에서 이벤트를 클릭 한**다음 <xref:System.Windows.Forms.Form.Load> 이벤트를 두 번 클릭 하 여 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-132">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="6a30e-133">새로 생성 된 `Form1_Load` 이벤트 처리기에 대 한 코드 편집기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-133">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="6a30e-134">Form1.cs의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-134">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="6a30e-135">`Form1_Load` 이벤트 처리기는 `UserControl1` 인스턴스를 만들고 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 자식 컨트롤 컬렉션에 공장를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-135">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="6a30e-136"><xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 폼의 자식 컨트롤 컬렉션에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-136">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="6a30e-137">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6a30e-137">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a30e-138">참조</span><span class="sxs-lookup"><span data-stu-id="6a30e-138">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="6a30e-139">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="6a30e-139">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="6a30e-140">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="6a30e-140">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="6a30e-141">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="6a30e-141">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="6a30e-142">Windows Forms 샘플에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="6a30e-142">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)
