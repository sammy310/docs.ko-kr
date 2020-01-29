---
title: MonthCalendar 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
ms.openlocfilehash: a9b56164339d03b380a564b21855f6d94ec06af5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734933"
---
# <a name="monthcalendar-control-overview-windows-forms"></a>MonthCalendar 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤은 사용자가 날짜 정보를 보고 설정 하기 위한 직관적인 그래픽 인터페이스를 제공 합니다. 이 컨트롤은 달력을 표시 합니다. 선택한 날짜 범위가 강조 표시 되 고 요일 아래의 열에 정렬 되어 있는 월의 번호가 매겨진 날짜를 포함 하는 표입니다. 월 캡션의 한쪽에 있는 화살표 단추를 클릭 하 여 다른 달을 선택할 수 있습니다. 비슷한 <xref:System.Windows.Forms.DateTimePicker> 컨트롤과 달리이 컨트롤을 사용 하 여 둘 이상의 날짜를 선택할 수 있습니다. <xref:System.Windows.Forms.DateTimePicker> 컨트롤에 대 한 자세한 내용은 [DateTimePicker control](datetimepicker-control-windows-forms.md)을 참조 하세요.  
  
## <a name="configuring-the-monthcalendar-control"></a>MonthCalendar 컨트롤 구성  
 <xref:System.Windows.Forms.MonthCalendar> 컨트롤의 모양은 매우 구성 가능 합니다. 기본적으로 오늘 날짜는 원으로 표시 되며 그리드 아래쪽에도 표시 됩니다. <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> 및 <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> 속성을 `false`로 설정 하 여이 기능을 변경할 수 있습니다. <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> 속성을 `true`설정 하 여 달력에 주 번호를 추가할 수도 있습니다. <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> 속성을 설정 하 여 여러 개월이 가로 및 세로로 표시 되도록 할 수 있습니다. 기본적으로 일요일은 주의 첫째 요일로 표시 되지만 <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> 속성을 사용 하 여 날짜를 지정할 수 있습니다.  
  
 <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>및 <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> 속성에 <xref:System.DateTime> 개체를 추가 하 여 특정 날짜를 1 회, 매년 또는 매월 굵게 표시 하도록 설정할 수도 있습니다. 자세한 내용은 [방법: Windows Forms MonthCalendar 컨트롤을 사용 하 여 특정 날짜를 굵게 표시](display-specific-days-in-bold-with-wf-monthcalendar-control.md)를 참조 하세요.  
  
 <xref:System.Windows.Forms.MonthCalendar> 컨트롤의 키 속성이 <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, 컨트롤에서 선택한 날짜 범위입니다. <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> 값은 <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> 속성에서 설정할 수 있는 최대 일 수를 초과할 수 없습니다. 사용자가 선택할 수 있는 가장 이른 날짜와 가장 늦은 날짜는 <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> 및 <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> 속성에 따라 결정 됩니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.MonthCalendar>
- [MonthCalendar 컨트롤](monthcalendar-control-windows-forms.md)
