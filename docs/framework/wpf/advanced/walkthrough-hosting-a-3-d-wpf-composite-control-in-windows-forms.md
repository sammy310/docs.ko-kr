---
title: Windows Forms에서 3D WPF 복합 컨트롤 호스팅
titleSuffix: ''
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: aaa726ac90fd75a12054c18be6ec08a1372c1128
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794206"
---
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a>연습: Windows Forms에서 3D WPF 복합 컨트롤 호스팅

이 연습에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤을 만들고 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 사용 하 여 Windows Forms 컨트롤과 폼에서 호스트 하는 방법을 보여 줍니다.

이 연습에서는 두 개의 자식 컨트롤을 포함 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>을 구현 합니다. <xref:System.Windows.Controls.UserControl> 3 차원 (3D) 원뿔을 표시 합니다. 3D 개체 렌더링은 Windows Forms 보다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용 하는 것이 훨씬 쉽습니다. 따라서 Windows Forms에서 3D 그래픽을 만들기 위해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 클래스를 호스트 하는 것이 좋습니다.

이 연습에서 설명하는 작업은 다음과 같습니다.

- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>만들기

- Windows Forms 호스트 프로젝트를 만듭니다.

- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>를 호스팅합니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 완료하려면 다음 구성 요소가 필요합니다.

- Visual Studio 2017

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a>UserControl 만들기

1. `HostingWpfUserControlInWf`이라는 **WPF 사용자 정의 컨트롤 라이브러리** 프로젝트를 만듭니다.

2. WPF 디자이너에서 UserControl1을 엽니다.

3. 생성 된 코드를 다음 코드로 바꿉니다.

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     이 코드는 두 개의 자식 컨트롤을 포함 하는 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>를 정의 합니다. 첫 번째 자식 컨트롤은 <xref:System.Windows.Controls.Label?displayProperty=nameWithType> 컨트롤입니다. 두 번째는 3D 원추를 표시 하는 <xref:System.Windows.Controls.Viewport3D> 컨트롤입니다.

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a>호스트 프로젝트 만들기

1. `WpfUserControlHost` 이라는 **Windows Forms 앱 (.NET Framework)** 프로젝트를 솔루션에 추가 합니다.

2. **솔루션 탐색기**에서 windows integration .Dll 이라는 windows양식 통합 어셈블리에 대 한 참조를 추가 합니다.

3. 다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리에 대 한 참조를 추가 합니다.

    - PresentationCore

    - PresentationFramework

    - WindowsBase

4. `HostingWpfUserControlInWf` 프로젝트에 대 한 참조를 추가 합니다.

5. 솔루션 탐색기에서 `WpfUserControlHost` 프로젝트를 시작 프로젝트로 설정 합니다.

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a>UserControl 호스트

1. Windows Forms 디자이너에서 Form1을 엽니다.

2. 속성 창 **에서 이벤트를 클릭 한**다음 <xref:System.Windows.Forms.Form.Load> 이벤트를 두 번 클릭 하 여 이벤트 처리기를 만듭니다.

     새로 생성 된 `Form1_Load` 이벤트 처리기에 대 한 코드 편집기가 열립니다.

3. Form1.cs의 코드를 다음 코드로 바꿉니다.

     `Form1_Load` 이벤트 처리기는 `UserControl1` 인스턴스를 만들고 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 자식 컨트롤 컬렉션에 공장를 추가 합니다. <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 폼의 자식 컨트롤 컬렉션에 추가 됩니다.

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Windows Forms 샘플에서 WPF 복합 컨트롤 호스팅](https://go.microsoft.com/fwlink/?LinkID=160001)
