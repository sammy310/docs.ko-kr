---
title: DataGridView 컨트롤에 편집 모드 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743770"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="bb09a-102">방법: Windows Forms DataGridView 컨트롤에 편집 모드 지정</span><span class="sxs-lookup"><span data-stu-id="bb09a-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="bb09a-103">기본적으로 사용자는 입력 하거나 F2 키를 눌러 현재 <xref:System.Windows.Forms.DataGridView> 텍스트 상자 셀의 내용을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb09a-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="bb09a-104">이렇게 하면 다음 조건이 모두 충족 될 경우 셀이 편집 모드로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb09a-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
- <span data-ttu-id="bb09a-105">기본 데이터 소스에서 편집을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb09a-105">The underlying data source supports editing.</span></span>  
  
- <span data-ttu-id="bb09a-106"><xref:System.Windows.Forms.DataGridView> 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb09a-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
- <span data-ttu-id="bb09a-107"><xref:System.Windows.Forms.DataGridView.EditMode%2A> 속성 값이 <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>가 아닌 경우</span><span class="sxs-lookup"><span data-stu-id="bb09a-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
- <span data-ttu-id="bb09a-108">셀, 행, 열 및 컨트롤의 `ReadOnly` 속성은 모두 `false`로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb09a-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="bb09a-109">편집 모드에서 사용자는 셀 값을 변경 하 고 ENTER 키를 눌러 변경 내용을 커밋하거나 ESC 키를 눌러 셀을 원래 값으로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb09a-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="bb09a-110">현재 셀이 되는 즉시 셀이 편집 모드로 전환 되도록 <xref:System.Windows.Forms.DataGridView> 컨트롤을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb09a-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="bb09a-111">이 경우에는 ENTER 키와 ESC 키의 동작이 변경 되지 않지만 값이 커밋되거나 되돌아간 후에는 셀이 편집 모드로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb09a-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="bb09a-112">사용자가 셀을 입력 하거나 F2 키를 누를 때만 셀이 편집 모드로 전환 되도록 컨트롤을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb09a-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="bb09a-113">마지막으로 <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> 메서드를 호출 하는 경우를 제외 하 고 셀이 편집 모드로 전환 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb09a-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="bb09a-114">DataGridView 컨트롤의 편집 모드를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="bb09a-114">To change the edit mode of a DataGridView control</span></span>  
  
- <span data-ttu-id="bb09a-115"><xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> 속성을 적절 한 <xref:System.Windows.Forms.DataGridViewEditMode> 열거형으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb09a-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bb09a-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="bb09a-116">Compiling the Code</span></span>  
 <span data-ttu-id="bb09a-117">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bb09a-117">This example requires:</span></span>  
  
- <span data-ttu-id="bb09a-118"><xref:System.Windows.Forms.DataGridView>이라는 `dataGridView1` 컨트롤</span><span class="sxs-lookup"><span data-stu-id="bb09a-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="bb09a-119"><xref:System> 및 <xref:System.Windows.Forms> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="bb09a-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb09a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb09a-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bb09a-121">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="bb09a-121">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
