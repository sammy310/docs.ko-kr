---
title: '연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: 99561490786f3f3569f272138001ea5ad8937410
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792264"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="79b4c-102">연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="79b4c-102">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="79b4c-103">데이터베이스에서 발생 하지 않는 테이블 형식 데이터를 표시 하려면 자주 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-103">You may frequently want to display tabular data that does not originate from a database.</span></span> <span data-ttu-id="79b4c-104">예를 들어 다음 문자열의 2 차원 배열의 내용을 표시 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-104">For example, you may want to show the contents of a two-dimensional array of strings.</span></span> <span data-ttu-id="79b4c-105"><xref:System.Windows.Forms.DataGridView> 클래스는 데이터 원본에 바인딩하지 않고 데이터를 표시 하는 쉽고 고도로 사용자 지정 가능한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-105">The <xref:System.Windows.Forms.DataGridView> class provides an easy and highly customizable way to display data without binding to a data source.</span></span> <span data-ttu-id="79b4c-106">이 연습을 채우는 방법을 보여는 <xref:System.Windows.Forms.DataGridView> 제어 하 고 추가 및 삭제 "바인딩되지 않은" 모드의 행을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-106">This walkthrough shows how to populate a <xref:System.Windows.Forms.DataGridView> control and manage the addition and deletion of rows in "unbound" mode.</span></span> <span data-ttu-id="79b4c-107">기본적으로 사용자는 새 행을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-107">By default, the user can add new rows.</span></span> <span data-ttu-id="79b4c-108">행 추가 방지 하려면 설정 합니다 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-108">To prevent row addition, set the <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="79b4c-109">이 항목의 코드를 단일 목록으로 복사하려면 [방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](how-to-create-an-unbound-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-109">To copy the code in this topic as a single listing, see [How to: Create an Unbound Windows Forms DataGridView Control](how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="79b4c-110">폼 만들기</span><span class="sxs-lookup"><span data-stu-id="79b4c-110">Creating the Form</span></span>  
  
#### <a name="to-use-an-unbound-datagridview-control"></a><span data-ttu-id="79b4c-111">바인딩되지 않은 DataGridView 컨트롤을 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="79b4c-111">To use an unbound DataGridView control</span></span>  
  
1. <span data-ttu-id="79b4c-112">파생 되는 클래스를 만듭니다 <xref:System.Windows.Forms.Form> 하 고 다음 변수 선언을 포함 하 고 `Main` 메서드.</span><span class="sxs-lookup"><span data-stu-id="79b4c-112">Create a class that derives from <xref:System.Windows.Forms.Form> and contains the following variable declarations and `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. <span data-ttu-id="79b4c-113">구현 된 `SetupLayout` 폼의 레이아웃을 설정 하려면 폼의 클래스 정의에 메서드.</span><span class="sxs-lookup"><span data-stu-id="79b4c-113">Implement a `SetupLayout` method in your form's class definition to set up the form's layout.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. <span data-ttu-id="79b4c-114">만들기를 `SetupDataGridView` 메서드를 설정 하는 <xref:System.Windows.Forms.DataGridView> 열과 속성.</span><span class="sxs-lookup"><span data-stu-id="79b4c-114">Create a `SetupDataGridView` method to set up the <xref:System.Windows.Forms.DataGridView> columns and properties.</span></span>  
  
     <span data-ttu-id="79b4c-115">이 메서드는 먼저 추가 합니다 <xref:System.Windows.Forms.DataGridView> 컨트롤을 폼의 <xref:System.Windows.Forms.Control.Controls%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-115">This method first adds the <xref:System.Windows.Forms.DataGridView> control to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span> <span data-ttu-id="79b4c-116">그런 다음 표시할 열의 수를 사용 하 여 설정 됩니다는 <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-116">Next, the number of columns to be displayed is set using the <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> property.</span></span> <span data-ttu-id="79b4c-117">열 머리글에 대 한 기본 스타일을 설정 하 여 설정 됩니다는 <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, 및 <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> 의 속성을 <xref:System.Windows.Forms.DataGridViewCellStyle> 반환한는 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-117">The default style for the column headers is set by setting the <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, and <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> returned by the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> property.</span></span>  
  
     <span data-ttu-id="79b4c-118">레이아웃 및 모양 속성을 설정 하 고 열 이름이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-118">Layout and appearance properties are set, and then the column names are assigned.</span></span> <span data-ttu-id="79b4c-119">이 메서드가 종료 되는 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤은을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-119">When this method exits, the <xref:System.Windows.Forms.DataGridView> control is ready to be populated.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. <span data-ttu-id="79b4c-120">만들기는 `PopulateDataGridView` 에 행을 추가 하는 방법의 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-120">Create a `PopulateDataGridView` method to add rows to the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="79b4c-121">각 행 노래 및 관련된 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-121">Each row represents a song and its associated information.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. <span data-ttu-id="79b4c-122">현재 위치에서 유틸리티 메서드를 사용 하 여 이벤트 처리기를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-122">With the utility methods in place, you can attach event handlers.</span></span>  
  
     <span data-ttu-id="79b4c-123">처리 하는 합니다 **추가** 및 **삭제** 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트, 양식의 <xref:System.Windows.Forms.Form.Load> 이벤트 및 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-123">You will handle the **Add** and **Delete** buttons' <xref:System.Windows.Forms.Control.Click> events, the form's <xref:System.Windows.Forms.Form.Load> event, and the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
     <span data-ttu-id="79b4c-124">경우는 **추가** 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생 하면 새로 만든 빈 행에 추가 됩니다는 <xref:System.Windows.Forms.DataGridView>합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-124">When the **Add** button's <xref:System.Windows.Forms.Control.Click> event is raised, a new, empty row is added to the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="79b4c-125">경우는 **삭제** 단추의 <xref:System.Windows.Forms.Control.Click> 선택한 행을 삭제 하면, 사용자는 새 레코드에 대 한 행은 새 행을 추가 하지 않은 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-125">When the **Delete** button's <xref:System.Windows.Forms.Control.Click> event is raised, the selected row is deleted, unless it is the row for new records, which enables the user add new rows.</span></span> <span data-ttu-id="79b4c-126">이 행의 마지막 행은 항상를 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-126">This row is always the last row in the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="79b4c-127">경우 양식의 <xref:System.Windows.Forms.Form.Load> 이벤트가 발생 합니다 `SetupLayout`, `SetupDataGridView`, 및 `PopulateDataGridView` 유틸리티 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-127">When the form's <xref:System.Windows.Forms.Form.Load> event is raised, the `SetupLayout`, `SetupDataGridView`, and `PopulateDataGridView` utility methods are called.</span></span>  
  
     <span data-ttu-id="79b4c-128">경우는 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트가 발생의 각 셀을 `Date` 열 형식은 long date 셀의 값을 구문 분석할 수 없는 경우가 아니면 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-128">When the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is raised, each cell in the `Date` column is formatted as a long date, unless the cell's value cannot be parsed.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="79b4c-129">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="79b4c-129">Testing the Application</span></span>  
 <span data-ttu-id="79b4c-130">이제 예상 대로 작동 되도록 폼을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-130">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="79b4c-131">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="79b4c-131">To test the form</span></span>  
  
- <span data-ttu-id="79b4c-132">F5 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-132">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="79b4c-133">표시 됩니다는 <xref:System.Windows.Forms.DataGridView> 에 나열 된 노래를 표시 하는 컨트롤 `PopulateDataGridView`합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-133">You will see a <xref:System.Windows.Forms.DataGridView> control that displays the songs listed in `PopulateDataGridView`.</span></span> <span data-ttu-id="79b4c-134">포함 된 새 행을 추가할 수 있습니다 합니다 **행 추가** 단추를 사용 하 여 선택한 행을 삭제할 수는 **행 삭제** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-134">You can add new rows with the **Add Row** button, and you can delete selected rows with the **Delete Row** button.</span></span> <span data-ttu-id="79b4c-135">바인딩되지 않은 <xref:System.Windows.Forms.DataGridView> 컨트롤은 데이터 저장소 및 데이터에 같은 외부 소스에 관계 없이 <xref:System.Data.DataSet> 또는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-135">The unbound <xref:System.Windows.Forms.DataGridView> control is the data store, and its data is independent of any external source, such as a <xref:System.Data.DataSet> or an array.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="79b4c-136">다음 단계</span><span class="sxs-lookup"><span data-stu-id="79b4c-136">Next Steps</span></span>  
 <span data-ttu-id="79b4c-137">이 응용 프로그램의 기본적인 이해를 제공 합니다 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-137">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="79b4c-138">동작과 모양을 사용자 지정할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 여러 가지 방법으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-138">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
- <span data-ttu-id="79b4c-139">헤더 및 테두리 스타일을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-139">Change border and header styles.</span></span> <span data-ttu-id="79b4c-140">자세한 내용은 [방법: 변경 된 테두리 및 모눈선 스타일에는 Windows Forms DataGridView 컨트롤](change-the-border-and-gridline-styles-in-the-datagrid.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-140">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="79b4c-141">사용 하도록 설정 하거나 사용자 입력을 제한 합니다 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-141">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="79b4c-142">자세한 내용은 [방법: 행 추가 방지 하 고 삭제는 Windows Forms DataGridView 컨트롤](prevent-row-addition-and-deletion-datagridview.md), 및 [방법: 에서 열을 설정 읽기 전용으로 Windows Forms DataGridView 컨트롤](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-142">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="79b4c-143">데이터베이스 관련 오류에 대 한 사용자 입력을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-143">Check user input for database-related errors.</span></span> <span data-ttu-id="79b4c-144">자세한 내용은 [연습: Forms DataGridView 컨트롤의 Windows에서 데이터 입력 중에 발생 하는 오류 처리](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-144">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="79b4c-145">가상 모드를 사용 하 여 매우 큰 데이터 집합을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-145">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="79b4c-146">자세한 내용은 [연습: Forms DataGridView 컨트롤의 Windows에서 가상 모드 구현](implementing-virtual-mode-wf-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-146">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="79b4c-147">셀의 모양을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-147">Customize the appearance of cells.</span></span> <span data-ttu-id="79b4c-148">자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](customize-the-appearance-of-cells-in-the-datagrid.md) 고 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79b4c-148">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b4c-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="79b4c-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="79b4c-150">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="79b4c-150">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="79b4c-151">방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="79b4c-151">How to: Create an Unbound Windows Forms DataGridView Control</span></span>](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="79b4c-152">Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드</span><span class="sxs-lookup"><span data-stu-id="79b4c-152">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
