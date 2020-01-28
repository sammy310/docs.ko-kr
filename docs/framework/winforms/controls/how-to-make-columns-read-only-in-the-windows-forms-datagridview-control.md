---
title: DataGridView 컨트롤에서 열을 읽기 전용으로 설정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: 11d008d47ec5edb594d3d862c68ff3b9920e0e25
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736191"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8dfe3-102">방법: Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정</span><span class="sxs-lookup"><span data-stu-id="8dfe3-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8dfe3-103">일부 데이터는 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-103">Not all data is meant for editing.</span></span> <span data-ttu-id="8dfe3-104"><xref:System.Windows.Forms.DataGridView> 컨트롤에서 열의 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 속성 값은 사용자가 해당 열의 셀을 편집할 수 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-104">In the <xref:System.Windows.Forms.DataGridView> control, the column <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property value determines whether users can edit cells in that column.</span></span> <span data-ttu-id="8dfe3-105">컨트롤을 완전히 읽기 전용으로 설정 하는 방법에 대 한 자세한 내용은 [방법: DataGridView 컨트롤 Windows Forms에서 행 추가 및 삭제 방지](prevent-row-addition-and-deletion-datagridview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md).</span></span>  
  
 <span data-ttu-id="8dfe3-106">Visual Studio에서는 이 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="8dfe3-107">또한 [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정을](make-columns-read-only-in-the-datagrid-using-the-designer.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-107">Also see [How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer](make-columns-read-only-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-make-a-column-read-only-programmatically"></a><span data-ttu-id="8dfe3-108">프로그래밍 방식으로 열을 읽기 전용으로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="8dfe3-108">To make a column read-only programmatically</span></span>  
  
- <span data-ttu-id="8dfe3-109"><xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-109">Set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8dfe3-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8dfe3-110">Compiling the Code</span></span>  
 <span data-ttu-id="8dfe3-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8dfe3-111">This example requires:</span></span>  
  
- <span data-ttu-id="8dfe3-112">이름이 `CompanyName`인 열을 포함하는 이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8dfe3-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a column named `CompanyName`.</span></span>  
  
- <span data-ttu-id="8dfe3-113"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="8dfe3-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dfe3-114">참조</span><span class="sxs-lookup"><span data-stu-id="8dfe3-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8dfe3-115">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="8dfe3-115">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="8dfe3-116">방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지</span><span class="sxs-lookup"><span data-stu-id="8dfe3-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)
