---
title: '연습: WPF에서 Windows Forms 컨트롤 정렬'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: d2bd3a7d4b8e84542f1c5fa3dbb15f1a9753a180
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168586"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="8dfb6-102">연습: WPF에서 Windows Forms 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="8dfb6-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="8dfb6-103">이 연습에서는 사용 하는 방법을 보여 줍니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 정렬 레이아웃 기능 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 하이브리드 응용 프로그램에서 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="8dfb6-104">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="8dfb6-105">프로젝트 만들기.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="8dfb6-106">기본 레이아웃 설정 사용</span><span class="sxs-lookup"><span data-stu-id="8dfb6-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="8dfb6-107">콘텐츠에 맞게 크기 조정</span><span class="sxs-lookup"><span data-stu-id="8dfb6-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="8dfb6-108">절대 위치 사용</span><span class="sxs-lookup"><span data-stu-id="8dfb6-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="8dfb6-109">명시적으로 크기 지정</span><span class="sxs-lookup"><span data-stu-id="8dfb6-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="8dfb6-110">레이아웃 속성 설정</span><span class="sxs-lookup"><span data-stu-id="8dfb6-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="8dfb6-111">z 순서 제한 사항 이해</span><span class="sxs-lookup"><span data-stu-id="8dfb6-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="8dfb6-112">도킹</span><span class="sxs-lookup"><span data-stu-id="8dfb6-112">Docking.</span></span>  
  
-   <span data-ttu-id="8dfb6-113">표시 유형 설정</span><span class="sxs-lookup"><span data-stu-id="8dfb6-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="8dfb6-114">늘어나지 않는 컨트롤 호스트</span><span class="sxs-lookup"><span data-stu-id="8dfb6-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="8dfb6-115">배율 조정</span><span class="sxs-lookup"><span data-stu-id="8dfb6-115">Scaling.</span></span>  
  
-   <span data-ttu-id="8dfb6-116">회전</span><span class="sxs-lookup"><span data-stu-id="8dfb6-116">Rotating.</span></span>  
  
-   <span data-ttu-id="8dfb6-117">안쪽 여백 및 여백 설정</span><span class="sxs-lookup"><span data-stu-id="8dfb6-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="8dfb6-118">동적 레이아웃 컨테이너 사용</span><span class="sxs-lookup"><span data-stu-id="8dfb6-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="8dfb6-119">이 연습에 설명 된 작업의 전체 코드 목록은 참조 하세요 [WPF 샘플에서 Windows Forms 컨트롤 정렬](https://go.microsoft.com/fwlink/?LinkID=159971)합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="8dfb6-120">완료 되 면 하면 이해가 더 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 레이아웃 기능 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8dfb6-121">전제 조건</span><span class="sxs-lookup"><span data-stu-id="8dfb6-121">Prerequisites</span></span>  

<span data-ttu-id="8dfb6-122">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="creating-the-project"></a><span data-ttu-id="8dfb6-123">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="8dfb6-123">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="8dfb6-124">프로젝트를 만들고 설정하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-124">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="8dfb6-125">이라는 WPF 응용 프로그램 프로젝트를 만듭니다 `WpfLayoutHostingWf`합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2.  <span data-ttu-id="8dfb6-126">솔루션 탐색기에서 다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-126">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="8dfb6-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="8dfb6-127">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="8dfb6-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="8dfb6-128">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="8dfb6-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="8dfb6-129">System.Drawing</span></span>  
  
3.  <span data-ttu-id="8dfb6-130">MainWindow.xaml을 두 번 클릭하여 XAML 보기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-130">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4.  <span data-ttu-id="8dfb6-131">에 <xref:System.Windows.Window> 요소를 다음 추가 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 네임 스페이스 매핑.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="8dfb6-132">에 <xref:System.Windows.Controls.Grid> 요소 집합을 <xref:System.Windows.Controls.Grid.ShowGridLines%2A> 속성을 `true` 5 개의 행과 세 개의 열을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="8dfb6-133">기본 레이아웃 설정 사용</span><span class="sxs-lookup"><span data-stu-id="8dfb6-133">Using Default Layout Settings</span></span>  
 <span data-ttu-id="8dfb6-134">기본적으로 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 호스팅된에 대 한 레이아웃을 처리 하는 요소 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="8dfb6-135">기본 레이아웃 설정을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-135">To use default layout settings</span></span>  
  
1.  <span data-ttu-id="8dfb6-136">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  <span data-ttu-id="8dfb6-137">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-137">Press F5 to build and run the application.</span></span> <span data-ttu-id="8dfb6-138">합니다 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> 컨트롤에 표시 됩니다는 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="8dfb6-139">호스팅된 컨트롤이 해당 콘텐츠에 따라 크기가 및 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 호스트 된 컨트롤에 맞게 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="8dfb6-140">콘텐츠에 맞게 크기 조정</span><span class="sxs-lookup"><span data-stu-id="8dfb6-140">Sizing to Content</span></span>  
 <span data-ttu-id="8dfb6-141"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 호스트 된 컨트롤 크기가 조정 됩니다 해당 콘텐츠가 제대로 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="8dfb6-142">콘텐츠 크기를 조정하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-142">To size to content</span></span>  
  
1.  <span data-ttu-id="8dfb6-143">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  <span data-ttu-id="8dfb6-144">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-144">Press F5 to build and run the application.</span></span> <span data-ttu-id="8dfb6-145">더 긴 텍스트 문자열과 더 큰 글꼴 크기를 올바르게 표시 하려면 두 개의 새 단추 컨트롤 크기가 조정 되 고 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 호스트 된 컨트롤에 맞게 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="8dfb6-146">절대 위치 사용</span><span class="sxs-lookup"><span data-stu-id="8dfb6-146">Using Absolute Positioning</span></span>  
 <span data-ttu-id="8dfb6-147">절대 위치를 배치 하는 데 사용할 수는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 사용자 인터페이스 (UI)에 있는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="8dfb6-148">절대 위치를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-148">To use absolute positioning</span></span>  
  
1.  <span data-ttu-id="8dfb6-149">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  <span data-ttu-id="8dfb6-150">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-150">Press F5 to build and run the application.</span></span> <span data-ttu-id="8dfb6-151"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 표 형태 셀의 위쪽에서 20 픽셀 및 왼쪽에서 20 픽셀 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="8dfb6-152">명시적으로 크기 지정</span><span class="sxs-lookup"><span data-stu-id="8dfb6-152">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="8dfb6-153">크기를 지정할 수 있습니다 합니다 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 사용 하 여 요소를 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="8dfb6-154">명시적으로 크기를 지정하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-154">To specify size explicitly</span></span>  
  
1.  <span data-ttu-id="8dfb6-155">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  <span data-ttu-id="8dfb6-156">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-156">Press F5 to build and run the application.</span></span> <span data-ttu-id="8dfb6-157"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 기본 레이아웃 설정 보다 작은 요소 50 픽셀 x 높이 70 픽셀의 크기로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="8dfb6-158">콘텐츠는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 적절 하 게 다시 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="8dfb6-159">레이아웃 속성 설정</span><span class="sxs-lookup"><span data-stu-id="8dfb6-159">Setting Layout Properties</span></span>  
 <span data-ttu-id="8dfb6-160">항상의 속성을 사용 하 여 호스트 된 컨트롤에서 레이아웃 관련 속성을 설정 합니다 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="8dfb6-161">호스트된 컨트롤에서 직접 레이아웃 속성을 설정하면 의도하지 않은 결과가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="8dfb6-162">에 호스트 된 컨트롤에서 레이아웃 관련 속성을 설정 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="8dfb6-163">호스트된 컨트롤에서 속성 설정의 결과를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-163">To see the effects of setting properties on the hosted control</span></span>  
  
1.  <span data-ttu-id="8dfb6-164">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  <span data-ttu-id="8dfb6-165">솔루션 탐색기에서 MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-165">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="8dfb6-166">vb 또는 MainWindow.xaml.cs를 두 번 클릭하여 코드 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-166">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3.  <span data-ttu-id="8dfb6-167">다음 코드를 복사 합니다 `MainWindow` 클래스 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-167">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4.  <span data-ttu-id="8dfb6-168">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-168">Press F5 to build and run the application.</span></span>

5.  <span data-ttu-id="8dfb6-169">클릭 합니다 **Click me** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-169">Click the **Click me** button.</span></span> <span data-ttu-id="8dfb6-170">`button1_Click` 이벤트 처리기 설정 합니다 <xref:System.Windows.Forms.Control.Top%2A> 및 <xref:System.Windows.Forms.Control.Left%2A> 호스팅된 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-170">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="8dfb6-171">이렇게 하면 호스트 된 컨트롤 내의 위치를 변경할 수는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-171">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="8dfb6-172">호스트는 동일한 화면 영역을 유지하지만 호스트된 컨트롤은 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-172">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="8dfb6-173">호스팅된 컨트롤이 항상 채우는 대신는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-173">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="8dfb6-174">Z 순서 제한 사항 이해</span><span class="sxs-lookup"><span data-stu-id="8dfb6-174">Understanding Z-Order Limitations</span></span>
 <span data-ttu-id="8dfb6-175">표시 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 항상 다른 WPF 요소를 기반으로 그려지며 z-순서 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-175">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="8dfb6-176">이 z 순서 동작을 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-176">To see this z-order behavior, do the following:</span></span>

1.  <span data-ttu-id="8dfb6-177">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-177">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2.  <span data-ttu-id="8dfb6-178">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-178">Press F5 to build and run the application.</span></span> <span data-ttu-id="8dfb6-179"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 레이블 요소 위에 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-179">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="8dfb6-180">도킹</span><span class="sxs-lookup"><span data-stu-id="8dfb6-180">Docking</span></span>
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <span data-ttu-id="8dfb6-181">요소가 지 원하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-181">element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="8dfb6-182">설정 합니다 <xref:System.Windows.Controls.DockPanel.Dock%2A> 연결 된 속성에서 호스트 된 컨트롤을 도킹을 <xref:System.Windows.Controls.DockPanel> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-182">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="8dfb6-183">호스트된 컨트롤을 도킹하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-183">To dock a hosted control</span></span>

1.  <span data-ttu-id="8dfb6-184">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-184">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2.  <span data-ttu-id="8dfb6-185">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-185">Press F5 to build and run the application.</span></span> <span data-ttu-id="8dfb6-186">합니다 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 오른쪽에 도킹 됩니다는 <xref:System.Windows.Controls.DockPanel> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-186">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="8dfb6-187">표시 유형 설정</span><span class="sxs-lookup"><span data-stu-id="8dfb6-187">Setting Visibility</span></span>
 <span data-ttu-id="8dfb6-188">할 수 있습니다 프로그램 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 보이지 않거나 설정 하 여 축소 합니다 <xref:System.Windows.UIElement.Visibility%2A> 속성에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-188">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="8dfb6-189">컨트롤이 보이지 않으면 표시되지는 않지만 레이아웃 공간은 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-189">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="8dfb6-190">컨트롤이 축소되면 표시되지 않고 레이아웃 공간도 자치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-190">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="8dfb6-191">호스트된 컨트롤의 표시 유형을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-191">To set the visibility of a hosted control</span></span>

1.  <span data-ttu-id="8dfb6-192">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-192">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2.  <span data-ttu-id="8dfb6-193">MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 다음 코드를 클래스 정의에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-193">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3.  <span data-ttu-id="8dfb6-194">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-194">Press F5 to build and run the application.</span></span>

4.  <span data-ttu-id="8dfb6-195">클릭 합니다 **보이지 않도록 하려면 클릭** 단추를 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-195">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5.  <span data-ttu-id="8dfb6-196">클릭 합니다 **축소 하려면 클릭** 숨기려면 단추는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 레이아웃에서 완전히 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-196">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="8dfb6-197">경우는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 축소 되는 경우 해당 공간을 차지 하도록 주변 요소가 다시 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-197">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="8dfb6-198">늘어나지 않는 컨트롤 호스트</span><span class="sxs-lookup"><span data-stu-id="8dfb6-198">Hosting a Control That Does Not Stretch</span></span>
 <span data-ttu-id="8dfb6-199">일부 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 고정 크기 및 레이아웃에 사용 가능한 공간을 채우도록 늘어나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-199">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="8dfb6-200">예를 들어를 <xref:System.Windows.Forms.MonthCalendar> 컨트롤은 고정 된 공간에 월을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-200">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="8dfb6-201">늘어나지 않는 컨트롤을 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-201">To host a control that does not stretch</span></span>

1.  <span data-ttu-id="8dfb6-202">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-202">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2.  <span data-ttu-id="8dfb6-203">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-203">Press F5 to build and run the application.</span></span> <span data-ttu-id="8dfb6-204"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 그리드 행에서 가운데에 있지만 사용 가능한 공간을 채우도록 확장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-204">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="8dfb6-205">창이 충분히 큰 경우 호스팅된 하 여 표시 되는 월을 두 개 이상 표시 될 수 있습니다 <xref:System.Windows.Forms.MonthCalendar> 컨트롤 이지만 이러한 행에서 가운데 맞춤 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-205">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="8dfb6-206">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 엔진 센터 요소는 사용 가능한 공간에 맞게 크기를 조정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-206">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="8dfb6-207">배율 조정</span><span class="sxs-lookup"><span data-stu-id="8dfb6-207">Scaling</span></span>
 <span data-ttu-id="8dfb6-208">WPF 요소와는 달리 대부분의 Windows Forms 컨트롤은 지속적으로 확장 가능하지 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-208">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="8dfb6-209">사용자 지정 확장을 제공 하려면 재정의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-209">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="8dfb6-210">기본 동작을 사용하여 호스트된 컨트롤의 배율을 조정하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-210">To scale a hosted control by using the default behavior</span></span>

1.  <span data-ttu-id="8dfb6-211">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-211">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2.  <span data-ttu-id="8dfb6-212">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-212">Press F5 to build and run the application.</span></span> <span data-ttu-id="8dfb6-213">호스트된 컨트롤과 해당 주변 요소가 0.5의 비율로 배율 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-213">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="8dfb6-214">그러나 호스트된 컨트롤의 글꼴은 배율 조정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-214">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="8dfb6-215">회전</span><span class="sxs-lookup"><span data-stu-id="8dfb6-215">Rotating</span></span>
 <span data-ttu-id="8dfb6-216">WPF 요소와는 달리 Windows Forms 컨트롤 회전을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-216">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="8dfb6-217"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 회전 변환이 적용 될 때 다른 WPF 요소와 요소 회전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-217">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="8dfb6-218">180도 발생 이외의 모든 회전 값은 <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-218">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="8dfb6-219">혼합 애플리케이션에서 회전의 결과를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-219">To see the effect of rotation in a hybrid application</span></span>

1.  <span data-ttu-id="8dfb6-220">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-220">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2.  <span data-ttu-id="8dfb6-221">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-221">Press F5 to build and run the application.</span></span> <span data-ttu-id="8dfb6-222">호스트된 컨트롤은 회전되지 않지만 주변 요소는 180도 각도로 회전됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-222">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="8dfb6-223">요소를 표시하려면 창의 크기를 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-223">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="8dfb6-224">안쪽 여백 및 여백 설정</span><span class="sxs-lookup"><span data-stu-id="8dfb6-224">Setting Padding and Margins</span></span>
 <span data-ttu-id="8dfb6-225">안쪽 여백 및 여백을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃은 안쪽 여백 및 여백을 비슷합니다 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-225">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="8dfb6-226">설정 하기만 하면 됩니다는 <xref:System.Windows.Controls.Control.Padding%2A> 하 고 <xref:System.Windows.FrameworkElement.Margin%2A> 속성에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-226">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="8dfb6-227">호스트된 컨트롤에 대해 안쪽 여백 및 여백을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-227">To set padding and margins for a hosted control</span></span>

1.  <span data-ttu-id="8dfb6-228">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-228">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2.  <span data-ttu-id="8dfb6-229">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-229">Press F5 to build and run the application.</span></span> <span data-ttu-id="8dfb6-230">안쪽 여백 및 여백 설정이 적용 됩니다 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 적용할 수는 동일한 방식으로 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-230">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="8dfb6-231">동적 레이아웃 컨테이너 사용</span><span class="sxs-lookup"><span data-stu-id="8dfb6-231">Using Dynamic Layout Containers</span></span>
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <span data-ttu-id="8dfb6-232">두 개의 동적 레이아웃 컨테이너를 제공 <xref:System.Windows.Forms.FlowLayoutPanel> 고 <xref:System.Windows.Forms.TableLayoutPanel>입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-232">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="8dfb6-233">이러한 컨테이너를 사용할 수도 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-233">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="8dfb6-234">동적 레이아웃 컨테이너를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="8dfb6-234">To use a dynamic layout container</span></span>

1.  <span data-ttu-id="8dfb6-235">에 다음 XAML을 복사 합니다 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-235">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2.  <span data-ttu-id="8dfb6-236">MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 다음 코드를 클래스 정의에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-236">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3.  <span data-ttu-id="8dfb6-237">생성자에서 `InitializeFlowLayoutPanel` 메서드에 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-237">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  <span data-ttu-id="8dfb6-238">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="8dfb6-239"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 입력 합니다 <xref:System.Windows.Controls.DockPanel>, 및 <xref:System.Windows.Forms.FlowLayoutPanel> 기본에서 자식 컨트롤을 정렬 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfb6-239">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dfb6-240">참고자료</span><span class="sxs-lookup"><span data-stu-id="8dfb6-240">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="8dfb6-241">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="8dfb6-241">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="8dfb6-242">WindowsFormsHost 요소에 대한 레이아웃 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8dfb6-242">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="8dfb6-243">WPF 샘플에서 정렬 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8dfb6-243">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="8dfb6-244">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="8dfb6-244">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="8dfb6-245">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="8dfb6-245">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
