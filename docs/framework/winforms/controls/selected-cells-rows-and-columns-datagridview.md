---
title: DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 0079c590ee6e4732523fd50be157bd58ec1bfb1b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743076"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="560d0-102">방법: Windows Forms DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기</span><span class="sxs-lookup"><span data-stu-id="560d0-102">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="560d0-103"><xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>및 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>해당 속성을 사용 하 여 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 선택한 셀, 행 또는 열을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560d0-103">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="560d0-104">다음 절차에서는 선택한 셀을 가져오고 해당 행 및 열 인덱스를 <xref:System.Windows.Forms.MessageBox>표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="560d0-104">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="560d0-105">DataGridView 컨트롤에서 선택한 셀을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="560d0-105">To get the selected cells in a DataGridView control</span></span>  
  
- <span data-ttu-id="560d0-106"><xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="560d0-106">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="560d0-107"><xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 메서드를 사용 하 여 잠재적으로 많은 수의 셀을 표시 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="560d0-107">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="560d0-108">DataGridView 컨트롤에서 선택 된 행을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="560d0-108">To get the selected rows in a DataGridView control</span></span>  
  
- <span data-ttu-id="560d0-109"><xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="560d0-109">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="560d0-110">사용자가 행을 선택할 수 있도록 하려면 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="560d0-110">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="560d0-111">DataGridView 컨트롤에서 선택한 열을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="560d0-111">To get the selected columns in a DataGridView control</span></span>  
  
- <span data-ttu-id="560d0-112"><xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="560d0-112">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="560d0-113">사용자가 열을 선택할 수 있도록 하려면 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="560d0-113">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="560d0-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="560d0-114">Compiling the Code</span></span>  
 <span data-ttu-id="560d0-115">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="560d0-115">This example requires:</span></span>  
  
- <span data-ttu-id="560d0-116">각각 연결 된 <xref:System.Windows.Forms.Control.Click> 이벤트에 대 한 처리기가 있는 `selectedCellsButton`, `selectedRowsButton`및 `selectedColumnsButton`이라는 컨트롤을 <xref:System.Windows.Forms.Button> 합니다.</span><span class="sxs-lookup"><span data-stu-id="560d0-116"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
- <span data-ttu-id="560d0-117">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="560d0-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="560d0-118"><xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> 및 <xref:System.Text?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="560d0-118">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="560d0-119">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="560d0-119">Robust Programming</span></span>  
 <span data-ttu-id="560d0-120">이 항목에 설명 된 컬렉션은 많은 셀, 행 또는 열이 선택 된 경우 효율적으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="560d0-120">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="560d0-121">많은 양의 데이터에 이러한 컬렉션을 사용 하는 방법에 대 한 자세한 내용은 [Windows Forms DataGridView 컨트롤 크기 조정에 대 한 모범 사례](best-practices-for-scaling-the-windows-forms-datagridview-control.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="560d0-121">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="560d0-122">참조</span><span class="sxs-lookup"><span data-stu-id="560d0-122">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="560d0-123">Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용</span><span class="sxs-lookup"><span data-stu-id="560d0-123">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
