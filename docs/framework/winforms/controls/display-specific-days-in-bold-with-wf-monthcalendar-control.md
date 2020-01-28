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
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="d013c-102">방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시</span><span class="sxs-lookup"><span data-stu-id="d013c-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="d013c-103">Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤은 날짜를 단수형 또는 반복 단위로 굵게 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="d013c-104">이 작업을 수행 하 여 휴일, 주말 등의 특수 날짜를 강조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="d013c-105">이 기능을 제어 하는 세 가지 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-105">Three properties control this feature.</span></span> <span data-ttu-id="d013c-106"><xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> 속성은 단일 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="d013c-107"><xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> 속성은 매년 굵게 표시 되는 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="d013c-108"><xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> 속성은 매월 굵게 표시 되는 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="d013c-109">이러한 각 속성은 <xref:System.DateTime> 개체의 배열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="d013c-110">이러한 목록 중 하나에서 날짜를 추가 하거나 제거 하려면 <xref:System.DateTime> 개체를 추가 하거나 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="d013c-111">날짜를 굵게 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="d013c-111">To make a date appear in bold type</span></span>  
  
1. <span data-ttu-id="d013c-112"><xref:System.DateTime> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-112">Create the <xref:System.DateTime> objects.</span></span>  
  
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
  
2. <span data-ttu-id="d013c-113"><xref:System.Windows.Forms.MonthCalendar> 컨트롤의 <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>또는 <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> 메서드를 호출 하 여 한 날짜를 굵게 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
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
  
     <span data-ttu-id="d013c-114">– 또는 –</span><span class="sxs-lookup"><span data-stu-id="d013c-114">–or–</span></span>  
  
     <span data-ttu-id="d013c-115"><xref:System.DateTime> 개체의 배열을 만들고이를 속성 중 하나에 할당 하 여 날짜 집합을 한 번에 모두 굵게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
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
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="d013c-116">날짜가 일반 글꼴로 표시 되도록 하려면</span><span class="sxs-lookup"><span data-stu-id="d013c-116">To make a date appear in the regular font</span></span>  
  
1. <span data-ttu-id="d013c-117"><xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>또는 <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> 메서드를 호출 하 여 굵게 표시 된 단일 날짜를 일반 글꼴로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
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
  
     <span data-ttu-id="d013c-118">– 또는 –</span><span class="sxs-lookup"><span data-stu-id="d013c-118">–or–</span></span>  
  
     <span data-ttu-id="d013c-119"><xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>또는 <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> 메서드를 호출 하 여 세 목록 중 하나에서 굵게 표시 된 날짜를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. <span data-ttu-id="d013c-120"><xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> 메서드를 호출 하 여 글꼴의 모양을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d013c-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d013c-121">참조</span><span class="sxs-lookup"><span data-stu-id="d013c-121">See also</span></span>

- [<span data-ttu-id="d013c-122">MonthCalendar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d013c-122">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="d013c-123">방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택</span><span class="sxs-lookup"><span data-stu-id="d013c-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="d013c-124">방법: Windows Forms MonthCalendar 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="d013c-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="d013c-125">방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시</span><span class="sxs-lookup"><span data-stu-id="d013c-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
