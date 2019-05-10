---
title: '방법: 하이브리드 애플리케이션에서 비주얼 스타일 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: 81a56c41d1aaa5924bb6ff1d3437000be412f886
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912442"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="68df9-102">방법: 하이브리드 애플리케이션에서 비주얼 스타일 사용</span><span class="sxs-lookup"><span data-stu-id="68df9-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="68df9-103">이 항목을 사용 하도록 설정 하는 방법을 보여 줍니다 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] 에서 비주얼 스타일을 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 에 호스트 된 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램.</span><span class="sxs-lookup"><span data-stu-id="68df9-103">This topic shows how to enable [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] visual styles on a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="68df9-104">응용 프로그램을 호출 하는 경우는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드를 대부분의 프로그램 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램에서 실행 될 때 컨트롤에서 시각적 스타일을 사용할지 자동으로 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls will automatically use visual styles when your application is run on [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].</span></span> <span data-ttu-id="68df9-105">자세한 내용은 [비주얼 스타일을 사용 하 여 컨트롤 렌더링](../../winforms/controls/rendering-controls-with-visual-styles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-105">For more information, see [Rendering Controls with Visual Styles](../../winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="68df9-106">이 항목에서 설명 된 작업의 전체 코드 목록은 참조 하세요 [하이브리드 응용 프로그램 샘플에서 비주얼 스타일 사용](https://go.microsoft.com/fwlink/?LinkID=159986)합니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="68df9-107">Windows Forms 시각적 스타일 사용</span><span class="sxs-lookup"><span data-stu-id="68df9-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="68df9-108">Windows Forms 시각적 스타일을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="68df9-108">To enable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="68df9-109">만들기는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 라는 응용 프로그램 프로젝트 `HostingWfWithVisualStyles`합니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2. <span data-ttu-id="68df9-110">솔루션 탐색기에서 다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="68df9-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="68df9-111">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="68df9-112">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="68df9-112">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="68df9-113">도구 상자에서 두 번 클릭 합니다 <xref:System.Windows.Controls.Grid> 아이콘을를 <xref:System.Windows.Controls.Grid> 디자인 화면의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4. <span data-ttu-id="68df9-114">속성 창에서 값을 설정 합니다 <xref:System.Windows.FrameworkElement.Height%2A> 하 고 <xref:System.Windows.FrameworkElement.Width%2A> 속성을 **자동**합니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5. <span data-ttu-id="68df9-115">디자인 뷰 또는 XAML 뷰에서 선택 된 <xref:System.Windows.Window>합니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6. <span data-ttu-id="68df9-116">속성 창에서 클릭 합니다 **이벤트** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-116">In the Properties window, click the **Events** tab.</span></span>  
  
7. <span data-ttu-id="68df9-117">두 번 클릭 하 여 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8. <span data-ttu-id="68df9-118">MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 다음 코드를 처리 하는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="68df9-119">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="68df9-120">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 비주얼 스타일으로 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-120">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="68df9-121">Windows Forms 시각적 스타일 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="68df9-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="68df9-122">비주얼 스타일을 사용 하지 않으려면 단순히 호출을 제거 합니다 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="68df9-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="68df9-123">Windows Forms 시각적 스타일을 사용하지 않으려면</span><span class="sxs-lookup"><span data-stu-id="68df9-123">To disable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="68df9-124">코드 편집기에서 MainWindow.xaml.vb 또는 MainWindow.xaml.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2. <span data-ttu-id="68df9-125">에 대 한 호출을 주석은 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="68df9-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3. <span data-ttu-id="68df9-126">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="68df9-127">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 기본 시스템 스타일으로 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="68df9-127">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68df9-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="68df9-128">See also</span></span>

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="68df9-129">비주얼 스타일을 사용하여 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="68df9-129">Rendering Controls with Visual Styles</span></span>](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [<span data-ttu-id="68df9-130">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="68df9-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
