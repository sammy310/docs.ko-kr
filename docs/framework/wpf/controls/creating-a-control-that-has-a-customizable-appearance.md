---
title: 사용자 지정 가능한 모양이 있는 컨트롤 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], customizing
- VisualStateManager [WPF], managing the state of a control
- ControlTemplate [WPF], customizing appearance
- controls [WPF], defining the visual structure and behavior of
- customizing appearance [WPF], ControlTemplate
- managing control states [WPF], VisualStateManager
- VisualStateManager [WPF], best practice
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
ms.openlocfilehash: d9cf092cf47d4fb70b15033d039777d3279b633a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283568"
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>사용자 지정 가능한 모양이 있는 컨트롤 만들기

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 모양을 사용자 지정할 수 있는 컨트롤을 만드는 기능을 제공 합니다. 예를 들어 새 <xref:System.Windows.Controls.ControlTemplate>를 만들어 설정 속성에 대 한 <xref:System.Windows.Controls.CheckBox>의 모양을 변경할 수 있습니다. 다음 그림에서는 기본 <xref:System.Windows.Controls.ControlTemplate>를 사용 하는 <xref:System.Windows.Controls.CheckBox>와 사용자 지정 <xref:System.Windows.Controls.ControlTemplate>를 사용 하는 <xref:System.Windows.Controls.CheckBox> 보여 줍니다.

![기본 컨트롤 템플릿을 사용하는 확인란](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")
기본 컨트롤 템플릿을 사용하는 확인란

![사용자 지정 컨트롤 템플릿을 사용하는 확인란](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")
사용자 지정 컨트롤 템플릿을 사용하는 확인란

컨트롤을 만들 때 파트 및 상태 모델을 따르는 경우 컨트롤의 모양을 사용자 지정할 수 있습니다. Blend for Visual Studio와 같은 디자이너 도구는 파트 및 상태 모델을 지원 하므로이 모델을 따를 경우 해당 응용 프로그램 형식에서 컨트롤을 사용자 지정할 수 있습니다.  이 항목에서는 파트 및 상태 모델에 대해 설명 하 고 사용자 고유의 컨트롤을 만들 때이를 따르는 방법을 설명 합니다. 이 항목에서는 사용자 지정 컨트롤 `NumericUpDown`의 예제를 사용 하 여이 모델의 철학을 설명 합니다.  `NumericUpDown` 컨트롤은 사용자가 컨트롤의 단추를 클릭 하 여 늘리거나 줄일 수 있는 숫자 값을 표시 합니다.  다음 그림에서는이 항목에서 설명 하는 `NumericUpDown` 컨트롤을 보여 줍니다.

![NumericUpDown 사용자 지정 컨트롤입니다.](./media/ndp-numericupdown.png "NDP_NumericUPDown")
사용자 지정 NumericUpDown 컨트롤입니다.

이 항목에는 다음과 같은 섹션이 포함되어 있습니다.

- [필수 구성 요소](#prerequisites)

- [파트 및 상태 모델](#parts_and_states_model)

- [ControlTemplate에서 컨트롤의 시각적 구조 및 시각적 동작 정의](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)

- [코드에서 ControlTemplate 부분 사용](#using_parts_of_the_controltemplate_in_code)

- [컨트롤 계약 제공](#providing_the_control_contract)

- [전체 예제](#complete_example)

<a name="prerequisites"></a>

## <a name="prerequisites"></a>전제 조건

이 항목에서는 기존 컨트롤에 대 한 새 <xref:System.Windows.Controls.ControlTemplate>을 만드는 방법, 컨트롤 계약의 요소에 대해 잘 알고 있다고 가정 하 고, [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)에 설명 된 개념을 이해 하 고 있다고 가정 합니다.

> [!NOTE]
> 모양을 사용자 지정 하는 컨트롤을 만들려면 <xref:System.Windows.Controls.Control> 클래스 또는 <xref:System.Windows.Controls.UserControl>이외의 하위 클래스 중 하나에서 상속 되는 컨트롤을 만들어야 합니다.  <xref:System.Windows.Controls.UserControl>에서 상속 되는 컨트롤은 빠르게 만들 수 있는 컨트롤이 며 <xref:System.Windows.Controls.ControlTemplate>를 사용 하지 않으며 모양을 사용자 지정할 수 없습니다.

<a name="parts_and_states_model"></a>

## <a name="parts-and-states-model"></a>파트 및 상태 모델

파트 및 상태 모델은 컨트롤의 시각적 구조 및 시각적 동작을 정의 하는 방법을 지정 합니다. 파트 및 상태 모델을 따르려면 다음을 수행 해야 합니다.

- 컨트롤 <xref:System.Windows.Controls.ControlTemplate>의 시각적 구조 및 시각적 동작을 정의 합니다.

- 컨트롤의 논리가 컨트롤 템플릿의 부분과 상호 작용 하는 경우 특정 모범 사례를 따릅니다.

- <xref:System.Windows.Controls.ControlTemplate>에 포함할 항목을 지정 하는 컨트롤 계약을 제공 합니다.

컨트롤의 <xref:System.Windows.Controls.ControlTemplate>에서 시각적 구조 및 시각적 동작을 정의 하는 경우 응용 프로그램 작성자는 코드를 작성 하는 대신 새 <xref:System.Windows.Controls.ControlTemplate>를 만들어 컨트롤의 시각적 구조 및 시각적 동작을 변경할 수 있습니다.   응용 프로그램 작성자에 게 <xref:System.Windows.Controls.ControlTemplate>에서 정의 해야 하 <xref:System.Windows.FrameworkElement> 개체 및 상태를 알려 주는 컨트롤 계약을 제공 해야 합니다. 컨트롤에서 불완전 한 <xref:System.Windows.Controls.ControlTemplate>를 제대로 처리 하도록 <xref:System.Windows.Controls.ControlTemplate>의 부분과 상호 작용할 때 몇 가지 모범 사례를 따라야 합니다.  이러한 세 가지 원칙을 따르는 경우 응용 프로그램 작성자는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공 되는 컨트롤의 경우와 마찬가지로 손쉽게 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 만들 수 있습니다.  다음 섹션에서는 이러한 각 권장 사항에 대해 자세히 설명 합니다.

<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>

## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>ControlTemplate에서 컨트롤의 시각적 구조 및 시각적 동작 정의

파트 및 상태 모델을 사용 하 여 사용자 지정 컨트롤을 만드는 경우 컨트롤의 시각적 구조와 시각적 동작을 논리 대신 <xref:System.Windows.Controls.ControlTemplate> 정의 합니다.  컨트롤의 시각적 구조는 컨트롤을 구성 하는 <xref:System.Windows.FrameworkElement> 개체의 복합입니다.  시각적 동작은 컨트롤이 특정 상태에 있을 때 표시 되는 방법입니다.   컨트롤의 시각적 구조 및 시각적 동작을 지정 하는 <xref:System.Windows.Controls.ControlTemplate>을 만드는 방법에 대 한 자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.

`NumericUpDown` 컨트롤의 예제에서 시각적 구조는 두 개의 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤과 <xref:System.Windows.Controls.TextBlock>를 포함 합니다.  예를 들어 `NumericUpDown` 컨트롤의 코드에 이러한 컨트롤을 추가 하는 경우 해당 컨트롤의 위치는 변경할 수 없습니다 됩니다.  코드에서 컨트롤의 시각적 구조와 시각적 동작을 정의 하는 대신 <xref:System.Windows.Controls.ControlTemplate>에서 정의 해야 합니다.  그런 다음 응용 프로그램 개발자가 단추 및 <xref:System.Windows.Controls.TextBlock>의 위치를 사용자 지정 하 고 <xref:System.Windows.Controls.ControlTemplate>를 바꿀 수 있으므로 `Value`가 음수인 경우 발생 하는 동작을 지정 합니다.

다음 예제에서는 `NumericUpDown` 컨트롤의 시각적 구조를 보여 줍니다. 여기에는 `Value`를 늘리기 위한 <xref:System.Windows.Controls.Primitives.RepeatButton>, `Value`를 줄이는 <xref:System.Windows.Controls.Primitives.RepeatButton>, <xref:System.Windows.Controls.TextBlock> 표시 하는 `Value`이 포함 됩니다.

[!code-xaml[VSMCustomControl#VisualStructure](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]

`NumericUpDown` 컨트롤의 시각적 동작은 값이 음수인 경우 빨간색 글꼴로 표시 된다는 것입니다.  `Value`가 음수인 경우 코드에서 <xref:System.Windows.Controls.TextBlock>의 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 변경 하면 `NumericUpDown`는 항상 빨강 음수 값을 표시 합니다. <xref:System.Windows.Controls.ControlTemplate>에 <xref:System.Windows.VisualState> 개체를 추가 하 여 <xref:System.Windows.Controls.ControlTemplate>에서 컨트롤의 시각적 동작을 지정 합니다.  다음 예제에서는 `Positive` 및 `Negative` 상태에 대 한 <xref:System.Windows.VisualState> 개체를 보여 줍니다.  `Positive` 및 `Negative`는 함께 사용할 수 없습니다. 즉, 컨트롤이 항상 두 항목 중 하나에 있으므로이 예제에서는 <xref:System.Windows.VisualState> 개체를 단일 <xref:System.Windows.VisualStateGroup>에 배치 합니다.  컨트롤이 `Negative` 상태로 들어가면 <xref:System.Windows.Controls.TextBlock>의 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 빨간색으로 바뀝니다.  컨트롤이 `Positive` 상태 이면 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 원래 값으로 돌아갑니다.  <xref:System.Windows.Controls.ControlTemplate>에서 <xref:System.Windows.VisualState> 개체 정의는 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)에서 자세히 설명 합니다.

> [!NOTE]
> <xref:System.Windows.Controls.ControlTemplate>의 루트 <xref:System.Windows.FrameworkElement>에 연결 된 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> 속성을 설정 해야 합니다.

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

<a name="using_parts_of_the_controltemplate_in_code"></a>

## <a name="using-parts-of-the-controltemplate-in-code"></a>코드에서 ControlTemplate 부분 사용

<xref:System.Windows.Controls.ControlTemplate> 작성자는 의도적으로 또는 실수로 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.VisualState> 개체를 생략할 수 있지만 컨트롤의 논리는 이러한 부분이 제대로 작동 해야 할 수 있습니다. 파트 및 상태 모델은 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.VisualState> 개체가 누락 된 <xref:System.Windows.Controls.ControlTemplate>에 대 한 컨트롤의 복원 력을 지정 합니다.  <xref:System.Windows.Controls.ControlTemplate>에서 <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>또는 <xref:System.Windows.VisualStateGroup> 누락 된 경우 컨트롤은 예외를 throw 하거나 오류를 보고 하지 않아야 합니다. 이 섹션에서는 <xref:System.Windows.FrameworkElement> 개체와 상호 작용 하 고 상태를 관리 하는 데 권장 되는 방법을 설명 합니다.

### <a name="anticipate-missing-frameworkelement-objects"></a>누락 된 FrameworkElement 개체 예상

<xref:System.Windows.Controls.ControlTemplate>에서 <xref:System.Windows.FrameworkElement> 개체를 정의 하는 경우 컨트롤의 논리가 일부 개체와 상호 작용 해야 할 수 있습니다.  예를 들어 `NumericUpDown` 컨트롤은 단추의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 구독 하 여 `Value`를 증가 시키거나 감소 시키고 <xref:System.Windows.Controls.TextBlock>의 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성을 `Value`로 설정 합니다. 사용자 지정 <xref:System.Windows.Controls.ControlTemplate>에서 <xref:System.Windows.Controls.TextBlock> 또는 단추를 생략 하는 경우 컨트롤의 일부 기능이 손실 될 수 있지만 컨트롤에서 오류를 발생 시 키 지 않도록 해야 합니다. 예를 들어 <xref:System.Windows.Controls.ControlTemplate>에 `Value`변경 하는 단추가 포함 되어 있지 않은 경우 `NumericUpDown`는 해당 기능을 상실 하지만 <xref:System.Windows.Controls.ControlTemplate>를 사용 하는 응용 프로그램은 계속 실행 됩니다.

다음 방법에서는 컨트롤이 누락 <xref:System.Windows.FrameworkElement> 개체에 올바르게 응답 하는지 확인 합니다.

1. 코드에서 참조 해야 하는 각 <xref:System.Windows.FrameworkElement>의 `x:Name` 특성을 설정 합니다.

2. 상호 작용 해야 하는 각 <xref:System.Windows.FrameworkElement>에 대 한 개인 속성을 정의 합니다.

3. <xref:System.Windows.FrameworkElement> 속성의 set 접근자에서 컨트롤이 처리 하는 이벤트를 구독 하 고 구독 취소 합니다.

4. <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 메서드에서 2 단계에서 정의한 <xref:System.Windows.FrameworkElement> 속성을 설정 합니다. 이는 <xref:System.Windows.Controls.ControlTemplate>의 <xref:System.Windows.FrameworkElement> 컨트롤에 사용할 수 있는 가장 빠른입니다. <xref:System.Windows.FrameworkElement> `x:Name`를 사용 하 여 <xref:System.Windows.Controls.ControlTemplate>에서 가져옵니다.

5. 해당 멤버에 액세스 하기 전에 <xref:System.Windows.FrameworkElement> `null` 되지 않았는지 확인 합니다.  `null`경우에는 오류를 보고 하지 마십시오.

다음 예제에서는 `NumericUpDown` 컨트롤이 앞의 목록에 있는 권장 사항에 따라 <xref:System.Windows.FrameworkElement> 개체와 상호 작용 하는 방법을 보여 줍니다.

<xref:System.Windows.Controls.ControlTemplate>에서 `NumericUpDown` 컨트롤의 시각적 구조를 정의 하는 예제에서는 `Value`를 늘리는 <xref:System.Windows.Controls.Primitives.RepeatButton> `x:Name` 특성이 `UpButton`로 설정 됩니다.  다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate>에 선언 된 <xref:System.Windows.Controls.Primitives.RepeatButton>를 나타내는 `UpButtonElement` 라는 속성을 선언 합니다. `set` 접근자는 먼저 단추의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 구독 취소 합니다. `UpDownElement` `null`되지 않은 경우 속성을 설정한 다음 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 구독 합니다. 다른 <xref:System.Windows.Controls.Primitives.RepeatButton>에는 정의 되어 있지만 여기에 표시 되지 않은 속성도 정의 되어 있습니다 `DownButtonElement`라고 합니다.

[!code-csharp[VSMCustomControl#UpButtonProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
[!code-vb[VSMCustomControl#UpButtonProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]

다음 예제에서는 `NumericUpDown` 컨트롤의 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>을 보여 줍니다.  이 예제에서는 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> 메서드를 사용 하 여 <xref:System.Windows.Controls.ControlTemplate>에서 <xref:System.Windows.FrameworkElement> 개체를 가져옵니다.  예는 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>에서 예상 된 형식이 아닌 지정 된 이름의 <xref:System.Windows.FrameworkElement>를 찾는 경우를 방지 합니다. 지정 된 `x:Name` 있지만 형식이 잘못 된 요소를 무시 하는 것도 좋습니다.

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

앞의 예제에 표시 된 방법에 따라 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.FrameworkElement>누락 된 경우에도 컨트롤이 계속 실행 되도록 합니다.

### <a name="use-the-visualstatemanager-to-manage-states"></a>R를 사용 하 여 상태 관리

<xref:System.Windows.VisualStateManager>는 컨트롤의 상태를 추적 하 고 상태를 전환 하는 데 필요한 논리를 수행 합니다. <xref:System.Windows.VisualState> 개체를 <xref:System.Windows.Controls.ControlTemplate>에 추가 하는 경우 해당 개체를 <xref:System.Windows.VisualStateGroup>에 추가 하 고 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> 연결 된 속성에 <xref:System.Windows.VisualStateGroup>를 추가 하 여 <xref:System.Windows.VisualStateManager>에서 액세스할 수 있도록 합니다.

다음 예제에서는 컨트롤의 `Positive` 및 `Negative` 상태에 해당 하는 <xref:System.Windows.VisualState> 개체를 보여 주는 이전 예제를 반복 합니다. `Negative`<xref:System.Windows.VisualState>의 <xref:System.Windows.Media.Animation.Storyboard>는 빨강의 <xref:System.Windows.Controls.TextBlock.Foreground%2A>을 <xref:System.Windows.Controls.TextBlock> 합니다.   `NumericUpDown` 컨트롤이 `Negative` 상태 이면 `Negative` 상태의 storyboard가 시작 됩니다.  그러면 컨트롤이 `Positive` 상태로 반환 될 때 `Negative` 상태의 <xref:System.Windows.Media.Animation.Storyboard> 중지 됩니다.  `Negative`에 대 한 <xref:System.Windows.Media.Animation.Storyboard> 중지 될 때 <xref:System.Windows.Controls.TextBlock.Foreground%2A>가 원래 색으로 반환 되기 때문에 `Positive`<xref:System.Windows.VisualState>는 <xref:System.Windows.Media.Animation.Storyboard>를 포함할 필요가 없습니다.

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

<xref:System.Windows.Controls.TextBlock>에 이름이 지정 되어 있지만 컨트롤의 논리가 <xref:System.Windows.Controls.TextBlock>를 참조 하지 않기 때문에 <xref:System.Windows.Controls.TextBlock> `NumericUpDown`에 대 한 컨트롤 계약에 없습니다.  <xref:System.Windows.Controls.ControlTemplate>에서 참조 되는 요소에는 이름이 있지만 컨트롤의 새 <xref:System.Windows.Controls.ControlTemplate>에서 해당 요소를 참조할 필요가 없기 때문에 컨트롤 계약의 일부가 될 필요는 없습니다.  예를 들어 `NumericUpDown`에 대 한 새 <xref:System.Windows.Controls.ControlTemplate>을 만드는 사람은 <xref:System.Windows.Controls.Control.Foreground%2A>를 변경 하 여 `Value`가 음수 임을 나타내지 않을 수 있습니다.  이 경우 코드와 <xref:System.Windows.Controls.ControlTemplate> 모두 이름으로 <xref:System.Windows.Controls.TextBlock>을 참조 하지 않습니다.

컨트롤의 논리는 컨트롤의 상태를 변경 하는 일을 담당 합니다. 다음 예제에서는 `NumericUpDown` 컨트롤이 <xref:System.Windows.VisualStateManager.GoToState%2A> 메서드를 호출 하 여 `Value` 0 이상인 경우 `Positive` 상태로 전환 하 고 `Negative`가 0 보다 작은 경우 `Value` 상태를 호출 하는 방법을 보여 줍니다.

[!code-csharp[VSMCustomControl#ValueStateChange](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
[!code-vb[VSMCustomControl#ValueStateChange](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]

<xref:System.Windows.VisualStateManager.GoToState%2A> 메서드는 스토리 보드를 적절 하 게 시작 및 중지 하는 데 필요한 논리를 수행 합니다. 컨트롤을 호출 하는 경우 <xref:System.Windows.VisualStateManager.GoToState%2A> 해당 상태를 변경 하는 <xref:System.Windows.VisualStateManager> 다음을 수행 합니다.

- 컨트롤에 <xref:System.Windows.Media.Animation.Storyboard>있는 <xref:System.Windows.VisualState> 있으면 storyboard가 시작 됩니다. 그런 다음 경우는 <xref:System.Windows.VisualState> 가 컨트롤에서 제공 되는 <xref:System.Windows.Media.Animation.Storyboard>, 스토리 보드 끝입니다.

- 컨트롤이 이미 지정 된 상태에 있는 경우 <xref:System.Windows.VisualStateManager.GoToState%2A> 작업을 수행 하지 않고 `true`을 반환 합니다.

- 지정 된 상태가 `control`의 <xref:System.Windows.Controls.ControlTemplate>에 없는 경우 <xref:System.Windows.VisualStateManager.GoToState%2A>는 아무런 작업도 수행 하지 않고 `false`를 반환 합니다.

#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>R 사용에 대 한 모범 사례

컨트롤의 상태를 유지 관리 하려면 다음을 수행 하는 것이 좋습니다.

- 속성을 사용 하 여 상태를 추적 합니다.

- 상태 간을 전환 하는 도우미 메서드를 만듭니다.

`NumericUpDown` 컨트롤은 `Value` 속성을 사용 하 여 `Positive` 또는 `Negative` 상태 인지 여부를 추적 합니다.  또한 `NumericUpDown` 컨트롤은 <xref:System.Windows.UIElement.IsFocused%2A> 속성을 추적 하는 `Focused` 및 `UnFocused` 상태를 정의 합니다. 자연스럽 게 컨트롤의 속성과 일치 하지 않는 상태를 사용 하는 경우 상태를 추적 하는 개인 속성을 정의할 수 있습니다.

모든 상태를 중앙에서 <xref:System.Windows.VisualStateManager>로 업데이트 하 고 코드를 관리 가능 하 게 유지 하는 단일 메서드입니다. 다음 예제에서는 `UpdateStates``NumericUpDown` 컨트롤의 도우미 메서드를 보여 줍니다. `Value`가 0 보다 크거나 같은 경우 <xref:System.Windows.Controls.Control>는 `Positive` 상태에 있습니다.  `Value`이 0 보다 작은 경우에는 컨트롤이 `Negative` 상태가 됩니다.  <xref:System.Windows.UIElement.IsFocused%2A> `true`되 면 컨트롤이 `Focused` 상태에 있습니다. 그렇지 않으면 `Unfocused` 상태입니다.  컨트롤은 상태 변경 내용에 관계 없이 상태를 변경 해야 할 때마다 `UpdateStates`를 호출할 수 있습니다.

[!code-csharp[VSMCustomControl#UpdateStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
[!code-vb[VSMCustomControl#UpdateStates](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]

컨트롤이 이미 해당 <xref:System.Windows.VisualStateManager.GoToState%2A> 상태에 있는 경우 상태 이름을 <xref:System.Windows.VisualStateManager.GoToState%2A>에 전달 하는 경우에는 아무 작업도 수행 하지 않으므로 컨트롤의 현재 상태를 확인할 필요가 없습니다.  예를 들어 `Value` 음수에서 다른 음수로 변경 하는 경우 `Negative` 상태의 storyboard는 중단 되지 않으며 사용자가 컨트롤의 변경 내용을 볼 수 없습니다.

<xref:System.Windows.VisualStateManager>은 <xref:System.Windows.VisualStateGroup> 개체를 사용 하 여 <xref:System.Windows.VisualStateManager.GoToState%2A>를 호출할 때 종료할 상태를 결정 합니다. 컨트롤은 <xref:System.Windows.Controls.ControlTemplate>에 정의 된 각 <xref:System.Windows.VisualStateGroup>에 대해 항상 한 가지 상태 이며 동일한 <xref:System.Windows.VisualStateGroup>에서 다른 상태로 전환 되는 경우에만 상태를 유지 합니다. 예를 들어 `NumericUpDown` 컨트롤의 <xref:System.Windows.Controls.ControlTemplate>는 한 <xref:System.Windows.VisualState>의 `Positive` 및 `Negative`<xref:System.Windows.VisualStateGroup> 개체를 정의 하 고 `Focused` 개체와 `Unfocused`개체를 서로 <xref:System.Windows.VisualState> 합니다. (컨트롤이 `Positive` 상태에서 `Negative` 상태로 이동 하거나 그 반대로 이동 하는 경우이 항목의 [전체 예제](#complete_example) 단원에 정의 된 `Focused` 및 <xref:System.Windows.VisualState> `Unfocused`를 확인할 수 있습니다. 컨트롤은 `Focused` 또는 `Unfocused` 상태로 유지 됩니다.

컨트롤의 상태가 변경 될 수 있는 세 가지 일반적인 위치는 다음과 같습니다.

- <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Control>에 적용 됩니다.

- 속성이 변경 되는 경우

- 이벤트가 발생 하는 경우

다음 예에서는 이러한 경우 `NumericUpDown` 컨트롤의 상태를 업데이트 하는 방법을 보여 줍니다.

<xref:System.Windows.Controls.ControlTemplate> 적용 될 때 컨트롤이 올바른 상태로 표시 되도록 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 메서드에서 컨트롤의 상태를 업데이트 해야 합니다. 다음 예제에서는 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>에서 `UpdateStates`를 호출 하 여 컨트롤이 적절 한 상태에 있는지 확인 합니다.  예를 들어 `NumericUpDown` 컨트롤을 만든 다음 <xref:System.Windows.Controls.Control.Foreground%2A>을 녹색으로 설정 하 고 `Value`를-5로 설정 한다고 가정 합니다.  `NumericUpDown` 컨트롤에 <xref:System.Windows.Controls.ControlTemplate> 적용 될 때 `UpdateStates`를 호출 하지 않으면 컨트롤이 `Negative` 상태가 아니고 값이 빨강 대신 녹색입니다.  `UpdateStates`를 호출 하 여 컨트롤을 `Negative` 상태로 전환 해야 합니다.

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

속성이 변경 될 때 컨트롤의 상태를 업데이트 해야 하는 경우가 종종 있습니다. 다음 예제에서는 전체 `ValueChangedCallback` 메서드를 보여 줍니다. `Value` 변경 될 때 `ValueChangedCallback`가 호출 되기 때문에 메서드는 긍정에서 음수로 또는 그 반대로 변경 `Value` 경우 `UpdateStates`를 호출 합니다. 이 경우 컨트롤은 상태를 변경 하지 않기 때문에 `Value` 변경 하는 경우 `UpdateStates`를 호출 하는 것은 가능 하지만 긍정 또는 음수는 그대로 유지 됩니다.

[!code-csharp[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
[!code-vb[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]

이벤트가 발생할 때 상태를 업데이트 해야 할 수도 있습니다. 다음 예에서는 `NumericUpDown`이 <xref:System.Windows.Controls.Control>에서 `UpdateStates`를 호출 하 여 <xref:System.Windows.UIElement.GotFocus> 이벤트를 처리 하는 방법을 보여 줍니다.

[!code-csharp[VSMCustomControl#OnGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
[!code-vb[VSMCustomControl#OnGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]

<xref:System.Windows.VisualStateManager>를 사용 하 여 컨트롤의 상태를 관리할 수 있습니다. <xref:System.Windows.VisualStateManager>를 사용 하 여 컨트롤이 상태 간을 올바르게 전환 하는지 확인 합니다.  <xref:System.Windows.VisualStateManager>사용 하기 위해이 섹션에 설명 된 권장 사항을 따르는 경우 컨트롤의 코드를 읽고 유지 관리할 수 있습니다.

<a name="providing_the_control_contract"></a>

## <a name="providing-the-control-contract"></a>컨트롤 계약 제공

<xref:System.Windows.Controls.ControlTemplate> 작성자가 템플릿에 넣을 항목을 알 수 있도록 컨트롤 계약을 제공 합니다. 컨트롤 계약에는 세 가지 요소가 있습니다.

- 컨트롤 논리가 사용하는 시각적 요소

- 컨트롤의 상태 및 각 상태가 속해 있는 그룹

- 컨트롤에 시각적으로 영향을 미치는 공용 속성

새 <xref:System.Windows.Controls.ControlTemplate>을 만드는 사용자는 컨트롤의 논리에서 사용 하는 <xref:System.Windows.FrameworkElement> 개체, 각 개체의 형식 및 해당 이름을 알고 있어야 합니다. 또한 <xref:System.Windows.Controls.ControlTemplate> 작성자는 컨트롤이 있을 수 있는 각 상태에 대 한 이름과 상태 <xref:System.Windows.VisualStateGroup>를 알고 있어야 합니다.

`NumericUpDown` 예제로 돌아가면 컨트롤은 <xref:System.Windows.Controls.ControlTemplate>에 다음과 같은 <xref:System.Windows.FrameworkElement> 개체가 있다고 가정 합니다.

- `UpButton`이라는 <xref:System.Windows.Controls.Primitives.RepeatButton>입니다.

- `DownButton.` 라는 <xref:System.Windows.Controls.Primitives.RepeatButton>

 컨트롤의 상태는 다음과 같을 수 있습니다.

- `ValueStates`<xref:System.Windows.VisualStateGroup>

  - `Positive`

  - `Negative`

- `FocusStates`<xref:System.Windows.VisualStateGroup>

  - `Focused`

  - `Unfocused`

컨트롤에 필요한 <xref:System.Windows.FrameworkElement> 개체를 지정 하려면 필요한 요소의 이름과 유형을 지정 하는 <xref:System.Windows.TemplatePartAttribute>을 사용 합니다.  컨트롤의 가능한 상태를 지정 하려면 상태 <xref:System.Windows.VisualStateGroup> 이름과 해당 이름을 지정 하는 <xref:System.Windows.TemplateVisualStateAttribute>을 사용 합니다.  <xref:System.Windows.TemplatePartAttribute>를 배치 하 고 컨트롤의 클래스 정의에 <xref:System.Windows.TemplateVisualStateAttribute> 합니다.

컨트롤의 모양에 영향을 주는 모든 public 속성은 컨트롤 계약의 일부 이기도 합니다.

다음 예제에서는 `NumericUpDown` 컨트롤의 <xref:System.Windows.FrameworkElement> 개체 및 상태를 지정 합니다.

[!code-csharp[VSMCustomControl#ControlContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
[!code-vb[VSMCustomControl#ControlContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]

<a name="complete_example"></a>

## <a name="complete-example"></a>완성된 예제

다음 예제는 `NumericUpDown` 컨트롤에 대 한 전체 <xref:System.Windows.Controls.ControlTemplate>입니다.

[!code-xaml[VSMCustomControl#NUDTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]

다음 예제에 대 한 논리는 `NumericUpDown`합니다.

[!code-csharp[VSMCustomControl#ControlLogic](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
[!code-vb[VSMCustomControl#ControlLogic](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]

## <a name="see-also"></a>참고 항목

- [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)
- [컨트롤 사용자 지정](control-customization.md)
