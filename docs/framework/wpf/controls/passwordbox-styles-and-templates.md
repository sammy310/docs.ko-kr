---
title: PasswordBox 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: 4ba90182468466773644c7375059f0cc01675b33
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283468"
---
# <a name="passwordbox-styles-and-templates"></a>PasswordBox 스타일 및 템플릿

이 항목에서는 <xref:System.Windows.Controls.PasswordBox> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다. 기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다. 자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.

## <a name="passwordbox-parts"></a>PasswordBox 파트

다음 표에서는 <xref:System.Windows.Controls.PasswordBox> 컨트롤의 명명 된 파트를 나열 합니다.

|부분|형식|설명|
|-|-|-|
|PART_ContentHost|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.FrameworkElement>포함할 수 있는 시각적 요소입니다. <xref:System.Windows.Controls.PasswordBox> 텍스트가이 요소에 표시 됩니다.|

## <a name="passwordbox-states"></a>PasswordBox 상태

다음 표에서는 <xref:System.Windows.Controls.PasswordBox> 컨트롤의 시각적 상태를 보여 줍니다.

|VisualState 이름|VisualStateGroup 이름|설명|
|-|-|-|
|보통|CommonStates|기본 상태입니다.|
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|
|사용 안 함|CommonStates|컨트롤이 비활성화되었습니다.|
|포커스 있음|FocusStates|컨트롤에 포커스가 있습니다.|
|포커스 없음|FocusStates|컨트롤에 포커스가 없습니다.|
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.|
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우|

## <a name="passwordbox-controltemplate-example"></a>PasswordBox ControlTemplate 예제

다음 예제에서는 <xref:System.Windows.Controls.PasswordBox> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 스타일 및 템플릿](control-styles-and-templates.md)
- [컨트롤 사용자 지정](control-customization.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)
