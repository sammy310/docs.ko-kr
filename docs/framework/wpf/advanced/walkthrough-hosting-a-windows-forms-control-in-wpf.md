---
title: WPF에서 Windows Forms 컨트롤 호스팅
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: 2ed4e153a2513dc99d22a1538399156c138eb9e5
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123833"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="99cc9-102">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="99cc9-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="99cc9-103">에서는 풍부한 기능 집합이 있는 많은 컨트롤을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="99cc9-104">그러나 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에서 Windows Forms 컨트롤을 사용 하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="99cc9-105">예를 들어 기존 Windows Forms 컨트롤에 상당한 투자가 있거나 고유한 기능을 제공 하는 Windows Forms 컨트롤이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>

<span data-ttu-id="99cc9-106">이 연습에서는 코드를 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에서 Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 컨트롤을 호스트 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="99cc9-107">이 연습에 표시 된 작업의 전체 코드 목록은 [WPF에서 Windows Forms 컨트롤 호스팅 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99cc9-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="99cc9-108">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="99cc9-108">Prerequisites</span></span>

<span data-ttu-id="99cc9-109">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="99cc9-110">Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="99cc9-110">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="99cc9-111">MaskedTextBox 컨트롤을 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="99cc9-111">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="99cc9-112">`HostingWfInWpf`이라는 WPF 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-112">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="99cc9-113">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-113">Add references to the following assemblies.</span></span>

    - <span data-ttu-id="99cc9-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="99cc9-114">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="99cc9-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="99cc9-115">System.Windows.Forms</span></span>

3. <span data-ttu-id="99cc9-116">WPF 디자이너에서 Mainwindow.xaml를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-116">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="99cc9-117"><xref:System.Windows.Controls.Grid> 요소의 이름을 `grid1`합니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-117">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="99cc9-118">디자인 뷰 또는 XAML 뷰에서 <xref:System.Windows.Window> 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-118">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="99cc9-119">속성 창에서 **이벤트** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-119">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="99cc9-120"><xref:System.Windows.FrameworkElement.Loaded> 이벤트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-120">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="99cc9-121"><xref:System.Windows.FrameworkElement.Loaded> 이벤트를 처리 하는 다음 코드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-121">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="99cc9-122">파일 맨 위에 다음 `Imports` 또는 `using` 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-122">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="99cc9-123">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="99cc9-123">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="99cc9-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99cc9-124">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="99cc9-125">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="99cc9-125">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="99cc9-126">연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="99cc9-126">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="99cc9-127">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="99cc9-127">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="99cc9-128">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="99cc9-128">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="99cc9-129">Windows Forms 컨트롤 및 해당 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="99cc9-129">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="99cc9-130">WPF에서 Windows Forms 컨트롤 호스팅 샘플</span><span class="sxs-lookup"><span data-stu-id="99cc9-130">Hosting a Windows Forms Control in WPF Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF)
