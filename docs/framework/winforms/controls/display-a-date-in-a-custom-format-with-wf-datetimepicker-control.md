---
title: DateTimePicker 컨트롤을 사용 하 여 날짜를 사용자 지정 형식으로 표시
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
ms.openlocfilehash: a27dbe737b81af86c0ac50b791bcd87bafe05b4f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745938"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시
Windows Forms <xref:System.Windows.Forms.DateTimePicker> 컨트롤을 사용 하면 컨트롤의 날짜 및 시간 표시를 유연 하 게 지정할 수 있습니다. <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성을 사용 하면 <xref:System.Windows.Forms.DateTimePickerFormat>에 나열 된 미리 정의 된 형식에서 선택할 수 있습니다. 이러한 항목이 용도에 적합 하지 않은 경우 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>에 나열 된 형식 문자를 사용 하 여 고유한 형식 스타일을 만들 수 있습니다.  
  
### <a name="to-display-a-custom-format"></a>사용자 지정 형식을 표시 하려면  
  
1. <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성을 `DateTimePickerFormat.Custom`으로 설정합니다.  
  
2. <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> 속성을 형식 문자열로 설정 합니다.  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### <a name="to-add-text-to-the-formatted-value"></a>서식이 지정 된 값에 텍스트를 추가 하려면  
  
1. 작은따옴표를 사용 하 여 "M"과 같은 서식 문자가 아닌 문자 또는 ":"와 같은 구분 기호를 묶습니다. 예를 들어 아래 서식 문자열은 영어 (미국) 문화권의 "오늘: 05:30:31 년 3 월 02 2012 일 금요일" 형식으로 현재 날짜를 표시 합니다.  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     문화권 설정에 따라 작은따옴표로 묶이지 않은 문자는 변경 될 수 있습니다. 예를 들어 위의 형식 문자열은 영어 (미국) 문화권의 "오늘: 05:30:31 년 3 월 02 2012 일 금요일" 형식으로 현재 날짜를 표시 합니다. 첫 번째 콜론은 "hh: mm: ss"에 있는 구분 문자로 사용할 수 없으므로 작은따옴표로 묶여 있습니다. 다른 문화권에서 형식은 "오늘: 05.30.31 금요일 3 월 02 2012"로 표시 될 수 있습니다.  
  
## <a name="see-also"></a>참조

- [DateTimePicker 컨트롤](datetimepicker-control-windows-forms.md)
- [방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
