---
title: '연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 10596f3ec89a5dc8bb7c20274b697d2592ad93d5
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197882"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 풍부한 기능 집합이 있는 많은 컨트롤을 제공합니다. 그러나 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 사용 하려는 경우가 있습니다. 예를 들어 기존 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 상당한 투자가 있거나 고유한 기능을 제공 하는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 있을 수 있습니다.  
  
 이 연습에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에서 Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 컨트롤을 호스트 하는 방법을 보여 줍니다.  
  
 이 연습에 표시 된 작업의 전체 코드 목록은 [WPF에서 XAML을 사용 하 여 Windows Forms 컨트롤 호스팅 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)을 참조 하세요.
  
## <a name="prerequisites"></a>Prerequisites  

이 연습을 완료하려면 Visual Studio가 필요합니다.  
  
## <a name="hosting-the-windows-forms-control"></a>Windows Forms 컨트롤 호스팅  
  
#### <a name="to-host-the-maskedtextbox-control"></a>MaskedTextBox 컨트롤을 호스트하려면  
  
1. `HostingWfInWpfWithXaml`이라는 WPF 응용 프로그램 프로젝트를 만듭니다.  
  
2. 다음 어셈블리에 대한 참조를 추가합니다.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]에서 Mainwindow.xaml을 엽니다.  
  
4. <xref:System.Windows.Window> 요소에서 다음 네임 스페이스 매핑을 추가 합니다. `wf` 네임 스페이스 매핑은 Windows Forms 컨트롤을 포함 하는 어셈블리에 대 한 참조를 설정 합니다.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <xref:System.Windows.Controls.Grid> 요소에 다음 XAML을 추가 합니다.  
  
     <xref:System.Windows.Forms.MaskedTextBox> 컨트롤은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤의 자식으로 생성 됩니다.  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [연습: WPF에서 Windows Forms 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows Forms 컨트롤 및 해당 WPF 컨트롤](windows-forms-controls-and-equivalent-wpf-controls.md)
- [XAML 샘플을 사용 하 여 WPF에서 Windows Forms 컨트롤 호스팅](https://go.microsoft.com/fwlink/?LinkID=160000)
