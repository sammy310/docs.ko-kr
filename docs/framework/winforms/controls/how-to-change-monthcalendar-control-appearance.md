---
title: '방법: Windows Forms MonthCalendar 컨트롤의 모양 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: 2e26f7a9db8e19b584000089f99e99aab7c25a32
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716376"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a>방법: Windows Forms MonthCalendar 컨트롤의 모양 변경
Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤을 사용 하면 여러 가지 방법으로 달력의 모양을 사용자 지정할 수 있습니다. 예를 들어, 색 구성표를 설정할 수 있으며 주 번호 및 현재 날짜를 표시 하거나 숨기려면 선택.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>월 달력의 색 구성표를 변경 하려면  
  
-   와 같은 속성을 설정 <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>하십시오 <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> 및 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>합니다. <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> 또한 속성은 요일에 대 한 글꼴 색을 결정 합니다. <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 속성 앞에 표시 된 달 또는 월을 수행 하는 날짜의 색을 결정 합니다.  
  
    ```vb  
    MonthCalendar1.TitleBackColor = System.Drawing.Color.Blue  
    MonthCalendar1.TrailingForeColor = System.Drawing.Color.Red  
    MonthCalendar1.TitleForeColor = System.Drawing.Color.Yellow  
    ```  
  
    ```csharp  
    monthCalendar1.TitleBackColor = System.Drawing.Color.Blue;  
    monthCalendar1.TrailingForeColor = System.Drawing.Color.Red;  
    monthCalendar1.TitleForeColor = System.Drawing.Color.Yellow;  
    ```  
  
    ```cpp  
    monthCalendar1->TitleBackColor = System::Drawing::Color::Blue;  
    monthCalendar1->TrailingForeColor = System::Drawing::Color::Red;  
    monthCalendar1->TitleForeColor = System::Drawing::Color::Yellow;  
    ```  
  
    > [!NOTE]
    >  Windows Vista와 테마에 따라부터 몇 가지 속성만 설정 변경할 수 없습니다 모양의 달력. 예를 들어 Windows Aero 테마를 사용 하도록 설정 되어를 설정 합니다 <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, 또는 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 속성에 영향을 주지 않습니다. 즉, 런타임에 현재 운영 체제 테마에서 파생 되는 모양을 사용 하 여 달력의 업데이트 된 렌더링 됩니다. 이러한 속성을 사용 하 고 달력의 이전 버전을 사용 하려는 경우에 응용 프로그램에 대 한 비주얼 스타일을 비활성화할 수 있습니다. 비주얼 스타일을 사용 하지 않도록 설정 하면 응용 프로그램에서 다른 컨트롤의 동작과 모양을 달라질 수 있습니다. Visual Basic에서 비주얼 스타일을 사용 하지 않으려면 프로젝트 디자이너를 열고 선택 취소 합니다 **XP 비주얼 스타일 사용** 확인란 합니다. C#에서 비주얼 스타일을 사용 하지 않으려면 Program.cs를 열고 주석 `Application.EnableVisualStyles();`합니다. 비주얼 스타일에 대 한 자세한 내용은 참조 하세요. [비주얼 스타일이 활성화](/windows/desktop/controls/cookbook-overview)합니다.  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>컨트롤의 맨 아래에 현재 날짜를 표시 하려면  
  
-   <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> 속성을 `true`으로 설정합니다. 아래 예제에서는 표시 하 고 폼을 두 번 클릭으로 오늘 날짜를 생략 하면 간에 전환 합니다.  
  
    ```vb  
    Private Sub Form1_DoubleClick(ByVal sender As Object, _  
    ByVal e As System.EventArgs) Handles MyBase.DoubleClick  
       ' Toggle between True and False.  
       MonthCalendar1.ShowToday = Not MonthCalendar1.ShowToday  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_DoubleClick(object sender, System.EventArgs e)  
    {  
       // Toggle between True and False.  
       monthCalendar1.ShowToday = !monthCalendar1.ShowToday;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void Form1_DoubleClick(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // Toggle between True and False.  
          monthCalendar1->ShowToday = !monthCalendar1->ShowToday;  
       }  
    ```  
  
     (Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>주 번호를 표시 하려면  
  
-   <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> 속성을 `true`으로 설정합니다. 코드 또는 속성 창에서이 속성을 설정할 수 있습니다.  
  
     주 번호 첫 번째 요일의 왼쪽에 별도 열에 표시 됩니다.  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a>참고자료
- [MonthCalendar 컨트롤](monthcalendar-control-windows-forms.md)
- [방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [방법: Forms MonthCalendar 컨트롤의 Windows를 사용 하 여 특정 날짜를 굵게 표시](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시](display-more-than-one-month-wf-monthcalendar-control.md)
