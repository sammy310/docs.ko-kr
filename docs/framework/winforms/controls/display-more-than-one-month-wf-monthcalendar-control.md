---
title: '방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시'
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
ms.openlocfilehash: 79100b52d8e0a5b651edb9d6555a4497287ed858
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209556"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="11c78-102">방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시</span><span class="sxs-lookup"><span data-stu-id="11c78-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="11c78-103">Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤 한 번에 최대 12 개월을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11c78-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="11c78-104">기본적으로 컨트롤은 한 달만 표시 되지만 몇 달이 표시 되 고 컨트롤 내에서 정렬 되는 방식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11c78-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="11c78-105">컨트롤의 크기 조정 달력의 크기를 변경한 경우, 하므로 새 차원에 대 한 폼에 공간이 충분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11c78-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="11c78-106">여러 달 표시</span><span class="sxs-lookup"><span data-stu-id="11c78-106">To display multiple months</span></span>  
  
-   <span data-ttu-id="11c78-107">설정 된 <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> 속성 가로 및 세로로 표시할 월의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="11c78-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="11c78-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="11c78-108">See also</span></span>

- [<span data-ttu-id="11c78-109">MonthCalendar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="11c78-109">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="11c78-110">방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택</span><span class="sxs-lookup"><span data-stu-id="11c78-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="11c78-111">방법: Windows Forms MonthCalendar 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="11c78-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
