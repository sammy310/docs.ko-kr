---
title: Windows 양식에서 WPF 복합 컨트롤 호스트
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: 88efab8adf36989938ba5aa887a28b41eb8820f3
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291631"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>연습: Windows Forms에서 WPF 복합 컨트롤 호스팅
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 애플리케이션을 만들기 위한 다양한 환경을 제공합니다. 그러나 Windows Forms 코드에 상당한 투자가 있는 경우 처음부터 다시 작성하는 대신 기존 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Windows Forms 응용 프로그램을 확장하는 것이 더 효과적일 수 있습니다. 일반적인 시나리오는 Windows Forms 응용 프로그램 내에서 구현된 하나 이상의 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 포함하려는 경우입니다. WPF 컨트롤 사용자 지정에 대한 자세한 내용은 [사용자 지정 제어](../controls/control-customization.md)를 참조하십시오.  
  
 이 연습에서는 Windows Forms 응용 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그램에서 데이터 입력을 수행하기 위해 복합 컨트롤을 호스트하는 응용 프로그램을 단계적시입니다. 복합 컨트롤은 DLL로 패키지됩니다. 이 일반적인 절차는 더 복잡한 애플리케이션 및 컨트롤로 확장할 수 있습니다. 이 연습은 [WPF에서 Windows 양식 복합 컨트롤 을 호스팅하는 연습과](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)모양 및 기능이 거의 동일하도록 설계되었습니다. 주요 차이점은 호스팅 시나리오가 반대라는 점입니다.  
  
 이 연습은 두 개의 섹션으로 구분됩니다. 첫 번째 섹션에서는 복합 제어의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현에 대해 간략하게 설명합니다. 두 번째 섹션에서는 Windows Forms 응용 프로그램에서 복합 컨트롤을 호스트하고, 컨트롤에서 이벤트를 수신하고, 컨트롤의 일부 속성에 액세스하는 방법에 대해 자세히 설명합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
- WPF 복합 컨트롤 구현  
  
- Windows Forms 호스트 애플리케이션 구현  
  
 이 연습에 설명된 작업의 전체 코드 목록은 [Windows 양식 샘플에서 WPF 복합 제어 호스팅을](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl)참조하십시오.  
  
## <a name="prerequisites"></a>사전 요구 사항  

이 연습을 완료하려면 Visual Studio가 필요합니다.  
  
## <a name="implementing-the-wpf-composite-control"></a>WPF 복합 컨트롤 구현  
 이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 예제에서 사용되는 복합 컨트롤은 사용자의 이름과 주소를 사용하는 간단한 데이터 입력 양식입니다. 사용자가 작업이 완료되었음을 나타내는 두 개의 단추 중 하나를 클릭하면 컨트롤에서 사용자 지정 이벤트가 발생하여 해당 정보가 호스트에 반환됩니다. 다음 그림에서는 렌더링된 컨트롤을 보여 줍니다.

 다음 이미지는 WPF 복합 컨트롤을 보여 주며, 다음 이미지는 다음과 같은

 ![간단한 WPF 컨트롤을 보여 주는 스크린샷입니다.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-presentation-foundation-composite-control.png)  
  
### <a name="creating-the-project"></a>프로젝트 만들기  
 프로젝트를 시작하려면  
  
1. 시각적 스튜디오를 실행하고 **새 프로젝트** 대화 상자를 엽니다.  
  
2. 시각적 C# 및 Windows 범주에서 **WPF 사용자 제어 라이브러리** 템플릿을 선택합니다.  
  
3. 새 프로젝트의 이름을 `MyControls`로 지정합니다.  
  
4. 위치의 경우 와 같이 `WindowsFormsHostingWpfControl`편리하게 명명된 최상위 폴더를 지정합니다. 나중에 이 폴더에 호스트 애플리케이션을 넣습니다.  
  
5. **확인**을 클릭하여 프로젝트를 만듭니다. 기본 프로젝트에는 .라는 `UserControl1`단일 컨트롤이 포함되어 있습니다.  
  
6. 솔루션 탐색기에서 `UserControl1` 이름을 `MyControl1`로 변경합니다.  
  
 프로젝트에는 다음과 같은 시스템 DLL에 대한 참조가 있어야 합니다. 이러한 DLL이 기본적으로 포함되지 않은 경우 프로젝트에 추가합니다.  
  
- PresentationCore  
  
- PresentationFramework  
  
- 시스템  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>사용자 인터페이스 만들기  
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 복합 컨트롤에 대한 컨트롤이 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]구현됩니다. 복합 컨트롤은 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 5개의 <xref:System.Windows.Controls.TextBox> 요소로 구성됩니다. 각 <xref:System.Windows.Controls.TextBox> 요소에는 <xref:System.Windows.Controls.TextBlock> 레이블 역할을 하는 관련 요소가 있습니다. 하단에는 <xref:System.Windows.Controls.Button> **확인** 및 **취소의**두 가지 요소가 있습니다. 사용자가 이 단추 중 하나를 클릭하면 컨트롤에서 사용자 지정 이벤트가 발생하여 호스트에 정보가 반환됩니다.  
  
#### <a name="basic-layout"></a>기본 레이아웃  
 다양한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소가 <xref:System.Windows.Controls.Grid> 요소에 포함되어 있습니다. HTML에서 <xref:System.Windows.Controls.Grid> 요소를 사용하는 것과 거의 동일한 방식으로 복합 컨트롤의 내용을 `Table` 정렬하는 데 사용할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]또한 <xref:System.Windows.Documents.Table> 요소가 있지만 <xref:System.Windows.Controls.Grid> 더 가볍고 간단한 레이아웃 작업에 더 적합합니다.  
  
 다음 XAML에서는 기본 레이아웃을 보여 줍니다. 이 XAML은 <xref:System.Windows.Controls.Grid> 요소의 열 및 행 수를 지정하여 컨트롤의 전체 구조를 정의합니다.  
  
 MyControl1.xaml에서 기존 XAML을 다음 XAML로 바꿉니다.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>그리드에 TextBlock 및 TextBox 요소 추가  
 <xref:System.Windows.Controls.Grid.RowProperty> 요소및속성을적절한행및열번호로설정하여격자에요소를배치합니다. <xref:System.Windows.Controls.Grid.ColumnProperty> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 행 및 열 번호는 0부터 시작해야 합니다. <xref:System.Windows.Controls.Grid.ColumnSpanProperty> 해당 특성을 설정하여 여러 열에 걸쳐 있는 요소를 가질 수 있습니다. 요소에 대한 <xref:System.Windows.Controls.Grid> 자세한 내용은 [그리드 요소 만들기](../controls/how-to-create-a-grid-element.md)를 참조하십시오.  
  
 다음 XAML은 그리드에 요소를 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBlock> 올바르게 배치하도록 설정된 복합 <xref:System.Windows.Controls.Grid.RowProperty> 컨트롤및 해당 요소와 <xref:System.Windows.Controls.Grid.ColumnProperty> 특성을 포함하는 요소를 보여 주었습니다.  
  
 MyControl1.xaml에서 요소 내에 다음 XAML을 추가합니다. <xref:System.Windows.Controls.Grid>  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>UI 요소 스타일 지정  
 데이터 입력 폼의 요소는 대부분 모양이 비슷합니다. 즉, 이러한 요소의 여러 속성 설정이 동일합니다. 이전 XAML에서는 각 요소의 특성을 별도로 설정하는 <xref:System.Windows.Style> 대신 요소를 사용하여 요소 클래스에 대한 표준 속성 설정을 정의합니다. 이 방법을 사용하면 컨트롤의 복잡도를 줄이고 하나의 스타일 특성을 통해 여러 요소의 모양을 변경할 수 있습니다.  
  
 <xref:System.Windows.Style> 요소는 요소의 속성에 <xref:System.Windows.Controls.Grid> 포함되므로 컨트롤의 <xref:System.Windows.FrameworkElement.Resources%2A> 모든 요소에서 사용할 수 있습니다. 스타일 이름이 지정되면 스타일 이름에 요소 집합을 <xref:System.Windows.Style> 추가하여 요소에 적용합니다. 이름이 지정되지 않은 스타일은 요소의 기본 스타일이 됩니다. 스타일에 대한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 자세한 내용은 [스타일 지정 및 템플릿을](../../../desktop-wpf/fundamentals/styles-templates-overview.md)참조하십시오.  
  
 다음 XAML은 <xref:System.Windows.Style> 복합 컨트롤의 요소를 보여 주어집니다. 스타일이 요소에 어떻게 적용되는지 확인하려면 앞의 XAML을 참조하세요. 예를 들어 마지막 <xref:System.Windows.Controls.TextBlock> 요소에는 `inlineText` 스타일이 있고 <xref:System.Windows.Controls.TextBox> 마지막 요소에는 기본 스타일을 사용합니다.  
  
 MyControl1.xaml에서 시작 요소 바로 다음에 다음 <xref:System.Windows.Controls.Grid> XAML을 추가합니다.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>확인 및 취소 단추 추가  
 복합 컨트롤의 마지막 <xref:System.Windows.Controls.Grid>요소는 **의** 마지막 행의 처음 두 열을 차지하는 확인 및 **취소** <xref:System.Windows.Controls.Button> 요소입니다. 이러한 요소는 공통 이벤트 `ButtonClicked`처리기 및 <xref:System.Windows.Controls.Button> 이전 XAML에 정의된 기본 스타일을 사용합니다.  
  
 MyControl1.xaml에서 마지막 <xref:System.Windows.Controls.TextBox> 요소 다음에 다음 XAML을 추가합니다. 이제 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 복합 컨트롤의 일부가 완료되었습니다.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>코드 숨김 파일 구현  
 코드 숨결 파일인 MyControl1.xaml.cs 다음 세 가지 필수 작업을 구현합니다.
  
1. 사용자가 단추 중 하나를 클릭할 때 발생하는 이벤트를 처리합니다.  
  
2. <xref:System.Windows.Controls.TextBox> 요소에서 데이터를 검색 하 고 사용자 지정 이벤트 인수 개체에 패키지를 지정 합니다.  
  
3. 사용자가 완료된 호스트에 데이터를 다시 호스트로 전달하는 사용자 지정 `OnButtonClick` 이벤트를 발생시면 됩니다.  
  
 또한 컨트롤에서는 모양을 변경하는 데 사용할 수 있는 많은 수의 색 및 글꼴 속성을 노출합니다. Windows <xref:System.Windows.Forms.Integration.WindowsFormsHost> Forms 컨트롤을 호스트하는 데 사용되는 클래스와 달리 클래스는 <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Controls.Panel.Background%2A> 컨트롤의 속성만 노출합니다. 이 코드 예제와 연습에서 설명하는 예제 간의 유사성을 유지하려면 [WPF에서 Windows Forms 복합 제어를 호스팅하면](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)컨트롤은 나머지 속성을 직접 노출합니다.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>코드 숨김 파일의 기본 구조  
 코드 숨는 파일은 두 개의 `MyControls`클래스를 포함하는 단일 `MyControl1` 네임스페이스 및 `MyControlEventArgs`으로 구성됩니다.  
  
```csharp  
namespace MyControls  
{  
  public partial class MyControl1 : Grid  
  {  
    //...  
  }  
  public class MyControlEventArgs : EventArgs  
  {  
    //...  
  }  
}  
```  
  
 첫 번째 `MyControl1`클래스는 MyControl1.xaml에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 정의된 기능을 구현하는 코드를 포함하는 부분 클래스입니다. MyControl1.xaml이 구문 분석되면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 동일한 부분 클래스로 변환되고 두 부분 클래스가 병합되어 컴파일된 컨트롤을 형성합니다. 따라서 코드 숨김 파일의 클래스 이름이 MyControl1.xaml에 할당된 클래스 이름과 일치해야 하며 컨트롤의 루트 요소에서 상속되어야 합니다. 두 번째 `MyControlEventArgs`클래스는 데이터를 호스트로 다시 보내는 데 사용되는 이벤트 인수 클래스입니다.  
  
 MyControl1.xaml.cs를 엽니다. 다음 이름을 가지고 에서 <xref:System.Windows.Controls.Grid>상속되도록 기존 클래스 선언을 변경합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>컨트롤 초기화  
 다음 코드에서는 다음과 같은 몇 가지 기본 작업을 구현합니다.  
  
- 개인 이벤트 및 `OnButtonClick`관련 대리자를 `MyControlEventHandler`선언합니다.  
  
- 사용자 데이터를 저장하는 여러 private 전역 변수를 만듭니다. 이 데이터는 해당 속성을 통해 노출됩니다.  
  
- 컨트롤의 이벤트에 `Init`대 한 처리기 <xref:System.Windows.FrameworkElement.Loaded> , 을 구현 합니다. 이 처리기에서는 MyControl1.xaml에 정의된 값을 할당하여 전역 변수를 초기화합니다. 이렇게 하려면 일반적인 <xref:System.Windows.FrameworkElement.Name%2A> <xref:System.Windows.Controls.TextBlock> 요소에 할당된 `nameLabel`을 사용하여 해당 요소의 속성 설정에 액세스합니다.  
  
 기존 생성자 삭제 하고 클래스에 `MyControl1` 다음 코드를 추가 합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>단추의 클릭 이벤트 처리  
 사용자는 **확인** 단추 또는 **취소** 단추를 클릭하여 데이터 입력 작업이 완료되었음을 나타냅니다. 두 단추모두 동일한 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 `ButtonClicked`처리기를 사용합니다. 두 단추모두 `btnOK` `btnCancel` `sender` 인수 값을 검사하여 클릭한 단추를 처리자가 확인할 수 있는 이름이 나 을 가있습니다. 처리기에서는 다음 작업을 수행합니다.  
  
- 요소의 `MyControlEventArgs` 데이터를 포함하는 개체를 <xref:System.Windows.Controls.TextBox> 만듭니다.  
  
- 사용자가 **취소** 단추를 클릭한 경우 `MyControlEventArgs` 개체의 `IsOK` 속성을 `false`로 설정합니다.  
  
- `OnButtonClick` 이벤트가 호스트에 사용자가 완료되었음을 나타내고 수집된 데이터를 다시 전달합니다.  
  
 메서드 다음에 클래스에 `MyControl1` 다음 코드를 `Init` 추가합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>속성 만들기  
 클래스의 나머지 부분에서는 위에서 설명한 전역 변수에 해당하는 속성을 노출하기만 합니다. 속성이 변경되면 set 접근자가 해당 요소 속성을 변경하고 기본 전역 변수를 업데이트하여 컨트롤 모양을 수정합니다.  
  
 클래스에 다음 코드를 `MyControl1` 추가합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>데이터를 다시 호스트에 보내기  
 파일의 마지막 구성 요소는 `MyControlEventArgs` 수집된 데이터를 호스트로 다시 보내는 데 사용되는 클래스입니다.  
  
 네임스페이스에 다음 `MyControls` 코드를 추가합니다. 구현 방법은 간단하므로 자세히 설명하지 않습니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 솔루션을 빌드합니다. 빌드하면 MyControls.dll이라는 DLL이 생성됩니다.  
  
<a name="winforms_host_section"></a>
## <a name="implementing-the-windows-forms-host-application"></a>Windows Forms 호스트 애플리케이션 구현  
 Windows Forms 호스트 응용 <xref:System.Windows.Forms.Integration.ElementHost> 프로그램은 개체를 사용하여 복합 컨트롤을 호스트합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 복합 `OnButtonClick` 컨트롤에서 데이터를 수신하는 이벤트를 처리합니다. 또한 응용 프로그램에는 컨트롤의 모양을 수정하는 데 사용할 수 있는 옵션 단추 집합이 있습니다. 다음 그림에서는 애플리케이션을 보여 줍니다.  

다음 이미지는 Windows Forms 응용 프로그램에서 호스팅되는 WPF 복합 컨트롤을 보여 주며"  

 ![Avalon 컨트롤을 호스팅 하는 Windows 양식을 보여 주는 스크린샷입니다.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>프로젝트 만들기  
 프로젝트를 시작하려면  
  
1. 시각적 스튜디오를 실행하고 **새 프로젝트** 대화 상자를 엽니다.  
  
2. 시각적 C# 및 Windows 범주에서 **Windows 양식 응용 프로그램** 템플릿을 선택합니다.  
  
3. 새 프로젝트의 이름을 `WFHost`로 지정합니다.  
  
4. 위치에는 MyControls 프로젝트를 포함하는 동일한 최상위 폴더를 지정합니다.  
  
5. **확인**을 클릭하여 프로젝트를 만듭니다.  
  
 또한 포함된 `MyControl1` DLL 및 기타 어셈블리에 대한 참조를 추가해야 합니다.  
  
1. 솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **참조 추가를**선택합니다.  
  
2. **찾아보기** 탭을 클릭하고 MyControls.dll이 포함된 폴더를 찾아봅봅습니다. 이 연습에서 이 폴더는 MyControls\bin\Debug입니다.  
  
3. MyControls.dll을 선택한 다음 **확인을**클릭합니다.  
  
4. 다음 어셈블리에 대한 참조를 추가합니다.  
  
    - PresentationCore  
  
    - PresentationFramework  
  
    - System.Xaml  
  
    - WindowsBase  
  
    - WindowsFormsIntegration  
  
### <a name="implementing-the-user-interface-for-the-application"></a>애플리케이션에 대한 사용자 인터페이스 구현  
 Windows Form 애플리케이션의 UI에는 WPF 복합 컨트롤과 상호 작용하는 여러 컨트롤이 포함되어 있습니다.  
  
1. Windows Form 디자이너에서 Form1을 엽니다.  
  
2. 컨트롤 크기에 맞게 폼을 확장합니다.  
  
3. 폼의 오른쪽 위 모서리에 복합 <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> 컨트롤을 보유하는 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 추가합니다.  
  
4. 양식에 <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> 다음 컨트롤을 추가합니다.  
  
    |이름|텍스트|  
    |----------|----------|  
    |groupBox1|배경색|  
    |groupBox2|전경색|  
    |groupBox3|글꼴 크기|  
    |groupBox4|글꼴 패밀리|  
    |groupBox5|글꼴 스타일|  
    |groupBox6|글꼴 두께|  
    |groupBox7|컨트롤의 데이터|  
  
5. 컨트롤에 <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> 다음 컨트롤을 추가합니다. <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>  
  
    |GroupBox|이름|텍스트|  
    |--------------|----------|----------|  
    |groupBox1|radioBackgroundOriginal|Original|  
    |groupBox1|radioBackgroundLightGreen|LightGreen|  
    |groupBox1|radioBackgroundLightSalmon|LightSalmon|  
    |groupBox2|radioForegroundOriginal|Original|  
    |groupBox2|radioForegroundRed|빨강|  
    |groupBox2|radioForegroundYellow|노란색|  
    |groupBox3|radioSizeOriginal|Original|  
    |groupBox3|radioSizeTen|10|  
    |groupBox3|radioSizeTwelve|12|  
    |groupBox4|radioFamilyOriginal|Original|  
    |groupBox4|radioFamilyTimes|궁서|  
    |groupBox4|radioFamilyWingDings|WingDings|  
    |groupBox5|radioStyleOriginal|정상|  
    |groupBox5|radioStyleItalic|기울임꼴|  
    |groupBox6|radioWeightOriginal|Original|  
    |groupBox6|radioWeightBold|굵게|  
  
6. 마지막 <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>에 <xref:System.Windows.Forms.Label?displayProperty=nameWithType> 다음 컨트롤을 추가합니다. 이러한 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤에서 반환된 데이터를 표시합니다.  
  
    |GroupBox|이름|텍스트|  
    |--------------|----------|----------|  
    |groupBox7|lblName|이름:|  
    |groupBox7|lblAddress|구/군/시:|  
    |groupBox7|lblCity|시/도:|  
    |groupBox7|lblState|상태:|  
    |groupBox7|lblZip|우편 번호:|  
  
### <a name="initializing-the-form"></a>폼 초기화  
 일반적으로 양식의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 호스팅 코드를 구현합니다. 다음 코드는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤의 <xref:System.Windows.FrameworkElement.Loaded> 이벤트에 대한 처리기 및 나중에 사용되는 여러 전역 변수에 대한 선언을 보여 주며, 이 코드는 다음과 같습니다.  
  
 Windows 양식 디자이너에서 양식을 두 번 클릭하여 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기를 만듭니다. Form1.cs 맨 위에 다음 `using` 문을 추가합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 기존 `Form1` 클래스의 내용을 다음 코드로 바꿉니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 앞의 코드의 메서드는 `Form1_Load` [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 호스팅하는 일반적인 절차를 보여 주며 다음과 같은 방법을 보여 주며 있습니다.  
  
1. 새 <xref:System.Windows.Forms.Integration.ElementHost> 개체를 만듭니다.  
  
2. 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>로 설정합니다.  
  
3. 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost> 컬렉션에 <xref:System.Windows.Forms.Panel> 컨트롤을 <xref:System.Windows.Forms.Control.Controls%2A> 추가합니다.  
  
4. 컨트롤의 인스턴스를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 만듭니다.  
  
5. 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성에 컨트롤을 할당하여 폼에서 <xref:System.Windows.Forms.Integration.ElementHost> 복합 컨트롤을 호스트합니다.  
  
 메서드의 `Form1_Load` 나머지 두 줄은 핸들러를 두 개의 컨트롤 이벤트에 연결합니다.  
  
- `OnButtonClick`는 사용자가 **확인** 또는 **취소** 단추를 클릭할 때 복합 컨트롤에 의해 발생 되는 사용자 지정 이벤트입니다. 이 이벤트를 처리하여 사용자의 응답을 수신하고 사용자가 지정한 데이터를 수집합니다.  
  
- <xref:System.Windows.FrameworkElement.Loaded>는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 완전히 로드될 때 발생하는 표준 이벤트입니다. 이 예제에서는 컨트롤의 속성을 사용하여 여러 전역 변수를 초기화해야 하기 때문에 이 이벤트가 사용됩니다. 양식 이벤트 <xref:System.Windows.Forms.Form.Load> 시 컨트롤이 완전히 로드되지 않고 해당 값이 여전히 로 `null`설정됩니다. 이러한 속성에 액세스하려면 컨트롤의 <xref:System.Windows.FrameworkElement.Loaded> 이벤트가 발생할 때까지 기다려야 합니다.  
  
 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기는 위의 코드에 표시됩니다. 처리기는 `OnButtonClick` 다음 섹션에서 설명합니다.  
  
### <a name="handling-onbuttonclick"></a>OnButtonClick 처리  
 이 `OnButtonClick` 이벤트는 사용자가 **확인** 또는 **취소** 단추를 클릭할 때 발생합니다.  
  
 이벤트 처리기는 이벤트 인수의 `IsOK` 필드를 검사하여 클릭한 단추를 확인합니다. `lbl` *데이터* 변수는 이전에 <xref:System.Windows.Forms.Label> 설명한 컨트롤에 해당합니다. 사용자가 **확인** 단추를 클릭하면 컨트롤의 컨트롤의 <xref:System.Windows.Controls.TextBox> 데이터가 해당 <xref:System.Windows.Forms.Label> 컨트롤에 할당됩니다. 사용자가 **Cancel을**클릭하면 <xref:System.Windows.Forms.Label.Text%2A> 값이 기본 문자열로 설정됩니다.  
  
 다음 단추 클릭 이벤트 처리기 `Form1` 코드를 클래스에 추가합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 애플리케이션을 빌드 및 실행합니다. WPF 복합 컨트롤에 텍스트를 추가한 다음 **확인을**클릭합니다. 텍스트가 레이블에 나타납니다. 현재는 라디오 단추를 처리하는 코드가 추가되지 않았습니다.  
  
### <a name="modifying-the-appearance-of-the-control"></a>컨트롤의 모양 수정  
 폼의 <xref:System.Windows.Forms.RadioButton> 컨트롤을 사용하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤의 전경 및 배경 색과 여러 글꼴 속성을 변경할 수 있습니다. 배경색은 오브젝트에 <xref:System.Windows.Forms.Integration.ElementHost> 의해 노출됩니다. 나머지 속성은 컨트롤의 사용자 지정 속성으로 노출됩니다.  
  
 양식의 각 <xref:System.Windows.Forms.RadioButton> 컨트롤을 두 <xref:System.Windows.Forms.RadioButton.CheckedChanged> 번 클릭하여 이벤트 처리기를 만듭니다. <xref:System.Windows.Forms.RadioButton.CheckedChanged> 이벤트 처리기를 다음 코드로 바꿉니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 애플리케이션을 빌드 및 실행합니다. WPF 복합 컨트롤에 대한 효과를 확인하려면 다른 라디오 단추를 클릭합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [연습: Windows 양식에서 3D WPF 복합 제어 호스팅](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
