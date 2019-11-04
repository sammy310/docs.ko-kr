---
title: Calendar 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Calendar
- templates [WPF], Calendar
- states [WPF], Calendar
- parts [WPF], Calendar
- Calendar [WPF], styles and templates
- ControlTemplate [WPF], Calendar
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
ms.openlocfilehash: 49d9ced42572ac06a4ff824ec41a59c14497d215
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460930"
---
# <a name="calendar-styles-and-templates"></a>Calendar 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.Calendar> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다. 기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다. 자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.  
  
## <a name="calendar-parts"></a>일정 부분  
 다음 표에서는 <xref:System.Windows.Controls.Calendar> 컨트롤의 명명 된 파트를 나열 합니다.  
  
|파트|Type|설명|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|<xref:System.Windows.Controls.Calendar>에 현재 표시 된 월 또는 연도입니다.|  
|PART_Root|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Primitives.CalendarItem>를 포함 하는 패널입니다.|  
  
## <a name="calendar-states"></a>일정 상태  
 다음 표에서는 <xref:System.Windows.Controls.Calendar> 컨트롤의 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|----------------------|---------------------------|-----------------|  
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|  
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우|  
  
## <a name="calendaritem-parts"></a>CalendarItem 파트  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.CalendarItem> 컨트롤의 명명 된 파트를 나열 합니다.  
  
|파트|Type|설명|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|컨트롤의 루트입니다.|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|클릭 하면 일정의 이전 페이지를 표시 하는 단추입니다.|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|클릭할 때 달력의 다음 페이지를 표시 하는 단추입니다.|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|월 모드, 연도 모드 및 10 년 모드 간을 전환할 수 있도록 하는 단추입니다.|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|월 모드에 있을 때 콘텐츠를 호스팅합니다.|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|연도 또는 10 년 모드에서 콘텐츠를 호스팅합니다.|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|비활성 상태의 오버레이입니다.|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|시각적 구조를 설명 하는 <xref:System.Windows.DataTemplate>입니다.|  
  
## <a name="calendaritem-states"></a>CalendarItem 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.CalendarItem> 컨트롤의 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|표준 상태|CommonStates|기본 상태입니다.|  
|사용 안 함 상태|CommonStates|<xref:System.Windows.UIElement.IsEnabled%2A> 속성이 `false`때의 일정 상태입니다.|  
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|  
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우|  
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|  
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우|  
  
## <a name="calendardaybutton-parts"></a>CalendarDayButton 파트  
 <xref:System.Windows.Controls.Primitives.CalendarDayButton> 컨트롤에는 명명 된 파트가 없습니다.  
  
## <a name="calendardaybutton-states"></a>CalendarDayButton 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.CalendarDayButton> 컨트롤의 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton> 사용 하지 않도록 설정 되었습니다.|  
|MouseOver|CommonStates|마우스 포인터가 <xref:System.Windows.Controls.Primitives.CalendarDayButton>위에 배치 됩니다.|  
|누름|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton>를 눌렀습니다.|  
|선택함|SelectionStates|단추가 선택 됩니다.|  
|선택 취소|SelectionStates|단추가 선택 되어 있지 않습니다.|  
|CalendarButtonFocused 있는|CalendarButtonFocusStates|단추에 포커스가 있습니다.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|단추에 포커스가 없습니다.|  
|포커스 있음|FocusStates|단추에 포커스가 있습니다.|  
|포커스 없음|FocusStates|단추에 포커스가 없습니다.|  
|활성|ActiveStates|단추가 활성 상태입니다.|  
|비활성|ActiveStates|단추가 비활성 상태입니다.|  
|RegularDay|DayStates|단추가 <xref:System.DateTime.Today%2A?displayProperty=nameWithType>를 나타내지 않습니다.|  
|오늘|DayStates|단추는 <xref:System.DateTime.Today%2A?displayProperty=nameWithType>나타냅니다.|  
|NormalDay|블랙 아웃 상태|단추는 선택할 수 있는 날짜를 나타냅니다.|  
|블랙 아웃 기념일|블랙 아웃 상태|단추는 선택할 수 없는 날짜를 나타냅니다.|  
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|  
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우|  
  
## <a name="calendarbutton-parts"></a>CalendarButton 파트  
 <xref:System.Windows.Controls.Primitives.CalendarButton> 컨트롤에는 명명 된 파트가 없습니다.  
  
## <a name="calendarbutton-states"></a>CalendarButton 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.CalendarButton> 컨트롤의 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton> 사용 하지 않도록 설정 되었습니다.|  
|MouseOver|CommonStates|마우스 포인터가 <xref:System.Windows.Controls.Primitives.CalendarButton>위에 배치 됩니다.|  
|누름|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton>를 눌렀습니다.|  
|선택함|SelectionStates|단추가 선택 됩니다.|  
|선택 취소|SelectionStates|단추가 선택 되어 있지 않습니다.|  
|CalendarButtonFocused 있는|CalendarButtonFocusStates|단추에 포커스가 있습니다.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|단추에 포커스가 없습니다.|  
|포커스 있음|FocusStates|단추에 포커스가 있습니다.|  
|포커스 없음|FocusStates|단추에 포커스가 없습니다.|  
|활성|ActiveStates|단추가 활성 상태입니다.|  
|비활성|ActiveStates|단추가 비활성 상태입니다.|  
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|  
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우|  
  
## <a name="calendar-controltemplate-example"></a>Calendar ControlTemplate 예  
 다음 예제에서는 <xref:System.Windows.Controls.Calendar> 컨트롤 및 관련 형식에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.  
  
 [!code-xaml[ControlTemplateExamples#Calendar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
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
