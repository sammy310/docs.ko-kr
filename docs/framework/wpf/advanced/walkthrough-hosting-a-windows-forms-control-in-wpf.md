---
title: '연습: WPF에서 Windows Forms 컨트롤 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: 3cd01126e22927151f3c7fb08726c006c710dd34
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197918"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a>연습: WPF에서 Windows Forms 컨트롤 호스팅

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 풍부한 기능 집합이 있는 많은 컨트롤을 제공합니다. 그러나 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 사용 하려는 경우가 있습니다. 예를 들어 기존 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 상당한 투자가 있거나 고유한 기능을 제공 하는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 있을 수 있습니다.

이 연습에서는 코드를 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 컨트롤을 호스트 하는 방법을 보여 줍니다.

이 연습에 표시 된 작업의 전체 코드 목록은 [WPF에서 Windows Forms 컨트롤 호스팅 샘플](https://go.microsoft.com/fwlink/?LinkID=160057)을 참조 하세요.

## <a name="prerequisites"></a>Prerequisites

이 연습을 완료하려면 Visual Studio가 필요합니다.

## <a name="hosting-the-windows-forms-control"></a>Windows Forms 컨트롤 호스팅

### <a name="to-host-the-maskedtextbox-control"></a>MaskedTextBox 컨트롤을 호스트하려면

1. `HostingWfInWpf`이라는 WPF 응용 프로그램 프로젝트를 만듭니다.

2. 다음 어셈블리에 대한 참조를 추가합니다.

    - WindowsFormsIntegration

    - System.Windows.Forms

3. [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]에서 Mainwindow.xaml을 엽니다.

4. <xref:System.Windows.Controls.Grid> 요소의 이름을 `grid1`합니다.

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. 디자인 뷰 또는 XAML 뷰에서 <xref:System.Windows.Window> 요소를 선택 합니다.

6. 속성 창에서 **이벤트** 탭을 클릭 합니다.

7. <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 두 번 클릭 합니다.

8. <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 처리 하는 다음 코드를 삽입 합니다.

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. 파일 맨 위에 다음 `Imports` 또는 `using` 문을 추가 합니다.

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows Forms 컨트롤 및 해당 WPF 컨트롤](windows-forms-controls-and-equivalent-wpf-controls.md)
- [WPF에서 Windows Forms 컨트롤 호스팅 샘플](https://go.microsoft.com/fwlink/?LinkID=160057)
