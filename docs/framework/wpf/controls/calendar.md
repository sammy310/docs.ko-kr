---
title: 일정
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
ms.openlocfilehash: e99a716e7ca8f7b2c9ed11543f37e0b8cb7422a6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460814"
---
# <a name="calendar"></a>일정
달력을 사용 하면 사용자가 시각적 일정 표시를 사용 하 여 날짜를 선택할 수 있습니다.  
  
 <xref:System.Windows.Controls.Calendar> 컨트롤은 자체적으로 사용 하거나 <xref:System.Windows.Controls.DatePicker> 컨트롤의 드롭다운 부분으로 사용할 수 있습니다. 자세한 내용은 <xref:System.Windows.Controls.DatePicker>을 참조하십시오.  
  
 다음 그림에서는 두 개의 <xref:System.Windows.Controls.Calendar> 컨트롤, 선택 항목 및 블랙 아웃 날짜 및가 없는 컨트롤을 보여 줍니다.  
  
 ![Calendar 컨트롤](./media/ndp-calendarcontrols.png "NDP_CalendarControls")  
Calendar 컨트롤  
  
 다음 표에서는 일반적으로 <xref:System.Windows.Controls.Calendar>와 연결 된 작업에 대 한 정보를 제공 합니다.  
  
|작업|구현|  
|----------|--------------------|  
|선택할 수 없는 날짜를 지정 합니다.|<xref:System.Windows.Controls.Calendar.BlackoutDates%2A> 속성을 사용합니다.|  
|<xref:System.Windows.Controls.Calendar>에 월, 전체 연도 또는 10 년이 표시 되도록 합니다.|<xref:System.Windows.Controls.Calendar.DisplayMode%2A> 속성을 월, 연도 또는 10 년으로 설정 합니다.|  
|사용자가 날짜, 날짜 범위 또는 여러 날짜 범위를 선택할 수 있는지 여부를 지정 합니다.|<xref:System.Windows.Controls.Calendar.SelectionMode%2A>를 사용 합니다.|  
|<xref:System.Windows.Controls.Calendar> 표시 되는 날짜 범위를 지정 합니다.|<xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> 및 <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A> 속성을 사용 합니다.|  
|현재 날짜를 강조 표시할지 여부를 지정 합니다.|<xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> 속성을 사용합니다. 기본적으로 <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> `true`됩니다.|  
|<xref:System.Windows.Controls.Calendar>의 크기를 변경 합니다.|<xref:System.Windows.Controls.Viewbox>를 사용 하거나 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성을 <xref:System.Windows.Media.ScaleTransform>로 설정 합니다. <xref:System.Windows.Controls.Calendar>의 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 설정 하면 실제 달력에서 크기가 변경 되지 않습니다.|  
  
 <xref:System.Windows.Controls.Calendar> 컨트롤은 마우스나 키보드를 사용 하 여 기본적인 탐색을 제공 합니다. 다음 표에서는 키보드 탐색을 요약 합니다.  
  
|키 조합|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|작업|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|화살표나|<xref:System.Windows.Controls.CalendarMode.Month>|<xref:System.Windows.Controls.Calendar.SelectionMode%2A> 속성이 <xref:System.Windows.Controls.CalendarSelectionMode.None>로 설정 되지 않은 경우 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 속성을 변경 합니다.|  
|화살표나|<xref:System.Windows.Controls.CalendarMode.Year>|<xref:System.Windows.Controls.Calendar.DisplayDate%2A> 속성의 월을 변경 합니다. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 변경 되지 않습니다.|  
|화살표나|<xref:System.Windows.Controls.CalendarMode.Decade>|<xref:System.Windows.Controls.Calendar.DisplayDate%2A>연도를 변경 합니다. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 변경 되지 않습니다.|  
|SHIFT + 화살표|<xref:System.Windows.Controls.CalendarMode.Month>|<xref:System.Windows.Controls.Calendar.SelectionMode%2A> <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> 또는 <xref:System.Windows.Controls.CalendarSelectionMode.None>로 설정 되지 않은 경우는 선택한 날짜 범위를 확장 합니다.|  
|홈|<xref:System.Windows.Controls.CalendarMode.Month>|<xref:System.Windows.Controls.Calendar.SelectedDate%2A>를 현재 달의 첫 번째 날짜로 변경 합니다.|  
|홈|<xref:System.Windows.Controls.CalendarMode.Year>|<xref:System.Windows.Controls.Calendar.DisplayDate%2A> 월을 해당 연도의 첫 번째 달로 변경 합니다. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 변경 되지 않습니다.|  
|홈|<xref:System.Windows.Controls.CalendarMode.Decade>|<xref:System.Windows.Controls.Calendar.DisplayDate%2A> 연도를 10 년의 1 년으로 변경 합니다. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 변경 되지 않습니다.|  
|End|<xref:System.Windows.Controls.CalendarMode.Month>|현재 달의 마지막 날로 <xref:System.Windows.Controls.Calendar.SelectedDate%2A>를 변경 합니다.|  
|End|<xref:System.Windows.Controls.CalendarMode.Year>|<xref:System.Windows.Controls.Calendar.DisplayDate%2A> 월을 해당 연도의 마지막 달로 변경 합니다. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 변경 되지 않습니다.|  
|End|<xref:System.Windows.Controls.CalendarMode.Decade>|<xref:System.Windows.Controls.Calendar.DisplayDate%2A> 연도를 10 년의 작년로 변경 합니다. <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 변경 되지 않습니다.|  
|Ctrl+위쪽 화살표|임의의 값|다음으로 큰 <xref:System.Windows.Controls.Calendar.DisplayMode%2A>로 전환 합니다. <xref:System.Windows.Controls.Calendar.DisplayMode%2A> 이미 <xref:System.Windows.Controls.CalendarMode.Decade>된 경우 아무 작업도 수행 하지 않습니다.|  
|CTRL+DOWN ARROW|임의의 값|다음으로 작은 <xref:System.Windows.Controls.Calendar.DisplayMode%2A>로 전환 합니다. <xref:System.Windows.Controls.Calendar.DisplayMode%2A> 이미 <xref:System.Windows.Controls.CalendarMode.Month>된 경우 아무 작업도 수행 하지 않습니다.|  
|스페이스바 또는 ENTER|<xref:System.Windows.Controls.CalendarMode.Year> 또는 <xref:System.Windows.Controls.CalendarMode.Decade>|포커스가 있는 항목으로 표시 되는 <xref:System.Windows.Controls.CalendarMode.Month> 또는 <xref:System.Windows.Controls.CalendarMode.Year> <xref:System.Windows.Controls.Calendar.DisplayMode%2A>를 전환 합니다.|  
  
## <a name="see-also"></a>참조

- [컨트롤](index.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
