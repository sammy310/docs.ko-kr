---
title: '방법: 혼합 애플리케이션에서 비주얼 스타일 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: dd52313e9100f9c6a1141b53ccc5a23a4b54410a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789915"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="71ff9-102">방법: 혼합 애플리케이션에서 비주얼 스타일 사용</span><span class="sxs-lookup"><span data-stu-id="71ff9-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="71ff9-103">이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 프로그램에서 호스팅되는 Windows Forms 컨트롤에서 비주얼 스타일을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-103">This topic shows how to enable visual styles on a Windows Forms control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="71ff9-104">응용 프로그램이 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드를 호출 하는 경우 대부분의 Windows Forms 컨트롤은 자동으로 비주얼 스타일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your Windows Forms controls will automatically use visual styles.</span></span> <span data-ttu-id="71ff9-105">자세한 내용은 [비주얼 스타일을 사용 하 여 컨트롤 렌더링](../../winforms/controls/rendering-controls-with-visual-styles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-105">For more information, see [Rendering Controls with Visual Styles](../../winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="71ff9-106">이 항목에서 설명 하는 작업의 전체 코드 목록은 [하이브리드 응용 프로그램에서 비주얼 스타일 사용 샘플](https://go.microsoft.com/fwlink/?LinkID=159986)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="71ff9-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="71ff9-107">Windows Forms 시각적 스타일 사용</span><span class="sxs-lookup"><span data-stu-id="71ff9-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="71ff9-108">Windows Forms 시각적 스타일을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="71ff9-108">To enable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="71ff9-109">`HostingWfWithVisualStyles`이라는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2. <span data-ttu-id="71ff9-110">솔루션 탐색기에서 다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="71ff9-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="71ff9-111">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="71ff9-112">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="71ff9-112">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="71ff9-113">도구 상자에서 <xref:System.Windows.Controls.Grid> 아이콘을 두 번 클릭 하 여 디자인 화면에 <xref:System.Windows.Controls.Grid> 요소를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4. <span data-ttu-id="71ff9-114">속성 창에서 <xref:System.Windows.FrameworkElement.Height%2A>의 값을 설정 하 고 속성을 <xref:System.Windows.FrameworkElement.Width%2A> **자동**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5. <span data-ttu-id="71ff9-115">디자인 뷰 또는 XAML 뷰에서 <xref:System.Windows.Window>를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6. <span data-ttu-id="71ff9-116">속성 창에서 **이벤트** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-116">In the Properties window, click the **Events** tab.</span></span>  
  
7. <span data-ttu-id="71ff9-117"><xref:System.Windows.FrameworkElement.Loaded> 이벤트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8. <span data-ttu-id="71ff9-118">Mainwindow.xaml 또는 MainWindow.xaml.cs에서 다음 코드를 삽입 하 여 <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="71ff9-119">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="71ff9-120">비주얼 스타일을 사용 하 여 Windows Forms 컨트롤을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-120">The Windows Forms control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="71ff9-121">Windows Forms 시각적 스타일 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="71ff9-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="71ff9-122">비주얼 스타일을 사용 하지 않도록 설정 하려면 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드에 대 한 호출을 제거 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="71ff9-123">Windows Forms 시각적 스타일을 사용하지 않으려면</span><span class="sxs-lookup"><span data-stu-id="71ff9-123">To disable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="71ff9-124">코드 편집기에서 MainWindow.xaml.vb 또는 MainWindow.xaml.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2. <span data-ttu-id="71ff9-125"><xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드에 대 한 호출을 주석으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3. <span data-ttu-id="71ff9-126">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="71ff9-127">Windows Forms 컨트롤은 기본 시스템 스타일로 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="71ff9-127">The Windows Forms control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ff9-128">참조</span><span class="sxs-lookup"><span data-stu-id="71ff9-128">See also</span></span>

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="71ff9-129">비주얼 스타일을 사용하여 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="71ff9-129">Rendering Controls with Visual Styles</span></span>](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [<span data-ttu-id="71ff9-130">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="71ff9-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
