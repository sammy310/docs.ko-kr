---
title: '방법: 테두리 및 Windows Forms DataGridView 컨트롤의 모눈선 스타일 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: b4984dca6fb7dc8575b00758f0d61d9ff011e1ca
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703371"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="5473b-102">방법: 테두리 및 Windows Forms DataGridView 컨트롤의 모눈선 스타일 변경</span><span class="sxs-lookup"><span data-stu-id="5473b-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5473b-103">사용 하 여는 <xref:System.Windows.Forms.DataGridView> 컨트롤, 컨트롤의 테두리 및 사용자 환경을 개선 하는 눈금선의 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5473b-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="5473b-104">모눈선 색과 컨트롤 내에 있는 셀의 테두리 스타일 외에도 컨트롤의 테두리 스타일을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5473b-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="5473b-105">또한 일반 셀, 행 머리글 셀 및 열 머리글 셀에 대 한 다른 셀 테두리 스타일을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5473b-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5473b-106">눈금선 색만 사용 됩니다는 <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, 및 <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> 의 값을 <xref:System.Windows.Forms.DataGridViewCellBorderStyle> 열거형 및 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> 값은 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> 열거형.</span><span class="sxs-lookup"><span data-stu-id="5473b-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="5473b-107">이러한 열거형의 다른 값을 사용 하 여 운영 체제에서 지정 된 색입니다.</span><span class="sxs-lookup"><span data-stu-id="5473b-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="5473b-108">비주얼 스타일이 Windows XP 및 Windows Server 2003 제품군을 통해 사용 되는 경우에 또한 합니다 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드를는 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 속성 값이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5473b-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="5473b-109">프로그래밍 방식으로 눈금선 색을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="5473b-109">To change the gridline color programmatically</span></span>  
  
-   <span data-ttu-id="5473b-110">
  <xref:System.Windows.Forms.DataGridView.GridColor%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5473b-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="5473b-111">프로그래밍 방식으로 전체 DataGridView 컨트롤의 테두리 스타일을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="5473b-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
-   <span data-ttu-id="5473b-112">
  <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> 속성을 <xref:System.Windows.Forms.BorderStyle> 열거형 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5473b-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="5473b-113">DataGridView 셀의 테두리 스타일을 프로그래밍 방식으로 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="5473b-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
-   <span data-ttu-id="5473b-114"><xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>및 <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5473b-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="5473b-115">예제</span><span class="sxs-lookup"><span data-stu-id="5473b-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5473b-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5473b-116">Compiling the Code</span></span>  
 <span data-ttu-id="5473b-117">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5473b-117">This example requires:</span></span>  
  
-   <span data-ttu-id="5473b-118">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5473b-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="5473b-119">
  <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> 및 <xref:System.Drawing?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="5473b-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5473b-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="5473b-120">See also</span></span>
- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [<span data-ttu-id="5473b-121">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="5473b-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
