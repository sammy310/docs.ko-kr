---
title: DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기
description: 해당 속성을 사용 하 여 DataGridView 컨트롤에서 선택한 셀, 행 또는 열을 가져오는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 32ddae34104d23b8e5fbc0cce7da79f33fcce1d2
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904171"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="cb1c3-103">방법: Windows Forms DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기</span><span class="sxs-lookup"><span data-stu-id="cb1c3-103">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cb1c3-104">해당 하는 <xref:System.Windows.Forms.DataGridView> 속성인 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> , 및를 사용 하 여 컨트롤에서 선택한 셀, 행 또는 열을 가져올 수 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb1c3-104">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="cb1c3-105">다음 절차에서는 선택한 셀을 가져오고 행 및 열 인덱스를에 표시 <xref:System.Windows.Forms.MessageBox> 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1c3-105">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="cb1c3-106">DataGridView 컨트롤에서 선택한 셀을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="cb1c3-106">To get the selected cells in a DataGridView control</span></span>  
  
- <span data-ttu-id="cb1c3-107"><xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1c3-107">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="cb1c3-108">잠재적으로 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 많은 수의 셀이 표시 되지 않도록 하려면 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1c3-108">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="cb1c3-109">DataGridView 컨트롤에서 선택 된 행을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="cb1c3-109">To get the selected rows in a DataGridView control</span></span>  
  
- <span data-ttu-id="cb1c3-110"><xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1c3-110">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="cb1c3-111">사용자가 행을 선택할 수 있도록 하려면 속성을 또는로 설정 해야 합니다 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> .</span><span class="sxs-lookup"><span data-stu-id="cb1c3-111">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="cb1c3-112">DataGridView 컨트롤에서 선택한 열을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="cb1c3-112">To get the selected columns in a DataGridView control</span></span>  
  
- <span data-ttu-id="cb1c3-113"><xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1c3-113">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="cb1c3-114">사용자가 열을 선택할 수 있도록 하려면 속성을 또는로 설정 해야 합니다 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> .</span><span class="sxs-lookup"><span data-stu-id="cb1c3-114">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cb1c3-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="cb1c3-115">Compiling the Code</span></span>  
 <span data-ttu-id="cb1c3-116">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1c3-116">This example requires:</span></span>  
  
- <span data-ttu-id="cb1c3-117"><xref:System.Windows.Forms.Button>`selectedCellsButton` `selectedRowsButton` `selectedColumnsButton` 각각 연결 된 이벤트에 대 한 처리기가 있는, 및 라는 컨트롤 <xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="cb1c3-117"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
- <span data-ttu-id="cb1c3-118">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cb1c3-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="cb1c3-119"><xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> 및 <xref:System.Text?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="cb1c3-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cb1c3-120">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="cb1c3-120">Robust Programming</span></span>  
 <span data-ttu-id="cb1c3-121">이 항목에 설명 된 컬렉션은 많은 셀, 행 또는 열이 선택 된 경우 효율적으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb1c3-121">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="cb1c3-122">많은 양의 데이터에 이러한 컬렉션을 사용 하는 방법에 대 한 자세한 내용은 [Windows Forms DataGridView 컨트롤 크기 조정에 대 한 모범 사례](best-practices-for-scaling-the-windows-forms-datagridview-control.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cb1c3-122">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb1c3-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb1c3-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="cb1c3-124">Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용</span><span class="sxs-lookup"><span data-stu-id="cb1c3-124">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
