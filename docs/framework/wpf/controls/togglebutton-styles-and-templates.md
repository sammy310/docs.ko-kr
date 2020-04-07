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
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805915"
---
# <a name="togglebutton-styles-and-templates"></a>ToggleButton 스타일 및 템플릿

이 항목에서는 <xref:System.Windows.Controls.Primitives.ToggleButton> 컨트롤의 스타일과 템플릿에 대해 설명합니다. 기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다. 자세한 내용은 [컨트롤에 대한 템플릿 만들기를](../../../desktop-wpf/themes/how-to-create-apply-template.md)참조하십시오.

## <a name="togglebutton-parts"></a>토글 버튼 부품

컨트롤에는 <xref:System.Windows.Controls.Primitives.ToggleButton> 명명된 부품이 없습니다.

## <a name="togglebutton-states"></a>토글버튼 상태

다음 표에는 컨트롤의 시각적 <xref:System.Windows.Controls.Primitives.ToggleButton> 상태가 나열됩니다.

|VisualState 이름|VisualStateGroup 이름|Description|
|-|-|-|
|정상|CommonStates|기본 상태입니다.|
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|
|누름|CommonStates|컨트롤을 눌렀습니다.|
|사용 안 함|CommonStates|컨트롤이 비활성화되었습니다.|
|포커스 있음|FocusStates|컨트롤에 포커스가 있습니다.|
|포커스 없음|FocusStates|컨트롤에 포커스가 없습니다.|
|선택|체크스테이트|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>은 `true`입니다.|
|선택 취소됨|체크스테이트|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>은 `false`입니다.|
|확정 되지 않은|체크스테이트|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>가 `true`이고 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>이 `null`인 경우|
|Valid|ValidationStates|컨트롤은 클래스를 <xref:System.Windows.Controls.Validation> 사용하고 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 `false`속성은 입니다.|
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 속성은 `true` 컨트롤에 포커스가 있습니다.|
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 속성이며 `true` 컨트롤에 포커스가 없습니다.|

> [!NOTE]
> 컨트롤 템플릿에 확정되지 않은 시각적 상태가 없으면 선택되지 않은 시각적 상태가 기본 시각적 상태로 사용됩니다.

## <a name="togglebutton-controltemplate-example"></a>토글 버튼 제어템플릿 예제

다음 예제에서는 컨트롤에 <xref:System.Windows.Controls.ControlTemplate> 대한 <xref:System.Windows.Controls.Primitives.ToggleButton> a를 정의하는 방법을 보여 주며 있습니다.

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 스타일 및 템플릿](control-styles-and-templates.md)
- [컨트롤 사용자 지정](control-customization.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [컨트롤용 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)
