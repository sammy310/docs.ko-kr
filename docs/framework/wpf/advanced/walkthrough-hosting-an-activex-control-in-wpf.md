---
title: '연습: WPF에서 ActiveX 컨트롤 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 959bc7942eaae91c0a7a72124f6ab1ab92a3553f
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040831"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a>연습: WPF에서 ActiveX 컨트롤 호스팅
브라우저와의 상호 작용을 개선 하기 위해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 프로그램에서 Microsoft ActiveX 컨트롤을 사용할 수 있습니다. 이 연습에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지의 컨트롤로 Microsoft Windows Media Player를 호스트 하는 방법을 보여 줍니다.

 이 연습에서 설명하는 작업은 다음과 같습니다.

- 프로젝트 만들기.

- ActiveX 컨트롤을 만듭니다.

- WPF 페이지에서 ActiveX 컨트롤 호스팅

 이 연습을 완료 하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 프로그램에서 Microsoft ActiveX 컨트롤을 사용 하는 방법을 이해 하 게 됩니다.

## <a name="prerequisites"></a>Prerequisites
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.

- Visual Studio가 설치 된 컴퓨터에 Microsoft Windows Media Player 설치 되어 있습니다.

- Visual Studio 2010

## <a name="creating-the-project"></a>프로젝트 만들기

### <a name="to-create-and-set-up-the-project"></a>프로젝트를 만들고 설정하려면

1. `HostingAxInWpf`이라는 WPF 응용 프로그램 프로젝트를 만듭니다.

2. Windows Forms 컨트롤 라이브러리 프로젝트를 솔루션에 추가 하 고 프로젝트 이름을 `WmpAxLib`합니다.

3. WmpAxLib 프로젝트에서 이름이 wmp 인 Windows Media Player 어셈블리에 대 한 참조를 추가 합니다.

4. **도구 상자**를 엽니다.

5. **도구 상자**를 마우스 오른쪽 단추로 클릭 한 다음 **항목 선택**을 클릭 합니다.

6. **COM 구성 요소** 탭을 클릭 하 고 **Windows Media Player** 컨트롤을 선택한 다음 **확인**을 클릭 합니다.

     Windows Media Player 컨트롤이 **도구 상자**에 추가 됩니다.

7. 솔루션 탐색기에서 **UserControl1** 파일을 마우스 오른쪽 단추로 클릭 한 다음 **이름 바꾸기**를 클릭 합니다.

8. 언어에 따라 이름을 `WmpAxControl.vb` 또는 `WmpAxControl.cs`로 변경 합니다.

9. 모든 참조의 이름을 바꾸라는 메시지가 표시 되 면 **예**를 클릭 합니다.

## <a name="creating-the-activex-control"></a>ActiveX 컨트롤 만들기
Visual Studio는 컨트롤이 디자인 화면에 추가 될 때 Microsoft ActiveX 컨트롤에 대 한 <xref:System.Windows.Forms.AxHost> 래퍼 클래스를 자동으로 생성 합니다. 다음 절차에서는 AxInterop 라는 관리 되는 어셈블리를 만듭니다.

### <a name="to-create-the-activex-control"></a>ActiveX 컨트롤을 만들려면

1. Windows Forms 디자이너에서 WmpAxControl 또는 WmpAxControl.cs를 엽니다.

2. **도구 상자**에서 Windows Media Player 컨트롤을 디자인 화면에 추가 합니다.

3. 속성 창에서 Windows Media Player 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성 값을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정 합니다.

4. WmpAxLib 컨트롤 라이브러리 프로젝트를 빌드합니다.

## <a name="hosting-the-activex-control-on-a-wpf-page"></a>WPF 페이지에서 ActiveX 컨트롤 호스팅

### <a name="to-host-the-activex-control"></a>ActiveX 컨트롤을 호스팅하려면

1. HostingAxInWpf 프로젝트에서 생성 된 ActiveX 상호 운용성 어셈블리에 대 한 참조를 추가 합니다.

     이 어셈블리의 이름은 WMPLib이 고 Windows Media Player 컨트롤을 가져올 때 WmpAxLib 프로젝트의 Debug 폴더에 추가 되었습니다.

2. Windows양식 통합 어셈블리에 참조를 추가 합니다 .이 어셈블리에는 Windows Integration .dll 이라는 이름이 지정 됩니다.

3. 이름이 System.object 인 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 어셈블리에 대 한 참조를 추가 합니다.

4. WPF 디자이너에서 Mainwindow.xaml를 엽니다.

5. <xref:System.Windows.Controls.Grid> 요소의 이름을 `grid1`합니다.

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. 디자인 뷰 또는 XAML 뷰에서 <xref:System.Windows.Window> 요소를 선택 합니다.

7. 속성 창에서 **이벤트** 탭을 클릭 합니다.

8. <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 두 번 클릭 합니다.

9. <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 처리 하는 다음 코드를 삽입 합니다.

     이 코드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤의 인스턴스를 만들고 `AxWindowsMediaPlayer` 컨트롤의 인스턴스를 자식으로 추가 합니다.

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Visual Studio에서 XAML 디자인](/visualstudio/designers/designing-xaml-in-visual-studio)
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
