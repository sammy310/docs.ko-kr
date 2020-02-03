---
title: DateTimePicker 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
ms.openlocfilehash: 63271dd91116c1f68d426f3ed5aa710644ded928
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746936"
---
# <a name="datetimepicker-control-overview-windows-forms"></a>DateTimePicker 컨트롤 개요(Windows Forms)
사용자는 Windows Forms <xref:System.Windows.Forms.DateTimePicker> 컨트롤을 사용 하 여 날짜 또는 시간 목록에서 단일 항목을 선택할 수 있습니다. 날짜를 나타내는 데 사용 되는 경우 두 부분, 즉 텍스트에 날짜가 표시 된 드롭다운 목록과 목록 옆에 있는 아래쪽 화살표를 클릭 하면 표시 되는 눈금이 표시 됩니다. 그리드는 여러 날짜를 선택 하는 데 사용할 수 있는 <xref:System.Windows.Forms.MonthCalendar> 컨트롤 처럼 보입니다. <xref:System.Windows.Forms.MonthCalendar> 컨트롤에 대 한 자세한 내용은 [MonthCalendar 컨트롤 개요](monthcalendar-control-overview-windows-forms.md)를 참조 하세요.  
  
## <a name="key-properties"></a>키 속성  
 날짜 대신 시간을 선택 하거나 편집 하기 위한 컨트롤로 <xref:System.Windows.Forms.DateTimePicker> 표시 하려면 <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> 속성을 `true`로 설정 하 고 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성을 <xref:System.Windows.Forms.DateTimePickerFormat.Time>로 설정 합니다. 자세한 내용은 [방법: DateTimePicker 컨트롤을 사용 하 여 시간 표시를](how-to-display-time-with-the-datetimepicker-control.md)참조 하세요.  
  
 <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> 속성이 `true`로 설정 되 면 컨트롤에서 선택한 날짜 옆에 확인란이 표시 됩니다. 확인란을 선택 하면 선택한 날짜-시간 값을 업데이트할 수 있습니다. 확인란이 비어 있으면 값을 사용할 수 없는 것으로 나타납니다.  
  
 컨트롤의 <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> 및 <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> 속성은 날짜 및 시간 범위를 결정 합니다. <xref:System.Windows.Forms.DateTimePicker.Value%2A> 속성은 컨트롤이로 설정 된 현재 날짜 및 시간을 포함 합니다. 자세한 내용은 [방법: Windows Forms DateTimePicker 컨트롤을 사용 하 여 날짜 설정 및 반환](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)을 참조 하세요. 값은 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성 (<xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>또는 <xref:System.Windows.Forms.DateTimePickerFormat.Custom>에 의해 설정 되는 네 가지 형식으로 표시 될 수 있습니다. 사용자 지정 형식을 선택 하는 경우 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> 속성을 적절 한 문자열로 설정 해야 합니다. 자세한 내용은 [방법: Windows Forms DateTimePicker 컨트롤을 사용 하 여 날짜를 사용자 지정 형식으로 표시](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
- [방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
