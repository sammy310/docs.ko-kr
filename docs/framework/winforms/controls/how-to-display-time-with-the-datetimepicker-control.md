---
title: '방법: DateTimePicker 컨트롤을 사용하여 시간 표시'
description: Windows Forms DateTimePicker 컨트롤을 사용 하 여 사용자가 날짜 및 시간을 선택 하 고 해당 날짜와 시간을 지정 된 형식으로 표시할 수 있도록 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: ab584367a189d05e567bb57d386c6bf629201102
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325586"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="5e217-103">방법: DateTimePicker 컨트롤을 사용하여 시간 표시</span><span class="sxs-lookup"><span data-stu-id="5e217-103">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="5e217-104">애플리케이션에서 사용자가 날짜와 시간을 선택하고 해당 날짜와 시간을 지정된 형식으로 표시할 수 있게 하려면 <xref:System.Windows.Forms.DateTimePicker> 컨트롤을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e217-104">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="5e217-105">다음 절차에서는 <xref:System.Windows.Forms.DateTimePicker> 컨트롤을 사용하여 시간을 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e217-105">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="5e217-106">DateTimePicker 컨트롤을 사용하여 시간을 표시하려면</span><span class="sxs-lookup"><span data-stu-id="5e217-106">To display the time with the DateTimePicker control</span></span>  
  
1. <span data-ttu-id="5e217-107"><xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성을 <xref:System.Windows.Forms.DateTimePickerFormat.Time>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e217-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to <xref:System.Windows.Forms.DateTimePickerFormat.Time></span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="5e217-108"><xref:System.Windows.Forms.DateTimePicker>에 대한 <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e217-108">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="5e217-109">예제</span><span class="sxs-lookup"><span data-stu-id="5e217-109">Example</span></span>  
 <span data-ttu-id="5e217-110">다음 코드 샘플은 사용자가 시간만 선택할 수 있도록 하는 <xref:System.Windows.Forms.DateTimePicker>를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e217-110">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5e217-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5e217-111">Compiling the Code</span></span>  
 <span data-ttu-id="5e217-112">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5e217-112">This example requires:</span></span>  
  
- <span data-ttu-id="5e217-113">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="5e217-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e217-114">참조</span><span class="sxs-lookup"><span data-stu-id="5e217-114">See also</span></span>

- [<span data-ttu-id="5e217-115">DateTimePicker 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5e217-115">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
