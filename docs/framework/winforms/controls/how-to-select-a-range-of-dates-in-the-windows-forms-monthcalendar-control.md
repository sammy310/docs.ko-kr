---
title: '방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], selecting range in calendar controls
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], selecting date range
- MonthCalendar control [Windows Forms], selecting date range
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
ms.openlocfilehash: 21cda9fb11edd3f6148d7128621fbde8d3ff913c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723818"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="83fef-102">방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택</span><span class="sxs-lookup"><span data-stu-id="83fef-102">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="83fef-103">Windows Forms의 중요 한 기능은 <xref:System.Windows.Forms.MonthCalendar> 컨트롤은 사용자가 날짜 범위를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83fef-103">An important feature of the Windows Forms <xref:System.Windows.Forms.MonthCalendar> control is that the user can select a range of dates.</span></span> <span data-ttu-id="83fef-104">이 기능은의 날짜 선택 기능 개선 된는 <xref:System.Windows.Forms.DateTimePicker> 만 사용자가 단일 날짜/시간 값을 선택할 수 있도록 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="83fef-104">This feature is an improvement over the date-selection feature of the <xref:System.Windows.Forms.DateTimePicker> control, which only enables the user to select a single date/time value.</span></span> <span data-ttu-id="83fef-105">날짜 범위를 설정 하거나 속성을 사용 하 여 사용자가 설정한 선택 범위를 가져올 수는 <xref:System.Windows.Forms.MonthCalendar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fef-105">You can set a range of dates or get a selection range set by the user by using properties of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span> <span data-ttu-id="83fef-106">다음 코드 예제에서는 선택 범위를 설정 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fef-106">The following code example demonstrates how to set a selection range.</span></span>  
  
### <a name="to-select-a-range-of-dates"></a><span data-ttu-id="83fef-107">날짜 범위 선택</span><span class="sxs-lookup"><span data-stu-id="83fef-107">To select a range of dates</span></span>  
  
1.  <span data-ttu-id="83fef-108">만들 <xref:System.DateTime> 범위에서 첫 번째 및 마지막 날짜를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="83fef-108">Create <xref:System.DateTime> objects that represent the first and last dates in a range.</span></span>  
  
    ```vb  
    Dim projectStart As Date = New DateTime(2001, 2, 13)  
    Dim projectEnd As Date = New DateTime(2001, 2, 28)  
    ```  
  
    ```csharp  
    DateTime projectStart = new DateTime(2001, 2, 13);  
    DateTime projectEnd = new DateTime(2001, 2, 28);  
    ```  
  
    ```cpp  
    DateTime projectStart = DateTime(2001, 2, 13);  
    DateTime projectEnd = DateTime(2001, 2, 28);  
    ```  
  
2.  <span data-ttu-id="83fef-109"><xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="83fef-109">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> property.</span></span>  
  
    ```vb  
    MonthCalendar1.SelectionRange = New SelectionRange(projectStart, projectEnd)  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionRange = new SelectionRange(projectStart, projectEnd);  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionRange = gcnew  
       SelectionRange(projectStart, projectEnd);  
    ```  
  
     <span data-ttu-id="83fef-110">– 또는 –</span><span class="sxs-lookup"><span data-stu-id="83fef-110">–or–</span></span>  
  
     <span data-ttu-id="83fef-111"><xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> 및 <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="83fef-111">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> and <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> properties.</span></span>  
  
    ```vb  
    MonthCalendar1.SelectionStart = projectStart  
    MonthCalendar1.SelectionEnd = projectEnd  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionStart = projectStart;  
    monthCalendar1.SelectionEnd = projectEnd;  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionStart = projectStart;  
    monthCalendar1->SelectionEnd = projectEnd;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="83fef-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="83fef-112">See also</span></span>
- [<span data-ttu-id="83fef-113">MonthCalendar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="83fef-113">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="83fef-114">방법: Windows Forms MonthCalendar 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="83fef-114">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="83fef-115">방법: Forms MonthCalendar 컨트롤의 Windows를 사용 하 여 특정 날짜를 굵게 표시</span><span class="sxs-lookup"><span data-stu-id="83fef-115">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="83fef-116">방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시</span><span class="sxs-lookup"><span data-stu-id="83fef-116">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
