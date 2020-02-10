---
title: XAML을 사용 하 여 WPF에서 Windows Forms 컨트롤 호스팅
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 99c077801a26043e17e0d51ecc0a97b9608784c0
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095062"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="7c181-102">연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="7c181-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="7c181-103">에서는 풍부한 기능 집합이 있는 많은 컨트롤을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="7c181-104">그러나 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에서 Windows Forms 컨트롤을 사용 하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="7c181-105">예를 들어 기존 Windows Forms 컨트롤에 상당한 투자가 있거나 고유한 기능을 제공 하는 Windows Forms 컨트롤이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="7c181-106">이 연습에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에서 Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 컨트롤을 호스트 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="7c181-107">이 연습에 표시 된 작업의 전체 코드 목록은 [WPF에서 XAML을 사용 하 여 Windows Forms 컨트롤 호스팅 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c181-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="7c181-108">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7c181-108">Prerequisites</span></span>  

<span data-ttu-id="7c181-109">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="7c181-110">Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="7c181-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="7c181-111">MaskedTextBox 컨트롤을 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="7c181-111">To host the MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="7c181-112">`HostingWfInWpfWithXaml`이라는 WPF 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2. <span data-ttu-id="7c181-113">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-113">Add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="7c181-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="7c181-114">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="7c181-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="7c181-115">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="7c181-116">WPF 디자이너에서 Mainwindow.xaml를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-116">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
4. <span data-ttu-id="7c181-117"><xref:System.Windows.Window> 요소에서 다음 네임 스페이스 매핑을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="7c181-118">`wf` 네임 스페이스 매핑은 Windows Forms 컨트롤을 포함 하는 어셈블리에 대 한 참조를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="7c181-119"><xref:System.Windows.Controls.Grid> 요소에 다음 XAML을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="7c181-120"><xref:System.Windows.Forms.MaskedTextBox> 컨트롤은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤의 자식으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. <span data-ttu-id="7c181-121">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c181-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c181-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c181-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="7c181-123">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="7c181-123">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="7c181-124">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="7c181-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="7c181-125">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="7c181-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="7c181-126">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="7c181-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="7c181-127">Windows Forms 컨트롤 및 해당 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7c181-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="7c181-128">XAML 샘플을 사용 하 여 WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="7c181-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)
