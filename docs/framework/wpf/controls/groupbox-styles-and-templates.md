---
title: GroupBox 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 474cda0abc6a18c015836c749c78f4d33aa5abd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187473"
---
# <a name="groupbox-styles-and-templates"></a>GroupBox 스타일 및 템플릿
<a name="introduction"></a>이 항목에서는 <xref:System.Windows.Controls.GroupBox> 컨트롤의 스타일과 템플릿에 대해 설명합니다. 기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다. 자세한 내용은 [컨트롤에 대한 템플릿 만들기를](../../../desktop-wpf/themes/how-to-create-apply-template.md)참조하십시오.  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a>그룹박스 부품  
 컨트롤에는 <xref:System.Windows.Controls.GroupBox> 명명된 부품이 없습니다.  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a>그룹박스 상태  
 다음 표에는 컨트롤의 시각적 <xref:System.Windows.Controls.GroupBox> 상태가 나열됩니다.  
  
|VisualState 이름|VisualStateGroup 이름|Description|  
|-|-|-|  
|Valid|ValidationStates|컨트롤은 클래스를 <xref:System.Windows.Controls.Validation> 사용하고 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 `false`속성은 입니다.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 속성은 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 속성은 `true` 컨트롤에 포커스가 없습니다.|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a>그룹박스 제어템플릿 예제  
 다음 예제에서는 컨트롤에 <xref:System.Windows.Controls.ControlTemplate> 대한 <xref:System.Windows.Controls.GroupBox> a를 정의하는 방법을 보여 주며 있습니다.  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 은 <xref:System.Windows.Controls.ControlTemplate> 다음 리소스 중 하나 이상을 사용합니다.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 스타일 및 템플릿](control-styles-and-templates.md)
- [컨트롤 사용자 지정](control-customization.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [컨트롤용 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)
