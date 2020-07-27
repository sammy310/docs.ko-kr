---
title: WPF에서 Windows Forms 컨트롤 호스팅
description: 이미 풍부한 기능 집합을 포함 하는 많은 컨트롤을 제공 하는 Windows Presentation Foundation에서 Windows Forms 컨트롤을 호스트 하는 방법을 알아봅니다.
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: ec67cf9fabaa5b7aadbb2a3c21ebf8dd828ee20f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164976"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a>연습: WPF에서 Windows Forms 컨트롤 호스팅

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 풍부한 기능 집합이 있는 많은 컨트롤을 제공합니다. 그러나 경우에 따라 페이지에서 Windows Forms 컨트롤을 사용 하는 것이 좋습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . 예를 들어 기존 Windows Forms 컨트롤에 상당한 투자가 있거나 고유한 기능을 제공 하는 Windows Forms 컨트롤이 있을 수 있습니다.

이 연습에서는 <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 코드를 사용 하 여 페이지에서 Windows Forms 컨트롤을 호스트 하는 방법을 보여 줍니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .

이 연습에 표시 된 작업의 전체 코드 목록은 [WPF에서 Windows Forms 컨트롤 호스팅 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF)을 참조 하세요.

## <a name="prerequisites"></a>필수 구성 요소

이 연습을 완료하려면 Visual Studio가 필요합니다.

## <a name="hosting-the-windows-forms-control"></a>Windows Forms 컨트롤 호스팅

### <a name="to-host-the-maskedtextbox-control"></a>MaskedTextBox 컨트롤을 호스트하려면

1. 이라는 WPF 응용 프로그램 프로젝트를 만듭니다 `HostingWfInWpf` .

2. 다음 어셈블리에 대한 참조를 추가합니다.

    - WindowsFormsIntegration

    - System.Windows.Forms

3. WPF 디자이너에서 Mainwindow.xaml를 엽니다.

4. 요소의 이름을 <xref:System.Windows.Controls.Grid> 로 `grid1` 합니다.

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. 디자인 뷰 또는 XAML 뷰에서 요소를 선택 <xref:System.Windows.Window> 합니다.

6. 속성 창에서 **이벤트** 탭을 클릭 합니다.

7. 이벤트를 두 번 클릭 <xref:System.Windows.FrameworkElement.Loaded> 합니다.

8. 다음 코드를 삽입 하 여 이벤트를 처리 <xref:System.Windows.FrameworkElement.Loaded> 합니다.

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. 파일 맨 위에 다음 `Imports` 또는 문을 추가 합니다 `using` .

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows Forms 컨트롤 및 해당 WPF 컨트롤](windows-forms-controls-and-equivalent-wpf-controls.md)
- [WPF에서 Windows Forms 컨트롤 호스팅 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF)
