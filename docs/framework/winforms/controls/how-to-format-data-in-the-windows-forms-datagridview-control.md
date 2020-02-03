---
title: DataGridView 컨트롤의 데이터 서식 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: 9ee2869cf4085b5acfdf1f8c440151be506dbe3e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736784"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d0319-102">방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="d0319-102">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d0319-103">다음 절차에서는 컨트롤의 <xref:System.Windows.Forms.DataGridView> 컨트롤과 특정 열의 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 속성을 사용 하 여 셀 값의 기본적인 서식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-103">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="d0319-104">고급 데이터 서식에 대 한 자세한 내용은 [방법: DataGridView 컨트롤 Windows Forms에서 데이터 형식 사용자 지정](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0319-104">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="d0319-105">통화 및 날짜 값의 서식을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="d0319-105">To format currency and date values</span></span>  
  
- <span data-ttu-id="d0319-106"><xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>의 <xref:System.Windows.Forms.DataGridViewCellStyle> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-106">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="d0319-107">다음 코드 예에서는 열의 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 속성을 사용 하 여 특정 열의 형식을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-107">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="d0319-108">`UnitPrice` 열의 값은 현재 문화권별 통화 형식으로 표시 되며 음수 값은 괄호로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-108">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="d0319-109">`ShipDate` 열의 값은 현재 문화권별 짧은 날짜 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-109">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="d0319-110"><xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 값에 대 한 자세한 내용은 [형식 서식 지정](../../../standard/base-types/formatting-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0319-110">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="d0319-111">Null 데이터베이스 값의 표시를 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="d0319-111">To customize the display of null database values</span></span>  
  
- <span data-ttu-id="d0319-112"><xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A>의 <xref:System.Windows.Forms.DataGridViewCellStyle> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="d0319-113">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 속성을 사용 하 여 <xref:System.DBNull.Value?displayProperty=nameWithType>와 같은 값을 포함 하는 모든 셀에 "no entry"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="d0319-114">텍스트 기반 셀에서 wordwrap를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d0319-114">To enable wordwrap in text-based cells</span></span>  
  
- <span data-ttu-id="d0319-115"><xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewTriState> 열거형 값 중 하나로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="d0319-116">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 속성을 사용 하 여 전체 컨트롤에 대 한 줄 바꿈 모드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="d0319-117">DataGridView 셀의 텍스트 맞춤을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="d0319-117">To specify the text alignment of DataGridView cells</span></span>  
  
- <span data-ttu-id="d0319-118"><xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> 속성을 <xref:System.Windows.Forms.DataGridViewContentAlignment> 열거형 값 중 하나로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="d0319-119">다음 코드 예에서는 열의 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 속성을 사용 하 여 특정 열에 대 한 맞춤을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-119">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="d0319-120">예제</span><span class="sxs-lookup"><span data-stu-id="d0319-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d0319-121">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d0319-121">Compiling the Code</span></span>  
 <span data-ttu-id="d0319-122">이러한 예제에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-122">These examples require:</span></span>  
  
- <span data-ttu-id="d0319-123">이름이 `UnitPrice`열, `ShipDate`이라는 열 및 `CustomerName`이라는 열을 포함 하는 `dataGridView1` 이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d0319-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
- <span data-ttu-id="d0319-124"><xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="d0319-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d0319-125">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d0319-125">Robust Programming</span></span>  
 <span data-ttu-id="d0319-126">확장성을 최대화 하려면 각 요소에 대 한 스타일 속성을 별도로 설정 하는 대신 동일한 스타일을 사용 하는 여러 행, 열 또는 셀에서 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 공유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="d0319-127">자세한 내용은 [Windows Forms DataGridView 컨트롤의 크기 조정에 대 한 모범 사례](best-practices-for-scaling-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0319-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0319-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0319-128">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="d0319-129">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="d0319-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d0319-130">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="d0319-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d0319-131">Windows Forms DataGridView 컨트롤의 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="d0319-131">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d0319-132">방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d0319-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d0319-133">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="d0319-133">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
