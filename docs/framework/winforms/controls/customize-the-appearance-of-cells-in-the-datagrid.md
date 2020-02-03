---
title: DataGridView 컨트롤에서 셀 모양 사용자 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744048"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="09ea3-102">방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="09ea3-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="09ea3-103"><xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellPainting> 이벤트를 처리 하 여 모든 셀의 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ea3-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="09ea3-104"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>의 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> 속성에서 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Drawing.Graphics>을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ea3-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="09ea3-105">이 <xref:System.Drawing.Graphics>사용 하면 전체 <xref:System.Windows.Forms.DataGridView> 컨트롤의 모양에 영향을 줄 수 있지만 일반적으로 현재 칠하는 중인 셀의 모양에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="09ea3-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="09ea3-106"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>의 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> 속성을 사용 하면 그리기 작업을 현재 칠하는 셀로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ea3-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="09ea3-107">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 색 구성표를 사용 하 여 `ContactName` 열의 모든 셀을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="09ea3-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="09ea3-108">각 셀의 텍스트 콘텐츠는 <xref:System.Drawing.Color.Crimson%2A>그려집니다. 삽입 사각형은 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 속성과 동일한 색으로 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="09ea3-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09ea3-109">예제</span><span class="sxs-lookup"><span data-stu-id="09ea3-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="09ea3-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="09ea3-110">Compiling the Code</span></span>  
 <span data-ttu-id="09ea3-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="09ea3-111">This example requires:</span></span>  
  
- <span data-ttu-id="09ea3-112">Northwind 샘플 데이터베이스의 Customers 테이블에 있는 것과 같은 `ContactName` 열과 함께 `dataGridView1` 라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="09ea3-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="09ea3-113">System, System.Windows.Forms 및 System.Drawing 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="09ea3-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ea3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09ea3-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="09ea3-115">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="09ea3-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
