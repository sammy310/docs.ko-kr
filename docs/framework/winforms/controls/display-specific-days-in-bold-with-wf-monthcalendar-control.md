---
title: MonthCalendar 컨트롤을 사용 하 여 특정 날짜를 굵게 표시
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], displaying dates in bold
- examples [Windows Forms], calendar controls
- GetDayBold event
- MonthCalendar control [Windows Forms], dates displayed in bold
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
ms.openlocfilehash: 377eb76f562fff20aae2136ddb7130516d2d76f7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745886"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a>방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시
Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤은 날짜를 단수형 또는 반복 단위로 굵게 표시할 수 있습니다. 이 작업을 수행 하 여 휴일, 주말 등의 특수 날짜를 강조할 수 있습니다.  
  
 이 기능을 제어 하는 세 가지 속성이 있습니다. <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> 속성은 단일 날짜를 포함 합니다. <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> 속성은 매년 굵게 표시 되는 날짜를 포함 합니다. <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> 속성은 매월 굵게 표시 되는 날짜를 포함 합니다. 이러한 각 속성은 <xref:System.DateTime> 개체의 배열을 포함 합니다. 이러한 목록 중 하나에서 날짜를 추가 하거나 제거 하려면 <xref:System.DateTime> 개체를 추가 하거나 제거 해야 합니다.  
  
### <a name="to-make-a-date-appear-in-bold-type"></a>날짜를 굵게 표시 하려면  
  
1. <xref:System.DateTime> 개체를 만듭니다.  
  
    ```vb  
    Dim myVacation1 As Date = New DateTime(2001, 6, 10)  
    Dim myVacation2 As Date = New DateTime(2001, 6, 17)  
    ```  
  
    ```csharp  
    DateTime myVacation1 = new DateTime(2001, 6, 10);  
    DateTime myVacation2 = new DateTime(2001, 6, 17);  
    ```  
  
    ```cpp  
    DateTime myVacation1 = DateTime(2001, 6, 10);  
    DateTime myVacation2 = DateTime(2001, 6, 17);  
    ```  
  
2. <xref:System.Windows.Forms.MonthCalendar> 컨트롤의 <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>또는 <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> 메서드를 호출 하 여 한 날짜를 굵게 표시 합니다.  
  
    ```vb  
    MonthCalendar1.AddBoldedDate(myVacation1)  
    MonthCalendar1.AddBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.AddBoldedDate(myVacation1);  
    monthCalendar1.AddBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->AddBoldedDate(myVacation1);  
    monthCalendar1->AddBoldedDate(myVacation2);  
    ```  
  
     -또는-  
  
     <xref:System.DateTime> 개체의 배열을 만들고이를 속성 중 하나에 할당 하 여 날짜 집합을 한 번에 모두 굵게 만듭니다.  
  
    ```vb  
    Dim VacationDates As DateTime() = {myVacation1, myVacation2}  
    MonthCalendar1.BoldedDates = VacationDates  
    ```  
  
    ```csharp  
    DateTime[] VacationDates = {myVacation1, myVacation2};  
    monthCalendar1.BoldedDates = VacationDates;  
    ```  
  
    ```cpp  
    Array<DateTime>^ VacationDates = {myVacation1, myVacation2};  
    monthCalendar1->BoldedDates = VacationDates;  
    ```  
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a>날짜가 일반 글꼴로 표시 되도록 하려면  
  
1. <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>또는 <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> 메서드를 호출 하 여 굵게 표시 된 단일 날짜를 일반 글꼴로 표시 합니다.  
  
    ```vb  
    MonthCalendar1.RemoveBoldedDate(myVacation1)  
    MonthCalendar1.RemoveBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveBoldedDate(myVacation1);  
    monthCalendar1.RemoveBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveBoldedDate(myVacation1);  
    monthCalendar1->RemoveBoldedDate(myVacation2);  
    ```  
  
     -또는-  
  
     <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>또는 <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> 메서드를 호출 하 여 세 목록 중 하나에서 굵게 표시 된 날짜를 모두 제거 합니다.  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> 메서드를 호출 하 여 글꼴의 모양을 업데이트 합니다.  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a>참고 항목

- [MonthCalendar 컨트롤](monthcalendar-control-windows-forms.md)
- [방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [방법: Windows Forms MonthCalendar 컨트롤의 모양 변경](how-to-change-monthcalendar-control-appearance.md)
- [방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시](display-more-than-one-month-wf-monthcalendar-control.md)
