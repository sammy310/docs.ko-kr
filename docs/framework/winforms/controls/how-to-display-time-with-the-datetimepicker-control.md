---
title: '방법: DateTimePicker 컨트롤을 사용하여 시간 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: 5163ca3eb04732152960c86c9a7428d87c6280f9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083039"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="bece7-102">방법: DateTimePicker 컨트롤을 사용하여 시간 표시</span><span class="sxs-lookup"><span data-stu-id="bece7-102">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="bece7-103">응용 프로그램에서 사용자가 날짜와 시간을 선택하고 해당 날짜와 시간을 지정된 형식으로 표시할 수 있게 하려면 <xref:System.Windows.Forms.DateTimePicker> 컨트롤을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bece7-103">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="bece7-104">다음 절차에서는 <xref:System.Windows.Forms.DateTimePicker> 컨트롤을 사용하여 시간을 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bece7-104">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="bece7-105">DateTimePicker 컨트롤을 사용하여 시간을 표시하려면</span><span class="sxs-lookup"><span data-stu-id="bece7-105">To display the time with the DateTimePicker control</span></span>  
  
1.  <span data-ttu-id="bece7-106">설정 된 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="bece7-106">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to</span></span> <xref:System.Windows.Forms.DateTimePickerFormat.Time>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2.  <span data-ttu-id="bece7-107"><xref:System.Windows.Forms.DateTimePicker>에 대한 <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bece7-107">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="bece7-108">예제</span><span class="sxs-lookup"><span data-stu-id="bece7-108">Example</span></span>  
 <span data-ttu-id="bece7-109">다음 코드 샘플은 사용자가 시간만 선택할 수 있도록 하는 <xref:System.Windows.Forms.DateTimePicker>를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bece7-109">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bece7-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="bece7-110">Compiling the Code</span></span>  
 <span data-ttu-id="bece7-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bece7-111">This example requires:</span></span>  
  
-   <span data-ttu-id="bece7-112">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="bece7-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="bece7-113">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bece7-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="bece7-114">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bece7-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bece7-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="bece7-115">See also</span></span>

- [<span data-ttu-id="bece7-116">DateTimePicker 컨트롤</span><span class="sxs-lookup"><span data-stu-id="bece7-116">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
