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
ms.openlocfilehash: 251c53a8665d2eae7c3b5bb23b0a388009362dcc
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960117"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>방법: 혼합 애플리케이션에서 비주얼 스타일 사용
이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 프로그램에서 호스팅되는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서 비주얼 스타일을 사용 하도록 설정 하는 방법을 보여 줍니다.  
  
 응용 프로그램이 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드를 호출 하는 경우 대부분의 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 자동으로 비주얼 스타일을 사용 합니다. 자세한 내용은 [비주얼 스타일을 사용 하 여 컨트롤 렌더링](../../winforms/controls/rendering-controls-with-visual-styles.md)합니다.  
  
 이 항목에서 설명 하는 작업의 전체 코드 목록은 [하이브리드 응용 프로그램에서 비주얼 스타일 사용 샘플](https://go.microsoft.com/fwlink/?LinkID=159986)을 참조 하세요.  
  
## <a name="enabling-windows-forms-visual-styles"></a>Windows Forms 시각적 스타일 사용  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>Windows Forms 시각적 스타일을 사용하려면  
  
1. `HostingWfWithVisualStyles`이라는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 프로젝트를 만듭니다.  
  
2. 솔루션 탐색기에서 다음 어셈블리에 대한 참조를 추가합니다.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. 도구 상자에서 <xref:System.Windows.Controls.Grid> 아이콘을 두 번 클릭 하 여 디자인 화면에 <xref:System.Windows.Controls.Grid> 요소를 놓습니다.  
  
4. 속성 창에서 <xref:System.Windows.FrameworkElement.Height%2A>의 값을 설정 하 고 속성을 <xref:System.Windows.FrameworkElement.Width%2A> **자동**으로 설정 합니다.  
  
5. 디자인 뷰 또는 XAML 뷰에서 <xref:System.Windows.Window>를 선택 합니다.  
  
6. 속성 창에서 **이벤트** 탭을 클릭 합니다.  
  
7. <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 두 번 클릭 합니다.
  
8. Mainwindow.xaml 또는 MainWindow.xaml.cs에서 다음 코드를 삽입 하 여 <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 처리 합니다.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
     비주얼 스타일을 사용 하 여 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 그립니다.  
  
## <a name="disabling-windows-forms-visual-styles"></a>Windows Forms 시각적 스타일 사용 안 함  
 비주얼 스타일을 사용 하지 않도록 설정 하려면 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드에 대 한 호출을 제거 하면 됩니다.  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>Windows Forms 시각적 스타일을 사용하지 않으려면  
  
1. 코드 편집기에서 MainWindow.xaml.vb 또는 MainWindow.xaml.cs를 엽니다.  
  
2. <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드에 대 한 호출을 주석으로 처리 합니다.  
  
3. F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
     [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 기본 시스템 스타일로 그려집니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [비주얼 스타일을 사용하여 컨트롤 렌더링](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [연습: WPF에서 Windows Forms 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
