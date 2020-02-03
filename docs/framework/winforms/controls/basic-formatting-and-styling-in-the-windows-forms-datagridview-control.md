---
title: DataGridView 컨트롤의 기본 형식 및 스타일 지정
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d295718b7bd4f3bc4c5f63b6e6cb911f733525fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732003"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a2231-102">Windows Forms DataGridView 컨트롤에서 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="a2231-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a2231-103">`DataGridView` 컨트롤을 사용 하면 셀의 기본 모양과 셀 값의 표시 형식을 쉽게 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="a2231-104">다양 한 `DataGridView` 컨트롤 속성을 통해 액세스 되는 `DataGridViewCellStyle` 개체의 속성을 설정 하 여 개별 셀, 특정 열 및 행의 셀 또는 컨트롤의 모든 셀에 대 한 모양 및 서식 스타일을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="a2231-105">또한 `CellFormatting` 이벤트를 처리 하 여 셀 값과 같은 요소에 따라 이러한 스타일을 동적으로 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a2231-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a2231-106">In This Section</span></span>  
 [<span data-ttu-id="a2231-107">방법: Windows Forms DataGridView 컨트롤의 테두리 및 모눈선 스타일 변경</span><span class="sxs-lookup"><span data-stu-id="a2231-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="a2231-108">컨트롤 테두리의 모양과 셀 사이의 경계 선을 정의 하는 `DataGridView` 속성을 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="a2231-109">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="a2231-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a2231-110">`DataGridViewCellStyle` 클래스와 해당 형식의 속성을 조작 하 여 셀이 컨트롤에 표시 되는 방식을 정의 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="a2231-111">방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="a2231-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a2231-112">`DataGridViewCellStyle` 속성을 사용 하 여 특정 행 및 열과 전체 컨트롤에 있는 셀의 기본 모양을 정의 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="a2231-113">방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="a2231-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a2231-114">`DataGridViewCellStyle` 속성을 사용 하 여 셀 표시 값의 서식을 지정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="a2231-115">방법: Windows Forms DataGridView 컨트롤의 글꼴 및 색 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="a2231-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a2231-116">`DefaultCellStyle` 속성을 사용 하 여 컨트롤의 모든 셀에 대 한 기본 표시 특성을 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="a2231-117">방법: Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="a2231-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a2231-118">다르게 표시 되는 교대로 반복 되는 행을 사용 하 여 컨트롤에서 장부와 유사한 효과를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="a2231-119">방법: 행 템플릿을 사용하여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a2231-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="a2231-120">`RowTemplate` 속성을 사용 하 여 컨트롤의 모든 행에 사용 되는 행 속성을 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a2231-121">참조</span><span class="sxs-lookup"><span data-stu-id="a2231-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="a2231-122"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="a2231-123"><xref:System.Windows.Forms.DataGridViewCellStyle> 클래스에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="a2231-124"><xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="a2231-125"><xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a2231-126">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="a2231-126">Related Sections</span></span>  
 [<span data-ttu-id="a2231-127">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a2231-127">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a2231-128"><xref:System.Windows.Forms.DataGridView> 셀 및 행의 사용자 지정 그리기를 수행하고 파생된 셀, 열 및 행 형식을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="a2231-129">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="a2231-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="a2231-130">일반적으로 사용 되는 셀, 행 및 열 속성을 설명 하는 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2231-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2231-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2231-131">See also</span></span>

- [<span data-ttu-id="a2231-132">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a2231-132">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
