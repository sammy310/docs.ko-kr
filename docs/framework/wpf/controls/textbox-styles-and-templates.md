---
title: TextBox 스타일 및 템플릿
description: Windows Presentation Foundation TextBox 컨트롤에 대 한 스타일 및 템플릿에 대해 알아봅니다. ControlTemplate를 수정 하 여 컨트롤에 고유한 모양을 제공 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 0e15fd40f5590ee46da49cc6c0d5fb30e051f7e4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164728"
---
# <a name="textbox-styles-and-templates"></a>TextBox 스타일 및 템플릿
이 항목에서는 컨트롤의 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.TextBox> . 기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다. 자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.  
  
## <a name="textbox-parts"></a>텍스트 상자 파트  
 다음 표에서는 컨트롤의 명명 된 파트를 나열 합니다 <xref:System.Windows.Controls.TextBox> .  
  
|부분|Type|Description|  
|-|-|-|  
|PART_ContentHost|<xref:System.Windows.FrameworkElement>|을 포함할 수 있는 시각적 요소입니다 <xref:System.Windows.FrameworkElement> . 의 텍스트가 <xref:System.Windows.Controls.TextBox> 이 요소에 표시 됩니다.|  
  
## <a name="textbox-states"></a>텍스트 상자 상태  
 다음 표에서는 컨트롤의 시각적 상태를 보여 줍니다 <xref:System.Windows.Controls.TextBox> .  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|----------------------|---------------------------|-----------------|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|  
|사용 안 함|CommonStates|컨트롤이 비활성화되었습니다.|  
|ReadOnly|CommonStates|사용자가의 텍스트를 변경할 수 없습니다 <xref:System.Windows.Controls.TextBox> .|  
|포커스 있음|FocusStates|컨트롤에 포커스가 있습니다.|  
|포커스 없음|FocusStates|컨트롤에 포커스가 없습니다.|  
|Valid|ValidationStates|컨트롤은 클래스를 사용 하 <xref:System.Windows.Controls.Validation> 고 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false` 입니다.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성은 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성이 `true` 컨트롤에 포커스가 없는 경우|  
  
## <a name="textbox-controltemplate-example"></a>텍스트 상자 ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 대 한을 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 스타일 및 템플릿](control-styles-and-templates.md)
- [컨트롤 사용자 지정](control-customization.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [컨트롤의 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)
