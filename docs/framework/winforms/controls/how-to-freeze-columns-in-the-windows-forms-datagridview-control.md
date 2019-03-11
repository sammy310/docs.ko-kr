---
title: '방법: Windows Forms DataGridView 컨트롤에서 열 고정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
ms.openlocfilehash: 640b6a9128758edfc22b5c9be971034c9e45fc70
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723870"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e24b1-102">방법: Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="e24b1-102">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e24b1-103">사용자가 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시된 데이터를 볼 때 단일 열이나 열 집합을 자주 참조해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e24b1-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="e24b1-104">예를 들어 많은 열이 포함된 고객 정보 테이블을 표시하는 경우 다른 열을 표시되는 영역 바깥으로 스크롤할 수 있게 하면서 고객 이름은 항상 표시하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e24b1-104">For example, when displaying a table of customer information that contains many columns, it is useful to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>  
  
 <span data-ttu-id="e24b1-105">이 동작을 얻기 위해 컨트롤에서 열을 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e24b1-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="e24b1-106">열을 고정하는 경우 왼쪽(또는 오른쪽에서 왼쪽 언어 스크립트의 경우 오른쪽)에 있는 모든 열도 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e24b1-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="e24b1-107">다른 모든 열을 스크롤할 수 있는 동안 고정된 열은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="e24b1-107">Frozen columns remain in place while all other columns can scroll.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e24b1-108">열 다시 정렬을 사용하는 경우 고정된 열은 고정되지 않은 열과 별개인 그룹으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e24b1-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="e24b1-109">사용자는 각 그룹에서 열의 위치를 변경할 수 있지만 그룹 간에 열을 이동할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e24b1-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>  
  
 <span data-ttu-id="e24b1-110">열의 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> 속성은 표에서 열이 항상 표시되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e24b1-110">The <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property of a column determines whether the column is always visible within the grid.</span></span>  
  
 <span data-ttu-id="e24b1-111">Visual Studio에서는 이 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e24b1-111">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="e24b1-112">또한 참조 [방법: 고정 열에는 Windows Forms DataGridView 컨트롤 디자이너를 사용 하 여](freeze-columns-in-the-datagrid-using-the-designer.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="e24b1-112">Also see [How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer](freeze-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-freeze-a-column-programmatically"></a><span data-ttu-id="e24b1-113">프로그래밍 방식으로 열을 고정하려면</span><span class="sxs-lookup"><span data-stu-id="e24b1-113">To freeze a column programmatically</span></span>  
  
-   <span data-ttu-id="e24b1-114"><xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e24b1-114">Set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e24b1-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e24b1-115">Compiling the Code</span></span>  
 <span data-ttu-id="e24b1-116">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e24b1-116">This example requires:</span></span>  
  
-   <span data-ttu-id="e24b1-117">이름이 `AddToCartButton`인 열을 포함하는 이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e24b1-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `AddToCartButton`.</span></span>  
  
-   <span data-ttu-id="e24b1-118">
  <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="e24b1-118">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e24b1-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="e24b1-119">See also</span></span>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="e24b1-120">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="e24b1-120">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="e24b1-121">방법: Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용</span><span class="sxs-lookup"><span data-stu-id="e24b1-121">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)
