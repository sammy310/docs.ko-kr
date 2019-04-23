---
title: '연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 10554145de9725bb4cfc655ed88195dce28d739c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59321616"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="37b7e-102">연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="37b7e-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="37b7e-103">에서는 풍부한 기능 집합이 있는 많은 컨트롤을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="37b7e-104">그러나 사용 하려는 경우에 따라 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="37b7e-105">예를 들어, 기존에 상당한 투자를 해야 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 또는 있습니다 있을 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 고유한 기능을 제공 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="37b7e-106">이 연습에서는 Windows Forms를 호스트 하는 방법을 보여 줍니다 <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지를 사용 하 여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="37b7e-107">이 연습에 나와 있는 작업의 전체 코드 목록은 참조 하세요 [XAML 예제를 사용 하 여 WPF에서 Windows Forms 컨트롤 호스팅](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)합니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="37b7e-108">전제 조건</span><span class="sxs-lookup"><span data-stu-id="37b7e-108">Prerequisites</span></span>  

<span data-ttu-id="37b7e-109">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="37b7e-110">Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="37b7e-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="37b7e-111">MaskedTextBox 컨트롤을 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="37b7e-111">To host the MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="37b7e-112">이라는 WPF 응용 프로그램 프로젝트를 만듭니다 `HostingWfInWpfWithXaml`합니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2. <span data-ttu-id="37b7e-113">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-113">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="37b7e-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="37b7e-114">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="37b7e-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="37b7e-115">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="37b7e-116">MainWindow.xaml을 엽니다는 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-116">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4. <span data-ttu-id="37b7e-117">에 <xref:System.Windows.Window> 요소를 다음 네임 스페이스 매핑을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="37b7e-118">`wf` 네임 스페이스 매핑 Windows Forms 컨트롤을 포함 하는 어셈블리에 대 한 참조를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="37b7e-119">에 <xref:System.Windows.Controls.Grid> 다음 XAML을 추가 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="37b7e-120">합니다 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤의 자식으로 생성 됩니다는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. <span data-ttu-id="37b7e-121">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="37b7e-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b7e-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="37b7e-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="37b7e-123">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="37b7e-123">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="37b7e-124">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="37b7e-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="37b7e-125">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="37b7e-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="37b7e-126">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="37b7e-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="37b7e-127">Windows Forms 컨트롤 및 해당 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="37b7e-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="37b7e-128">XAML 샘플을 사용 하 여 WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="37b7e-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160000)
