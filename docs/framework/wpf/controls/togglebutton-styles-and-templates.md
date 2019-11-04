---
title: ToggleButton 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: 981a487b9935a86595a9caca03b4371326924642
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458229"
---
# <a name="togglebutton-styles-and-templates"></a>ToggleButton 스타일 및 템플릿

이 항목에서는 <xref:System.Windows.Controls.Primitives.ToggleButton> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다. 기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다. 자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.

## <a name="togglebutton-parts"></a>ToggleButton 파트

<xref:System.Windows.Controls.Primitives.ToggleButton> 컨트롤에는 명명 된 파트가 없습니다.

## <a name="togglebutton-states"></a>ToggleButton 상태

다음 표에서는 <xref:System.Windows.Controls.Primitives.ToggleButton> 컨트롤의 시각적 상태를 보여 줍니다.

|VisualState 이름|VisualStateGroup 이름|설명|
|-|-|-|
|보통|CommonStates|기본 상태입니다.|
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|
|누름|CommonStates|컨트롤을 눌렀습니다.|
|Disabled|CommonStates|컨트롤이 비활성화되었습니다.|
|포커스 있음|FocusStates|컨트롤에 포커스가 있습니다.|
|포커스 없음|FocusStates|컨트롤에 포커스가 없습니다.|
|선택한 상태|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>가 `true`입니다.|
|선택 취소|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>가 `false`입니다.|
|않음|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>가 `true`이고 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>이 `null`인 경우|
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.|
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우|

> [!NOTE]
> 컨트롤 템플릿에 확정 되지 않은 시각적 상태가 없으면 선택 되지 않은 시각적 상태가 기본 시각적 상태로 사용 됩니다.

## <a name="togglebutton-controltemplate-example"></a>ToggleButton ControlTemplate 예제

다음 예제에서는 <xref:System.Windows.Controls.Primitives.ToggleButton> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.

## <a name="see-also"></a>참조

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 스타일 및 템플릿](control-styles-and-templates.md)
- [컨트롤 사용자 지정](control-customization.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)
