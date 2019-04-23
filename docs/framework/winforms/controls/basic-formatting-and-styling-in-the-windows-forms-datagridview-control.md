---
title: Windows Forms DataGridView 컨트롤에서 기본 형식 및 스타일 지정
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: 5e967c1bbe54095cc11e48b014600158da7fe6a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189898"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="9efc0-102">Windows Forms DataGridView 컨트롤에서 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="9efc0-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9efc0-103">`DataGridView` 컨트롤을 사용 하면 쉽게 셀의 기본 모양과 셀 값의 표시 형식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="9efc0-104">모양을 정의할 수 있으며, 개별 셀, 특정 열과 행의 셀 또는 컨트롤의 모든 셀에 대 한 속성을 설정 하 여 스타일 서식 지정 된 `DataGridViewCellStyle` 다양 한를 통해 액세스 되는 개체 `DataGridView` 속성을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="9efc0-105">또한 처리 하 여 셀 값 등의 요인에 따라 동적으로 이러한 스타일을 수정할 수는 `CellFormatting` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9efc0-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="9efc0-106">In This Section</span></span>  
 [<span data-ttu-id="9efc0-107">방법: 테두리 및 Windows Forms DataGridView 컨트롤의 모눈선 스타일 변경</span><span class="sxs-lookup"><span data-stu-id="9efc0-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="9efc0-108">설정 하는 방법에 설명 `DataGridView` 컨트롤 테두리 및 셀 사이의 경계 줄의 모양을 정의 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="9efc0-109">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="9efc0-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9efc0-110">에 대해 설명 합니다 `DataGridViewCellStyle` 클래스 및 해당 형식의 속성은 컨트롤에서 셀을 표시 하는 방법을 정의 하려면 상호 작용 하는 방법을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="9efc0-111">방법: Windows Forms DataGridView 컨트롤에 대 한 기본 셀 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="9efc0-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9efc0-112">사용 하는 방법에 설명 `DataGridViewCellStyle` 전체 컨트롤에 특정 행과 열에서 셀의 기본 모양을 정의 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="9efc0-113">방법: 형식 데이터에는 Windows Forms DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9efc0-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9efc0-114">사용 하 여 셀 표시 값의 서식을 지정 하는 방법에 설명 `DataGridViewCellStyle` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="9efc0-115">방법: Windows Forms DataGridView 컨트롤의 글꼴 및 색 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="9efc0-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9efc0-116">사용 하는 방법에 설명 합니다 `DefaultCellStyle` 속성을 기본 설정 컨트롤의 모든 셀에 대 한 특성을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="9efc0-117">방법: Windows Forms DataGridView 컨트롤에 대 한 행 스타일 교대로 반복 되는 설정</span><span class="sxs-lookup"><span data-stu-id="9efc0-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9efc0-118">다르게 표시 되는 교대로 반복 되는 행을 사용 하 여 컨트롤에서 장부와 비슷한 효과 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="9efc0-119">방법: 행 템플릿을 사용 하 여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9efc0-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="9efc0-120">사용 하는 방법에 설명 합니다 `RowTemplate` 속성을 컨트롤의 모든 행에 사용할 행 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9efc0-121">참조</span><span class="sxs-lookup"><span data-stu-id="9efc0-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="9efc0-122"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="9efc0-123">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="9efc0-124">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="9efc0-125">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9efc0-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="9efc0-126">Related Sections</span></span>  
 [<span data-ttu-id="9efc0-127">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9efc0-127">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="9efc0-128"><xref:System.Windows.Forms.DataGridView> 셀 및 행의 사용자 지정 그리기를 수행하고 파생된 셀, 열 및 행 형식을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="9efc0-129">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="9efc0-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="9efc0-130">셀, 행 및 열 속성을 사용 하는 일반적으로 설명 하는 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9efc0-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efc0-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="9efc0-131">See also</span></span>

- [<span data-ttu-id="9efc0-132">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9efc0-132">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
