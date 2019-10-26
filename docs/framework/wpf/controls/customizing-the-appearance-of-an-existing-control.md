---
title: ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.assetid: 678dd116-43a2-4b8c-82b5-6b826f126e31
ms.openlocfilehash: 0c79ba3dd42f2e65eb241409946e921577ced5f1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920059"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정
<a name="introduction"></a>컨트롤의 시각적 구조와 시각적 동작을 지정 하 <xref:System.Windows.Controls.ControlTemplate>입니다. 새 <xref:System.Windows.Controls.ControlTemplate>을 제공 하 여 컨트롤의 모양을 사용자 지정할 수 있습니다. <xref:System.Windows.Controls.ControlTemplate>를 만들 때 해당 기능을 변경 하지 않고 기존 컨트롤의 모양을 바꿉니다. 예를 들어, 기본 정사각형 셰이프 대신 응용 프로그램의 둥근 모양 단추를 만들 수 있지만 단추는 계속 해 서 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 발생 시킵니다.

 이 항목에서는 <xref:System.Windows.Controls.ControlTemplate>의 다양 한 부분에 대해 설명 하 고 <xref:System.Windows.Controls.Button>에 대 한 간단한 <xref:System.Windows.Controls.ControlTemplate>을 만드는 방법을 보여 주고 컨트롤의 컨트롤 계약을 이해 하는 방법을 설명 합니다. 그러면 컨트롤의 모양을 사용자 지정할 수 있습니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 <xref:System.Windows.Controls.ControlTemplate>를 만들기 때문에 코드를 작성 하지 않고 컨트롤의 모양을 변경할 수 있습니다. Blend for Visual Studio와 같은 디자이너를 사용 하 여 사용자 지정 컨트롤 템플릿을 만들 수도 있습니다. 이 항목에서는 <xref:System.Windows.Controls.Button>의 모양을 사용자 지정 하 고 항목의 끝에 있는 전체 예제를 나열 하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제를 보여 줍니다. Blend for Visual Studio를 사용 하는 방법에 대 한 자세한 내용은 [템플릿을 지 원하는 컨트롤의 스타일](https://go.microsoft.com/fwlink/?LinkId=161153)지정을 참조 하세요.

 다음 그림에서는이 항목에서 만든 <xref:System.Windows.Controls.ControlTemplate>를 사용 하는 <xref:System.Windows.Controls.Button> 보여 줍니다.

 ![사용자 지정 컨트롤 템플릿을 사용하는 단추](./media/ndp-buttonnormal.png "NDP_ButtonNormal")
사용자 지정 컨트롤 템플릿을 사용하는 단추

 ![빨간색 테두리가 있는 단추](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")
사용자 지정 컨트롤 템플릿을 사용하고 마우스 포인터가 위에 놓여 있는 단추

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites
 이 항목에서는 [컨트롤](index.md)에 설명된 대로 컨트롤과 스타일을 만들고 사용하는 방법을 알고 있다고 가정합니다. 이 항목에서 설명 하는 개념은 <xref:System.Windows.Controls.UserControl>를 제외 하 고 <xref:System.Windows.Controls.Control> 클래스에서 상속 되는 요소에 적용 됩니다. <xref:System.Windows.Controls.UserControl>에 <xref:System.Windows.Controls.ControlTemplate>을 적용할 수 없습니다.

<a name="when_you_should_create_a_controltemplate"></a>
## <a name="when-you-should-create-a-controltemplate"></a>ControlTemplate을 만들어야 하는 경우
 컨트롤에는 <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>및 <xref:System.Windows.Controls.Control.FontFamily%2A>와 같이 컨트롤의 모양에 대 한 다양 한 측면을 지정 하기 위해 설정할 수 있는 다양 한 속성이 있지만 이러한 속성을 설정 하 여 변경할 수 있는 내용은 제한 됩니다. 예를 들어 <xref:System.Windows.Controls.CheckBox>에서 <xref:System.Windows.Controls.Control.Foreground%2A> 속성을 blue로 설정 하 고 <xref:System.Windows.Controls.Control.FontStyle%2A>을 기울임꼴로 설정할 수 있습니다.

 컨트롤에 대 한 새 <xref:System.Windows.Controls.ControlTemplate>을 만들 수 없는 경우에는 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 프로그램의 모든 컨트롤에 동일한 일반 모양이 지정 되어 사용자 지정 모양과 느낌을 가진 응용 프로그램을 만드는 기능이 제한 됩니다. 기본적으로 모든 <xref:System.Windows.Controls.CheckBox>에는 유사한 특징이 있습니다. 예를 들어 <xref:System.Windows.Controls.CheckBox>의 내용은 항상 선택 표시기의 오른쪽에 있고 확인 표시는 항상 <xref:System.Windows.Controls.CheckBox> 선택 됨을 나타내는 데 사용 됩니다.

 컨트롤의 다른 속성이 수행 하는 설정에 따라 컨트롤의 모양을 사용자 지정 하려는 경우 <xref:System.Windows.Controls.ControlTemplate>를 만듭니다. <xref:System.Windows.Controls.CheckBox>예제에서는 확인란의 내용이 선택 표시기 위에 표시 되도록 하 고 X를 클릭 하 여 <xref:System.Windows.Controls.CheckBox> 선택 되었음을 나타냅니다. 이러한 변경 내용은 <xref:System.Windows.Controls.CheckBox>의 <xref:System.Windows.Controls.ControlTemplate>에서 지정 합니다.

 다음 그림에서는 기본 <xref:System.Windows.Controls.ControlTemplate>를 사용 하는 <xref:System.Windows.Controls.CheckBox> 보여 줍니다.

 ![기본 컨트롤 템플릿을 사용하는 확인란](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")
기본 컨트롤 템플릿을 사용하는 확인란

 다음 그림에서는 사용자 지정 <xref:System.Windows.Controls.ControlTemplate>를 사용 하 여 <xref:System.Windows.Controls.CheckBox> 콘텐츠를 선택 표시기 위에 놓고 <xref:System.Windows.Controls.CheckBox>를 선택 하면 X를 표시 하는 <xref:System.Windows.Controls.CheckBox> 보여 줍니다.

 ![사용자 지정 컨트롤 템플릿을 사용하는 확인란](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")
사용자 지정 컨트롤 템플릿을 사용하는 확인란

 이 샘플의 <xref:System.Windows.Controls.CheckBox>에 대 한 <xref:System.Windows.Controls.ControlTemplate> 비교적 복잡 하므로이 항목에서는 <xref:System.Windows.Controls.Button>에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 만드는 간단한 예제를 사용 합니다.

<a name="changing_the_visual_structure_of_a_control"></a>
## <a name="changing-the-visual-structure-of-a-control"></a>컨트롤의 시각적 구조 변경
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 컨트롤은 종종 복합 <xref:System.Windows.FrameworkElement> 개체입니다. <xref:System.Windows.Controls.ControlTemplate>를 만드는 경우 <xref:System.Windows.FrameworkElement> 개체를 결합 하 여 단일 컨트롤을 빌드합니다. <xref:System.Windows.Controls.ControlTemplate>에는 루트 요소로 <xref:System.Windows.FrameworkElement> 하나만 있어야 합니다. 일반적으로 루트 요소는 다른 <xref:System.Windows.FrameworkElement> 개체를 포함 합니다. 개체가 조합되면 컨트롤의 시각적 구조가 만들어집니다.

 다음 예에서는 <xref:System.Windows.Controls.Button>에 대 한 사용자 지정 <xref:System.Windows.Controls.ControlTemplate>를 만듭니다. <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Button>의 시각적 구조를 만듭니다. 이 예제에서는 마우스 포인트를 단추 위로 이동하거나 단추를 클릭할 때 단추의 모양이 변경되지 않습니다. 단추가 다른 상태에 있을 때 단추의 모양을 변경하는 방법에 대해서는 이 항목의 뒷부분에서 설명합니다.

 이 예제에서 시각적 구조는 다음 부분으로 구성되어 있습니다.

- 템플릿의 루트 <xref:System.Windows.FrameworkElement>역할을 하는 `RootElement` 이라는 <xref:System.Windows.Controls.Border>입니다.

- `RootElement`의 자식인 <xref:System.Windows.Controls.Grid>입니다.

- 단추의 콘텐츠를 표시 하는 <xref:System.Windows.Controls.ContentPresenter>입니다. <xref:System.Windows.Controls.ContentPresenter>를 사용 하면 모든 형식의 개체를 표시할 수 있습니다.

 [!code-xaml[VSMButtonTemplate#BasicTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]

### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>TemplateBinding을 사용하여 컨트롤의 속성 기능 유지
 새 <xref:System.Windows.Controls.ControlTemplate>을 만드는 경우에도 공용 속성을 사용 하 여 컨트롤의 모양을 변경 하는 것이 좋습니다. [TemplateBinding](../advanced/templatebinding-markup-extension.md) 태그 확장은 <xref:System.Windows.Controls.ControlTemplate>에 있는 요소의 속성을 컨트롤에 정의 된 공용 속성에 바인딩합니다. [TemplateBinding](../advanced/templatebinding-markup-extension.md)을 사용하면 컨트롤의 속성이 템플릿의 매개 변수로 작동됩니다. 즉, 컨트롤의 속성을 설정하면 해당 값은 [TemplateBinding](../advanced/templatebinding-markup-extension.md)이 있는 요소로 전달됩니다.

 다음 예제에서는 [TemplateBinding](../advanced/templatebinding-markup-extension.md) 태그 확장을 사용 하 여 <xref:System.Windows.Controls.ControlTemplate>에 있는 요소의 속성을 단추에 정의 된 공용 속성에 바인딩하는 위의 예제 부분을 반복 합니다.

 [!code-xaml[VSMButtonTemplate#TemplateBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]

 이 예제에서는 <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> 속성 템플릿이 <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>에 바인딩되어 있습니다. <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType>는 템플릿 바인딩 이기 때문에 동일한 <xref:System.Windows.Controls.ControlTemplate>를 사용 하는 여러 단추를 만든 다음 <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>를 각 단추의 다른 값으로 설정할 수 있습니다. <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.ControlTemplate>요소의 속성에 매핑되지 않은 경우 단추의 <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>를 설정 해도 단추의 모양에는 영향을 주지 않습니다.

 두 속성의 이름이 같지 않아도 됩니다. 앞의 예제에서 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> 속성은 <xref:System.Windows.Controls.ContentPresenter>의 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> 속성에 바인딩되는 템플릿입니다. 이를 통해 단추 콘텐츠의 가로 위치를 지정할 수 있습니다. <xref:System.Windows.Controls.ContentPresenter>에 `HorizontalContentAlignment`라는 속성이 없지만 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>바인딩할 수 있습니다. 속성을 템플릿 바인딩할 경우 대상 속성과 소스 속성의 형식이 동일해야 합니다.

 <xref:System.Windows.Controls.Control> 클래스는 컨트롤이 설정 될 때 컨트롤에 영향을 주는 데 사용 해야 하는 여러 속성을 정의 합니다. 속성을 사용 하는 <xref:System.Windows.Controls.ControlTemplate>는 속성에 따라 달라 집니다. <xref:System.Windows.Controls.ControlTemplate>는 다음 방법 중 하나를 사용 하 여 속성을 사용 해야 합니다.

- <xref:System.Windows.Controls.ControlTemplate> 템플릿의 요소가 속성에 바인딩됩니다.

- <xref:System.Windows.Controls.ControlTemplate>의 요소는 부모 <xref:System.Windows.FrameworkElement>에서 속성을 상속 합니다.

 다음 표에서는 <xref:System.Windows.Controls.Control> 클래스에서 컨트롤에 상속 된 시각적 속성을 보여 줍니다. 또한 컨트롤의 기본 컨트롤 템플릿이 상속받은 속성 값을 사용하는지 또는 템플릿 바인딩되어야 하는지를 나타냅니다.

|속성|사용 방법|
|--------------|------------------|
|<xref:System.Windows.Controls.Control.Background%2A>|템플릿 바인딩|
|<xref:System.Windows.Controls.Control.BorderThickness%2A>|템플릿 바인딩|
|<xref:System.Windows.Controls.Control.BorderBrush%2A>|템플릿 바인딩|
|<xref:System.Windows.Controls.Control.FontFamily%2A>|속성 상속 또는 템플릿 바인딩|
|<xref:System.Windows.Controls.Control.FontSize%2A>|속성 상속 또는 템플릿 바인딩|
|<xref:System.Windows.Controls.Control.FontStretch%2A>|속성 상속 또는 템플릿 바인딩|
|<xref:System.Windows.Controls.Control.FontWeight%2A>|속성 상속 또는 템플릿 바인딩|
|<xref:System.Windows.Controls.Control.Foreground%2A>|속성 상속 또는 템플릿 바인딩|
|<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>|템플릿 바인딩|
|<xref:System.Windows.Controls.Control.Padding%2A>|템플릿 바인딩|
|<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>|템플릿 바인딩|

 테이블에는 <xref:System.Windows.Controls.Control> 클래스에서 상속 된 시각적 속성만 나열 됩니다. 표에 나열 된 속성 외에도 컨트롤은 부모 프레임 워크 요소에서 <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A>및 <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> 속성을 상속할 수 있습니다.

 또한 <xref:System.Windows.Controls.ContentPresenter> <xref:System.Windows.Controls.ContentControl><xref:System.Windows.Controls.ControlTemplate>에 있는 경우 <xref:System.Windows.Controls.ContentPresenter> <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 및 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성에 자동으로 바인딩됩니다. 마찬가지로 <xref:System.Windows.Controls.ItemsControl>의 <xref:System.Windows.Controls.ControlTemplate>에 있는 <xref:System.Windows.Controls.ItemsPresenter>은 자동으로 <xref:System.Windows.Controls.ItemsControl.Items%2A> 및 <xref:System.Windows.Controls.ItemsPresenter> 속성에 바인딩됩니다.

 다음 예제에서는 앞의 예제에 정의 된 <xref:System.Windows.Controls.ControlTemplate>를 사용 하는 두 개의 단추를 만듭니다. 이 예에서는 각 단추에 <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>및 <xref:System.Windows.Controls.Control.FontSize%2A> 속성을 설정 합니다. <xref:System.Windows.Controls.Control.Background%2A> 속성을 설정 하는 것은 <xref:System.Windows.Controls.ControlTemplate>에 템플릿이 바인딩되어 있으므로 효과가 있습니다. <xref:System.Windows.Controls.Control.Foreground%2A> 및 <xref:System.Windows.Controls.Control.FontSize%2A> 속성이 템플릿 바운드가 아닌 경우에도 해당 값이 상속 되므로 값을 설정 하면 효과가 있습니다.

 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]

 앞의 예제에서는 다음 그림과 유사한 출력을 생성합니다.

 ![단추 두 개: 파란색 단추 하나와 자주색 단추 하나](./media/ndp-buttontwo.png "NDP_ButtonTwo")
배경색이 서로 다른 두 개의 단추

<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>상태에 따라 컨트롤의 모양 변경
 기본 모양을 가진 단추와 앞의 예제에서 사용된 단추의 차이점은 기본 단추가 다른 상태에 있을 때 약간 변경된다는 것입니다. 예를 들어 단추를 누르거나 마우스 포인터가 단추 위에 있으면 기본 단추의 모양이 변경됩니다. <xref:System.Windows.Controls.ControlTemplate>는 컨트롤의 기능을 변경 하지 않지만 컨트롤의 시각적 동작을 변경 합니다. 시각적 동작은 컨트롤이 특정 상태에 있을 때의 컨트롤 모양을 설명합니다. 컨트롤의 기능과 시각적 동작의 차이점을 파악하려면 단추 예제를 참조하세요. 단추의 기능은 클릭 될 때 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 발생 시키는 것 이지만 단추의 시각적 동작은 포인터가 가리키거나 눌린 상태에서 모양을 변경 하는 것입니다.

 <xref:System.Windows.VisualState> 개체를 사용 하 여 컨트롤이 특정 상태에 있을 때 컨트롤의 모양을 지정할 수 있습니다. <xref:System.Windows.VisualState>에는 <xref:System.Windows.Controls.ControlTemplate>에 있는 요소의 모양을 변경 하는 <xref:System.Windows.Media.Animation.Storyboard> 포함 되어 있습니다. 컨트롤의 논리가 <xref:System.Windows.VisualStateManager>를 사용 하 여 상태를 변경 하기 때문에이 작업을 수행 하기 위해 코드를 작성할 필요가 없습니다. 컨트롤이 <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType> 속성으로 지정 된 상태에 들어가면 <xref:System.Windows.Media.Animation.Storyboard> 시작 됩니다. 컨트롤이 상태를 종료 하면 <xref:System.Windows.Media.Animation.Storyboard> 중지 됩니다.

 다음 예제에서는 마우스 포인터가 위에 있을 때 <xref:System.Windows.Controls.Button> 모양을 변경 하는 <xref:System.Windows.VisualState> 보여 줍니다. <xref:System.Windows.Media.Animation.Storyboard> `BorderBrush`색을 변경 하 여 단추의 테두리 색을 변경 합니다. 이 항목의 시작 부분에 <xref:System.Windows.Controls.ControlTemplate> 예제를 참조 하는 경우 `BorderBrush`은 <xref:System.Windows.Controls.Border>의 <xref:System.Windows.Controls.Border.Background%2A>에 할당 된 <xref:System.Windows.Media.SolidColorBrush> 이름 이라고 기억 하십시오.

 [!code-xaml[VSMButtonTemplate#4](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]

 이 컨트롤을 통해 해당 컨트롤 계약의 일부로 상태를 정의합니다. 컨트롤 계약에 대해서는 이 항목의 뒷부분에 있는 [컨트롤 계약을 이해하여 다른 컨트롤 사용자 지정](#customizing_other_controls_by_understanding_the_control_contract)에서 자세히 설명합니다. 다음 표에서는 <xref:System.Windows.Controls.Button>에 대해 지정 된 상태를 나열 합니다.

|VisualState 이름|VisualStateGroup 이름|설명|
|----------------------|---------------------------|-----------------|
|보통|CommonStates|기본 상태입니다.|
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|
|누름|CommonStates|컨트롤을 눌렀습니다.|
|Disabled|CommonStates|컨트롤이 비활성화되었습니다.|
|포커스 있음|FocusStates|컨트롤에 포커스가 있습니다.|
|포커스 없음|FocusStates|컨트롤에 포커스가 없습니다.|

 <xref:System.Windows.Controls.Button>는 두 개의 상태 그룹을 정의 합니다. `CommonStates` 그룹에는 `Normal`, `MouseOver`, `Pressed`및 `Disabled` 상태가 포함 됩니다. `FocusStates` 그룹에는 `Focused` 및 `Unfocused` 상태가 포함됩니다. 같은 상태 그룹에 있는 상태는 함께 사용할 수 없습니다. 컨트롤은 항상 그룹마다 한 개의 상태에 있습니다. 예를 들어 <xref:System.Windows.Controls.Button>는 마우스 포인터가 위에 있지 않아도 포커스를 가질 수 있으므로 `Focused` 상태의 <xref:System.Windows.Controls.Button> `MouseOver`, `Pressed`또는 `Normal` 상태일 수 있습니다.

 <xref:System.Windows.VisualStateGroup> 개체에 <xref:System.Windows.VisualState> 개체를 추가 합니다. 연결 된 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> 속성에 <xref:System.Windows.VisualStateGroup> 개체를 추가 합니다. 다음 예제에서는 `Normal`, `MouseOver`및 `Pressed` 상태에 대 한 <xref:System.Windows.VisualState> 개체를 정의 합니다 .이 개체는 모두 `CommonStates` 그룹에 있습니다. 각 <xref:System.Windows.VisualState>의 <xref:System.Windows.VisualState.Name%2A>은 위의 테이블에 있는 이름과 일치 합니다. 간단한 예제를 제공하기 위해 `Disabled` 상태와 `FocusStates` 그룹의 상태는 생략되었지만 이 항목의 끝에 있는 전체 예제에는 포함되어 있습니다.

> [!NOTE]
> <xref:System.Windows.Controls.ControlTemplate>의 루트 <xref:System.Windows.FrameworkElement>에 연결 된 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> 속성을 설정 해야 합니다.

 [!code-xaml[VSMButtonTemplate#VisualStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]

 앞의 예제에서는 다음 그림과 유사한 출력을 생성합니다.

 ![사용자 지정 컨트롤 템플릿을 사용하는 단추](./media/ndp-buttonnormal.png "NDP_ButtonNormal")
정상 상태에서 사용자 지정 컨트롤 템플릿을 사용하는 단추

 ![빨간색 테두리가 있는 단추](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")
마우스가 위에 있는 상태에서 사용자 지정 컨트롤 템플릿을 사용하는 단추

 ![단추를 누르면 테두리가 투명해집니다.](./media/ndp-buttonpressed.png "NDP_ButtonPressed")
누름 상태에서 사용자 지정 컨트롤 템플릿을 사용하는 단추

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공된 컨트롤의 시각적 상태를 찾으려면 [Control 스타일 및 템플릿](control-styles-and-templates.md)을 참조하세요.

<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>상태 간 전환 시 컨트롤의 동작 지정
 위의 예제에서 단추를 클릭하면 모양도 변경되지만 단추를 1초 동안 누르고 있지 않으면 효과가 표시되지 않습니다. 기본적으로 애니메이션은 적용되려면 1초가 걸립니다. 사용자가 단추를 클릭 하 여 더 짧은 시간 안에 놓을 가능성이 있기 때문에 <xref:System.Windows.Controls.ControlTemplate>를 기본 상태로 두면 시각적 피드백이 적용 되지 않습니다.

 <xref:System.Windows.Controls.ControlTemplate>에 <xref:System.Windows.VisualTransition> 개체를 추가 하 여 컨트롤을 한 상태에서 다른 상태로 원활 하 게 전환 하기 위해 애니메이션이 발생 하는 시간을 지정할 수 있습니다. 만들 때는 <xref:System.Windows.VisualTransition>, 다음 중 하나 이상을 지정:

- 적용할 상태 간에 전환되는 데 소요되는 시간

- 컨트롤의 모양에 전환 시 적용되는 추가 변경 내용

- <xref:System.Windows.VisualTransition> 적용 되는 상태입니다.

### <a name="specifying-the-duration-of-a-transition"></a>전환 기간 지정
 전환 하는 걸리는 시간을 설정 하 여 지정할 수 있습니다는 <xref:System.Windows.VisualTransition.GeneratedDuration%2A> 속성입니다. 위의 예제에는 단추를 누를 때 단추의 테두리가 투명해 지는 것을 지정 하는 <xref:System.Windows.VisualState> 있습니다. 그러나 단추를 빠르게 누르고 놓았을 경우 애니메이션을 눈에 띄는 시간이 오래 걸립니다. <xref:System.Windows.VisualTransition>를 사용 하 여 컨트롤을 눌린 상태로 전환 하는 데 소요 되는 시간을 지정할 수 있습니다. 다음 예제에서는 컨트롤이 누른 상태로 전환되는 데 1/100초가 걸리도록 지정합니다.

 [!code-xaml[VSMButtonTemplate#PressedTransition](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]

### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>전환 중 컨트롤의 모양 변경 지정
 <xref:System.Windows.VisualTransition>에는 컨트롤이 상태 간에 전환 될 때 시작 하는 <xref:System.Windows.Media.Animation.Storyboard> 포함 되어 있습니다. 예를 들어 컨트롤이 `MouseOver` 상태에서 `Normal` 상태로 전환될 때 특정 애니메이션이 적용되도록 지정할 수 있습니다. 다음 예에서는 사용자가 마우스 포인터를 단추 밖으로 이동할 때 단추의 테두리가 파랑, 노란색, 1.5 초 내 검은색으로 변경 될 때이를 지정 하는 <xref:System.Windows.VisualTransition>을 만듭니다.

 [!code-xaml[VSMButtonTemplate#8](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]

### <a name="specifying-when-a-visualtransition-is-applied"></a>VisualTransition 적용 시기 지정
 <xref:System.Windows.VisualTransition>는 특정 상태에만 적용 되도록 제한 하거나, 컨트롤이 상태 간에 전환 될 때마다 적용 될 수 있습니다. 위의 예제에서는 컨트롤이 `MouseOver` 상태에서 `Normal` 상태로 이동할 때 <xref:System.Windows.VisualTransition> 적용 됩니다. 이전 예제에서는 컨트롤이 `Pressed` 상태로 전환 될 때 <xref:System.Windows.VisualTransition> 적용 됩니다. 시간을 제한할 수는 <xref:System.Windows.VisualTransition> 설정 하 여 적용 되는 <xref:System.Windows.VisualTransition.To%2A> 및 <xref:System.Windows.VisualTransition.From%2A> 속성. 다음 표에서는 최대한의 제한에서 최소한의 제한까지 제한 수준에 대해 설명합니다.

|제한 유형|From 값|To 값|
|-------------------------|-------------------|-----------------|
|지정된 상태에서 지정된 다른 상태로 전환|이름을 <xref:System.Windows.VisualState>|이름을 <xref:System.Windows.VisualState>|
|임의의 상태에서 지정된 상태로 전환|설정 안 함|이름을 <xref:System.Windows.VisualState>|
|지정된 상태에서 임의의 상태로 전환|이름을 <xref:System.Windows.VisualState>|설정 안 함|
|임의의 상태에서 임의의 다른 상태로 전환|설정 안 함|설정 안 함|

 여러 개 있을 수 있습니다 <xref:System.Windows.VisualTransition> 개체는 <xref:System.Windows.VisualStateGroup> 동일한 상태를 참조 하는 있지만 이러한 이전 표에 지정 된 순서 대로 사용 됩니다. 다음 예제에는 두 개의 <xref:System.Windows.VisualTransition> 개체가 있습니다. 컨트롤에서 전환 하는 경우는 `Pressed` 상태는 `MouseOver` 상태를 <xref:System.Windows.VisualTransition> 둘 다를 포함 하는 <xref:System.Windows.VisualTransition.From%2A> 및 <xref:System.Windows.VisualTransition.To%2A> 집합이 사용 됩니다. 컨트롤이 `Pressed`가 아닌 상태에서 `MouseOver` 상태로 전환될 때는 다른 상태가 사용됩니다.

 [!code-xaml[VSMButtonTemplate#7](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]

 <xref:System.Windows.VisualStateGroup>에는 <xref:System.Windows.VisualStateGroup>의 <xref:System.Windows.VisualState> 개체에 적용 되는 <xref:System.Windows.VisualTransition> 개체를 포함 하는 <xref:System.Windows.VisualStateGroup.Transitions%2A> 속성이 있습니다. <xref:System.Windows.Controls.ControlTemplate> 저자는 원하는 <xref:System.Windows.VisualTransition>를 자유롭게 포함할 수 있습니다. 그러나 <xref:System.Windows.VisualTransition.To%2A> 및 <xref:System.Windows.VisualTransition.From%2A> 속성이 <xref:System.Windows.VisualStateGroup>에 없는 상태 이름으로 설정 된 경우 <xref:System.Windows.VisualTransition>는 무시 됩니다.

 다음 예에서는 `CommonStates`에 대 한 <xref:System.Windows.VisualStateGroup>를 보여 줍니다. 이 예제에서는 단추의 다음 전환에 대 한 <xref:System.Windows.VisualTransition>를 정의 합니다.

- `Pressed` 상태로 전환

- `MouseOver` 상태로 전환

- `Pressed` 상태에서 `MouseOver` 상태로 전환

- `MouseOver` 상태에서 `Normal` 상태로 전환

 [!code-xaml[VSMButtonTemplate#VisualTransitions](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]

<a name="customizing_other_controls_by_understanding_the_control_contract"></a>
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>컨트롤 계약을 이해하여 다른 컨트롤 사용자 지정
 <xref:System.Windows.FrameworkElement> 개체를 사용 하 여 시각적 구조를 지정 하기 위해 <xref:System.Windows.Controls.ControlTemplate>를 사용 하 고 <xref:System.Windows.VisualState> 개체를 사용 하 여 시각적 동작을 지정 하는 컨트롤은 파트 컨트롤 모델을 사용 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4와 함께 제공되는 많은 컨트롤이 이 모델을 사용합니다. <xref:System.Windows.Controls.ControlTemplate> 작성자가 인식 해야 하는 파트는 컨트롤 계약을 통해 전달 됩니다. 컨트롤 계약의 파트를 이해하면 파트 컨트롤 모델을 사용하는 모든 컨트롤의 모양을 사용자 지정할 수 있습니다.

 컨트롤 계약에는 세 가지 요소가 있습니다.

- 컨트롤 논리가 사용하는 시각적 요소

- 컨트롤의 상태 및 각 상태가 속해 있는 그룹

- 컨트롤에 시각적으로 영향을 미치는 공용 속성

### <a name="visual-elements-in-the-control-contract"></a>컨트롤 계약의 시각적 요소
 경우에 따라 컨트롤의 논리는 <xref:System.Windows.Controls.ControlTemplate>에 있는 <xref:System.Windows.FrameworkElement> 상호 작용 합니다. 예를 들어 컨트롤에서 해당 요소 중 하나의 이벤트를 처리할 수 있습니다. 컨트롤에서 <xref:System.Windows.Controls.ControlTemplate>의 특정 <xref:System.Windows.FrameworkElement> 찾으려는 경우 <xref:System.Windows.Controls.ControlTemplate> 작성자에 게 해당 정보를 전달 해야 합니다. 컨트롤은 <xref:System.Windows.TemplatePartAttribute>를 사용 하 여 예상 되는 요소 형식과 요소의 이름을 전달 합니다. <xref:System.Windows.Controls.Button>는 해당 컨트롤 계약에 <xref:System.Windows.FrameworkElement> 부분이 없지만 <xref:System.Windows.Controls.ComboBox>와 같은 다른 컨트롤은 수행 합니다.

 다음 예제에서는 <xref:System.Windows.Controls.ComboBox> 클래스에 지정 된 <xref:System.Windows.TemplatePartAttribute> 개체를 보여 줍니다. <xref:System.Windows.Controls.ComboBox> 논리는 `PART_EditableTextBox` 이라는 <xref:System.Windows.Controls.TextBox>와 `PART_Popup`에서 <xref:System.Windows.Controls.ControlTemplate>이라는 <xref:System.Windows.Controls.Primitives.Popup>를 찾으려고 합니다.

 [!code-csharp[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]

 다음 예제에서는 <xref:System.Windows.Controls.ComboBox> 클래스에서 <xref:System.Windows.TemplatePartAttribute> 개체로 지정 된 요소가 포함 된 <xref:System.Windows.Controls.ComboBox>에 대 한 단순화 된 <xref:System.Windows.Controls.ControlTemplate>를 보여 줍니다.

 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]

### <a name="states-in-the-control-contract"></a>컨트롤 계약의 상태
 컨트롤의 상태도 컨트롤 계약의 파트입니다. <xref:System.Windows.Controls.Button>에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 만드는 예제에서는 상태에 따라 <xref:System.Windows.Controls.Button> 모양을 지정 하는 방법을 보여 줍니다. 지정 된 각 상태에 대 한 <xref:System.Windows.VisualState> 만들고이 항목의 이전 [상태에 따라 컨트롤의 모양 변경](#changing_the_appearance_of_a_control_depending_on_its_state) 에 설명 된 대로 <xref:System.Windows.VisualStateGroup>에서 <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A>을 공유 하는 모든 <xref:System.Windows.VisualState> 개체를 배치 합니다. 타사 컨트롤은 <xref:System.Windows.TemplateVisualStateAttribute>를 사용 하 여 상태를 지정 해야 합니다 .이 도구를 사용 하면 Visual Studio의 [XAML 디자이너](/visualstudio/xaml-tools/designing-xaml-in-visual-studio) 및 Blend for Visual Studio와 같은 디자이너 도구를 사용 하 여 컨트롤 템플릿 제작을 위한 컨트롤의 상태를 노출할 수 있습니다.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공되는 컨트롤의 컨트롤 계약을 찾으려면 [Control 스타일 및 템플릿](control-styles-and-templates.md)을 참조하세요.

### <a name="properties-in-the-control-contract"></a>컨트롤 계약의 속성
 시각적으로 컨트롤에 영향을 주는 공용 속성도 컨트롤 계약에 포함됩니다. 이러한 속성을 설정 하 여 새 <xref:System.Windows.Controls.ControlTemplate>을 만들지 않고 컨트롤의 모양을 변경할 수 있습니다. [TemplateBinding](../advanced/templatebinding-markup-extension.md) 태그 확장을 사용 하 여 <xref:System.Windows.Controls.ControlTemplate>에 있는 요소의 속성을 <xref:System.Windows.Controls.Button>정의 된 공용 속성에 바인딩할 수도 있습니다.

 다음 예제에서는 단추의 컨트롤 계약을 보여 줍니다.

 [!code-csharp[VSMButtonTemplate#ButtonContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]

 <xref:System.Windows.Controls.ControlTemplate>를 만들 때 기존 <xref:System.Windows.Controls.ControlTemplate> 시작 하 고 변경 하는 것이 가장 쉬운 경우가 많습니다. 다음 중 하나를 수행 하 여 기존 <xref:System.Windows.Controls.ControlTemplate>를 변경할 수 있습니다.

- 컨트롤 템플릿을 만들기 위한 그래픽 사용자 인터페이스를 제공 하는 Blend for Visual Studio와 같은 디자이너를 사용 합니다. 자세한 내용은 [템플릿을 지원하는 컨트롤의 스타일 지정](https://go.microsoft.com/fwlink/?LinkId=161153)을 참조하세요.

- 기본 <xref:System.Windows.Controls.ControlTemplate>를 가져오고 편집 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공되는 기본 컨트롤 템플릿을 찾으려면 [기본 WPF 테마](https://go.microsoft.com/fwlink/?LinkID=158252)를 참조하세요.

<a name="complete_example"></a>
## <a name="complete-example"></a>완성된 예제
 다음 예제에서는이 항목에서 설명 하는 전체 <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.ControlTemplate>를 보여 줍니다.

 [!code-xaml[VSMButtonTemplate#3](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]

## <a name="see-also"></a>참조

- [스타일 지정 및 템플릿](styling-and-templating.md)
