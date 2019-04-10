---
title: '방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시'
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
ms.openlocfilehash: 08d5a505229cd434dbf82e8ae4624bb418efd379
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335942"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="2a24b-102">방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시</span><span class="sxs-lookup"><span data-stu-id="2a24b-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="2a24b-103">Windows Forms <xref:System.Windows.Forms.DateTimePicker> 컨트롤의 컨트롤에서 날짜와 시간 표시를 서식 지정에 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a24b-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="2a24b-104">합니다 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성에 나열 된 미리 정의 된 형식에서 선택할 수는 <xref:System.Windows.Forms.DateTimePickerFormat>합니다.</span><span class="sxs-lookup"><span data-stu-id="2a24b-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="2a24b-105">이러한 용도 맞게 적절 한 인 경우에 나열 된 형식 문자를 사용 하 여 사용자 고유의 형식 스타일을 만들 수 있습니다 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="2a24b-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="2a24b-106">사용자 지정 형식을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="2a24b-106">To display a custom format</span></span>  
  
1. <span data-ttu-id="2a24b-107"><xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성을 `DateTimePickerFormat.Custom`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a24b-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2. <span data-ttu-id="2a24b-108">설정 된 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> 는 형식 문자열 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2a24b-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="2a24b-109">서식이 지정 된 값으로 텍스트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="2a24b-109">To add text to the formatted value</span></span>  
  
1. <span data-ttu-id="2a24b-110">작은따옴표를 사용 하 여 "M"와 같은 문자 형식 또는 같은 구분 되지 않는 모든 문자를 묶습니다 ":".</span><span class="sxs-lookup"><span data-stu-id="2a24b-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="2a24b-111">아래의 형식 문자열은 형식으로 현재 날짜를 표시 하는 예를 들어, "임: 05시 30분: 31 년 3 월 금요일 02, 2012"영어 (미국) 문화권의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a24b-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
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
  
     <span data-ttu-id="2a24b-112">문화권 설정에 따라 단일 따옴표로 묶이지 않은 문자를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a24b-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="2a24b-113">위의 형식 문자열은 형식으로 현재 날짜를 표시 하는 예를 들어, "임: 05시 30분: 31 년 3 월 금요일 02, 2012"영어 (미국) 문화권의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a24b-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="2a24b-114">참고 "ss" 이므로 구분 문자가 되도록 것이 아니므로 첫 번째 콜론을 하나의 따옴표로 묶입니다.</span><span class="sxs-lookup"><span data-stu-id="2a24b-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="2a24b-115">다른 문화권의 형식으로 나타날 수 있습니다 "임: 05.30.31 금요일 년 3 월 02 2012"입니다.</span><span class="sxs-lookup"><span data-stu-id="2a24b-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a24b-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="2a24b-116">See also</span></span>

- [<span data-ttu-id="2a24b-117">DateTimePicker 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2a24b-117">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="2a24b-118">방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환</span><span class="sxs-lookup"><span data-stu-id="2a24b-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
