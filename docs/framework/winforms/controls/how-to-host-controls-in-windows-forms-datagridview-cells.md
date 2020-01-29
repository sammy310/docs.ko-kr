---
title: DataGridView 셀의 호스트 컨트롤
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: a64521a15a272ca8140302f39d15e7f17e0c423b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736534"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="b8415-102">방법: Windows Forms DataGridView 셀에서 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="b8415-102">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="b8415-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 사용자가 다양한 방법으로 값을 입력하고 편집할 수 있도록 하는 여러 가지 열 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8415-103">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="b8415-104">그러나 이들 열 형식이 데이터 입력 요구 사항에 맞지 않으면 선택한 컨트롤을 호스트하는 셀을 사용하여 고유한 열 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8415-104">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="b8415-105">이 작업을 하려면 <xref:System.Windows.Forms.DataGridViewColumn> 및 <xref:System.Windows.Forms.DataGridViewCell>에서 파생된 클래스를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8415-105">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="b8415-106"><xref:System.Windows.Forms.Control>에서 파생되고 <xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스를 구현하는 클래스도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8415-106">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="b8415-107">다음 코드 예제에서는 달력 열을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8415-107">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="b8415-108">이 열의 셀에는 날짜가 일반 텍스트 상자 셀로 표시되지만 사용자가 셀을 편집할 때 <xref:System.Windows.Forms.DateTimePicker> 컨트롤이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8415-108">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="b8415-109">텍스트 상자 표시 기능을 다시 구현하지 않아도 되도록, <xref:System.Windows.Forms.DataGridViewCell> 클래스를 직접 상속하는 것이 아니라 `CalendarCell` 클래스가 <xref:System.Windows.Forms.DataGridViewTextBoxCell> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8415-109">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8415-110"><xref:System.Windows.Forms.DataGridViewCell> 또는 <xref:System.Windows.Forms.DataGridViewColumn>에서 파생시키고 파생 클래스에 새 속성을 추가하는 경우 복제 작업 중 새 속성을 복사하도록 `Clone` 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8415-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="b8415-111">또한 기본 클래스의 속성이 새로운 셀 또는 열에 복사되도록 기본 클래스의 `Clone` 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8415-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8415-112">예</span><span class="sxs-lookup"><span data-stu-id="b8415-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b8415-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b8415-113">Compiling the Code</span></span>  
 <span data-ttu-id="b8415-114">다음 예제에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b8415-114">The following example requires:</span></span>  
  
- <span data-ttu-id="b8415-115">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="b8415-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8415-116">참조</span><span class="sxs-lookup"><span data-stu-id="b8415-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [<span data-ttu-id="b8415-117">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b8415-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b8415-118">DataGridView 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="b8415-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="b8415-119">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="b8415-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
