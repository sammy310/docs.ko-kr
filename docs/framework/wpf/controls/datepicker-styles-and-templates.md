---
title: DatePicker 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
ms.openlocfilehash: 323768b6221061d46446ab18f85555f5f7415e74
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460373"
---
# <a name="datepicker-styles-and-templates"></a>DatePicker 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.DatePicker> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다. 기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다. 자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.  
  
## <a name="datepicker-parts"></a>DatePicker 파트  
 다음 표에서는 <xref:System.Windows.Controls.DatePicker> 컨트롤의 명명 된 파트를 나열 합니다.  
  
|파트|Type|설명|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|컨트롤의 루트입니다.|  
|PART_Button|<xref:System.Windows.Controls.Button>|<xref:System.Windows.Controls.Calendar>를 열고 닫는 단추입니다.|  
|PART_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|날짜를 입력할 수 있는 입력란입니다.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|<xref:System.Windows.Controls.DatePicker> 컨트롤의 popup입니다.|  
  
## <a name="datepicker-states"></a>DatePicker 상태  
 다음 표에서는 <xref:System.Windows.Controls.DatePicker> 컨트롤의 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.DatePicker> 사용 하지 않도록 설정 되었습니다.|  
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|  
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우|  
  
## <a name="datepickertextbox-parts"></a>DatePickerTextBox 파트  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 컨트롤의 명명 된 파트를 나열 합니다.  
  
|파트|Type|설명|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|<xref:System.Windows.Controls.DatePicker>의 초기 텍스트를 포함 하는 요소입니다.|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.FrameworkElement>포함할 수 있는 시각적 요소입니다. <xref:System.Windows.Controls.TextBox> 텍스트가이 요소에 표시 됩니다.|  
  
## <a name="datepickertextbox-states"></a>DatePickerTextBox 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 컨트롤의 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.Primitives.DatePickerTextBox> 사용 하지 않도록 설정 되었습니다.|  
|MouseOver|CommonStates|마우스 포인터가 <xref:System.Windows.Controls.Primitives.DatePickerTextBox>위에 배치 됩니다.|  
|ReadOnly|CommonStates|사용자는 <xref:System.Windows.Controls.Primitives.DatePickerTextBox>의 텍스트를 변경할 수 없습니다.|  
|포커스 있음|FocusStates|컨트롤에 포커스가 있습니다.|  
|포커스 없음|FocusStates|컨트롤에 포커스가 없습니다.|  
|워터 마크|WatermarkStates|컨트롤은 초기 텍스트를 표시 합니다.  사용자가 텍스트를 입력 하거나 날짜를 선택 하지 않은 경우 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 상태입니다.|  
|Unwatermarked|WatermarkStates|사용자가 <xref:System.Windows.Controls.Primitives.DatePickerTextBox>에 텍스트를 입력 했거나 <xref:System.Windows.Controls.DatePicker>날짜를 선택 했습니다.|  
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|  
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 고 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 고 컨트롤에 포커스가 없는 경우|  
  
## <a name="datepicker-controltemplate-example"></a>DatePicker ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.DatePicker> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
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
