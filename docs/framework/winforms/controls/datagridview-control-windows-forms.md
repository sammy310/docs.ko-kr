---
title: DataGridView 컨트롤
description: 컨트롤을 사용 하 여 `DataGridView` 적은 양의 데이터에 대 한 읽기 전용 보기를 표시 하거나 크기를 조정 하 여 매우 큰 데이터 집합에 대 한 편집 가능한 보기를 표시 하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- data grids [Windows Forms
- data [Windows Forms], displaying in tabular format
- grid controls [Windows Forms]
- datasets [Windows Forms], user interface
- Windows Forms, displaying data
- data presentation
- tabular data [Windows Forms], displaying on Windows Forms
- datasets [Windows Forms], displaying in DataGridView control
- DataGridView control [Windows Forms]
ms.assetid: dbee73f2-bba6-4874-9389-cd21d44309be
ms.openlocfilehash: f9a45e8be7975697ca5c0d019c6bc4119f562aea
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325892"
---
# <a name="datagridview-control-windows-forms"></a><span data-ttu-id="933c6-103">DataGridView 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="933c6-103">DataGridView Control (Windows Forms)</span></span>
<span data-ttu-id="933c6-104">`DataGridView` 컨트롤에서는 데이터를 표 형식으로 표시하는 강력하고 유연한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-104">The `DataGridView` control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="933c6-105">`DataGridView` 컨트롤을 사용하여 적은 양의 데이터에 대한 읽기 전용 보기를 표시하거나, 컨트롤을 확장하여 매우 큰 데이터 집합에 대한 편집 가능한 보기를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-105">You can use the `DataGridView` control to show read-only views of a small amount of data, or you can scale it to show editable views of very large sets of data.</span></span>  
  
 <span data-ttu-id="933c6-106">다양한 방법으로 `DataGridView` 컨트롤을 확장하여 사용자 지정 동작을 애플리케이션에 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-106">You can extend the `DataGridView` control in a number of ways to build custom behaviors into your applications.</span></span> <span data-ttu-id="933c6-107">예를 들어 프로그래밍 방식으로 고유한 정렬 알고리즘을 지정하고 고유한 셀 형식을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-107">For example, you can programmatically specify your own sorting algorithms, and you can create your own types of cells.</span></span> <span data-ttu-id="933c6-108">여러 속성 중에서 선택하여 `DataGridView` 컨트롤의 모양을 쉽게 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-108">You can easily customize the appearance of the `DataGridView` control by choosing among several properties.</span></span> <span data-ttu-id="933c6-109">대부분 데이터 저장소 형식을 데이터 소스로 사용하거나 `DataGridView` 컨트롤을 바인딩된 데이터 소스 없이 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-109">Many types of data stores can be used as a data source, or the `DataGridView` control can operate with no data source bound to it.</span></span>  
  
 <span data-ttu-id="933c6-110">이 섹션의 항목에서는 `DataGridView` 기능을 애플리케이션에 빌드하는 데 사용할 수 있는 개념 및 기술을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-110">The topics in this section describe the concepts and techniques that you can use to build `DataGridView` features into your applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="933c6-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="933c6-111">In This Section</span></span>  
 [<span data-ttu-id="933c6-112">DataGridView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="933c6-112">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)  
 <span data-ttu-id="933c6-113">Windows Forms `DataGridView` 컨트롤의 아키텍처와 핵심 개념을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-113">Provides topics that describe the architecture and core concepts of the Windows Forms `DataGridView` control.</span></span>  
  
 [<span data-ttu-id="933c6-114">Windows Forms DataGridView 컨트롤의 기본 기능</span><span class="sxs-lookup"><span data-stu-id="933c6-114">Default Functionality in the Windows Forms DataGridView Control</span></span>](default-functionality-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="933c6-115">데이터 소스에 바인딩될 때 Windows Forms `DataGridView` 컨트롤의 기본 모양과 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-115">Describes the default appearance and behavior of the Windows Forms `DataGridView` control when it is bound to a data source.</span></span>  
  
 [<span data-ttu-id="933c6-116">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="933c6-116">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="933c6-117">데이터를 표시하고 사용자가 데이터를 수정 또는 추가할 수 있도록 하는 데 사용되는 Windows Forms `DataGridView` 컨트롤의 열 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-117">Describes the column types in the Windows Forms `DataGridView` control used to display data and allow users to modify or add data.</span></span>  
  
 [<span data-ttu-id="933c6-118">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="933c6-118">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="933c6-119">일반적으로 사용되는 셀, 행 및 열 속성을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-119">Provides topics that describe commonly-used cell, row, and column properties.</span></span>  
  
 [<span data-ttu-id="933c6-120">Windows Forms DataGridView 컨트롤에서 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="933c6-120">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="933c6-121">컨트롤의 기본 모양과 셀 데이터의 표시 형식을 수정하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-121">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="933c6-122">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="933c6-122">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="933c6-123">수동으로 또는 외부 데이터 소스에서 컨트롤을 데이터로 채우는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-123">Provides topics that describe how to populate the control with data either manually, or from an external data source.</span></span>  
  
 [<span data-ttu-id="933c6-124">Windows Forms DataGridView 컨트롤에서 열 및 행 크기 조정</span><span class="sxs-lookup"><span data-stu-id="933c6-124">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="933c6-125">셀 내용에 맞추거나 컨트롤의 사용 가능한 너비에 맞춰서 행 및 열 크기를 자동으로 조정할 수 있는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-125">Provides topics that describe how the size of rows and columns can be adjusted automatically to fit cell content or to fit the available width of the control.</span></span>  
  
 [<span data-ttu-id="933c6-126">Windows Forms DataGridView 컨트롤의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="933c6-126">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="933c6-127">컨트롤의 정렬 기능을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-127">Provides topics that describe the sorting features in the control.</span></span>  
  
 [<span data-ttu-id="933c6-128">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="933c6-128">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="933c6-129">사용자가 컨트롤에서 데이터를 추가 및 수정하는 방법을 변경하는 방법에 대해 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-129">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
 [<span data-ttu-id="933c6-130">Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용</span><span class="sxs-lookup"><span data-stu-id="933c6-130">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="933c6-131">컨트롤의 셀, 행 및 열 선택 기능을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-131">Provides topics that describe the cell, row, and column selection features in the control.</span></span>  
  
 [<span data-ttu-id="933c6-132">Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="933c6-132">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="933c6-133">셀, 행 및 열 개체를 사용하여 프로그래밍하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-133">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
 [<span data-ttu-id="933c6-134">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="933c6-134">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="933c6-135">`DataGridView` 셀 및 행의 사용자 지정 그리기를 수행하고 파생된 셀, 열 및 행 형식을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-135">Provides topics that describe custom painting `DataGridView` cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="933c6-136">Windows Forms DataGridView 컨트롤의 성능 조정</span><span class="sxs-lookup"><span data-stu-id="933c6-136">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="933c6-137">컨트롤을 효율적으로 사용하여 대용량 데이터를 사용할 때 성능 문제를 방지하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-137">Provides topics that describe how to use the control efficiently to avoid performance problems when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="933c6-138">Windows Forms DataGridView 컨트롤의 기본 키보드 및 마우스 처리</span><span class="sxs-lookup"><span data-stu-id="933c6-138">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="933c6-139">사용자가 키보드와 마우스를 통해 `DataGridView` 컨트롤을 조작할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-139">Describes how users can interact with the `DataGridView` control through a keyboard and a mouse.</span></span>  
  
 [<span data-ttu-id="933c6-140">Windows Forms DataGridView 및 DataGrid 컨트롤 간의 차이점</span><span class="sxs-lookup"><span data-stu-id="933c6-140">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)  
 <span data-ttu-id="933c6-141">`DataGridView` 컨트롤로 <xref:System.Windows.Forms.DataGrid> 컨트롤을 개선하고 대체하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-141">Describes how the `DataGridView` control improves upon and replaces the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
 <span data-ttu-id="933c6-142">또한 [Windows Forms DataGridView 컨트롤과 함께 디자이너 사용](using-the-designer-with-the-windows-forms-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="933c6-142">Also see [Using the Designer with the Windows Forms DataGridView Control](using-the-designer-with-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="933c6-143">참조</span><span class="sxs-lookup"><span data-stu-id="933c6-143">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="933c6-144"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-144">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="933c6-145"><xref:System.Windows.Forms.BindingSource> 구성 요소에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-145">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="933c6-146"><xref:System.Windows.Forms.DataGridView> 컨트롤과 <xref:System.Windows.Forms.BindingSource> 구성 요소는 서로 긴밀하게 작동하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="933c6-146">The <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component are designed to work closely together.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="933c6-147">참조</span><span class="sxs-lookup"><span data-stu-id="933c6-147">See also</span></span>

- [<span data-ttu-id="933c6-148">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="933c6-148">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
