---
title: MonthCalendar 컨트롤에서 한 달 이상 표시
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], formatting display
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], multiple months
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d197caa2-38a5-4cb4-acc3-562130c2ace3
ms.openlocfilehash: 5d3925bc19ddcd67742f0ab8b5b2e45530820f38
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745893"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시
Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤은 한 번에 최대 12 개월까지 표시할 수 있습니다. 기본적으로 컨트롤은 한 달만 표시 하지만 표시 되는 월 수와 컨트롤 내에 정렬 되는 방법을 지정할 수 있습니다. 달력 차원을 변경 하면 컨트롤의 크기가 조정 되므로 폼에 새 차원에 대 한 충분 한 공간이 있어야 합니다.  
  
### <a name="to-display-multiple-months"></a>여러 월을 표시 하려면  
  
- <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> 속성을 가로 및 세로로 표시할 월 수로 설정 합니다.  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a>참조

- [MonthCalendar 컨트롤](monthcalendar-control-windows-forms.md)
- [방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [방법: Windows Forms MonthCalendar 컨트롤의 모양 변경](how-to-change-monthcalendar-control-appearance.md)
