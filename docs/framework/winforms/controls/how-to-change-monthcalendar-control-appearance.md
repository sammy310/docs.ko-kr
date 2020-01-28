---
title: MonthCalendar 컨트롤의 모양 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: ded9059ede4ad03f637c0e697b880c41a9a8ba32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746647"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a><span data-ttu-id="7cae6-102">방법: Windows Forms MonthCalendar 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="7cae6-102">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>
<span data-ttu-id="7cae6-103">Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤을 사용 하면 여러 가지 방법으로 달력의 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="7cae6-104">예를 들어 색 구성표를 설정 하 고 주 번호와 현재 날짜를 표시 하거나 숨기도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="7cae6-105">월 달력의 색 구성표를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="7cae6-105">To change the month calendar's color scheme</span></span>  
  
- <span data-ttu-id="7cae6-106"><xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> 및 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>와 같은 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="7cae6-107">또한 <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> 속성은 요일에 대 한 글꼴 색을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="7cae6-108"><xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 속성은 표시 된 월 또는 월 앞과 뒤의 날짜 색을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
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
    > <span data-ttu-id="7cae6-109">Windows Vista부터 테마에 따라 일부 속성을 설정 하면 일정의 모양이 변경 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="7cae6-110">예를 들어 Windows가 Aero 테마를 사용 하도록 설정 된 경우 <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>또는 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 속성을 설정 해도 아무 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="7cae6-111">즉, 런타임에 현재 운영 체제 테마에서 파생 되는 모양을 사용 하 여 달력의 업데이트 된 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="7cae6-112">이러한 속성을 사용 하 고 이전 버전의 달력을 사용 하려면 응용 프로그램에 대 한 비주얼 스타일을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="7cae6-113">비주얼 스타일을 사용 하지 않도록 설정 하면 애플리케이션에서 다른 컨트롤의 동작과 모양을 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="7cae6-114">Visual Basic에서 비주얼 스타일을 사용 하지 않으려면 프로젝트 디자이너를 열고 선택 취소 합니다 **XP 비주얼 스타일 사용** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="7cae6-115">C#에서 비주얼 스타일을 사용 하지 않으려면 Program.cs를 열고 주석 `Application.EnableVisualStyles();`합니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="7cae6-116">비주얼 스타일에 대 한 자세한 내용은 [비주얼 스타일 사용](/windows/desktop/controls/cookbook-overview)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cae6-116">For more information about visual styles, see [Enabling Visual Styles](/windows/desktop/controls/cookbook-overview).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="7cae6-117">컨트롤의 맨 아래에 있는 현재 날짜를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="7cae6-117">To display the current date at the bottom of the control</span></span>  
  
- <span data-ttu-id="7cae6-118"><xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="7cae6-119">아래 예제에서는 폼을 두 번 클릭 했을 때 오늘 날짜를 표시 하거나 생략할 때를 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
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
  
     <span data-ttu-id="7cae6-120">(시각적 C#개체, C++시각적 개체) 폼의 생성자에 다음 코드를 추가 하 여 이벤트 처리기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="7cae6-121">주 번호를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="7cae6-121">To display week numbers</span></span>  
  
- <span data-ttu-id="7cae6-122"><xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="7cae6-123">코드 또는 속성 창에서이 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="7cae6-124">주 번호는 첫 번째 요일의 왼쪽에 있는 별도의 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cae6-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7cae6-125">참조</span><span class="sxs-lookup"><span data-stu-id="7cae6-125">See also</span></span>

- [<span data-ttu-id="7cae6-126">MonthCalendar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7cae6-126">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="7cae6-127">방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택</span><span class="sxs-lookup"><span data-stu-id="7cae6-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="7cae6-128">방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시</span><span class="sxs-lookup"><span data-stu-id="7cae6-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="7cae6-129">방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시</span><span class="sxs-lookup"><span data-stu-id="7cae6-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
