---
title: DataGrid 컨트롤
ms.date: 03/30/2017
helpviewer_keywords:
- datasets [Windows Forms], user interface
- DataGrid control [Windows Forms]
- datasets [Windows Forms], displaying in DataGrid control
- displaying data [Windows Forms], on forms
- data [Windows Forms], displaying on Windows Forms
ms.assetid: 1d9d5683-43d2-42dd-b6c3-e43f4cf0de99
ms.openlocfilehash: efcc8770232f657c13135cefb4027f814d4d7d19
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742517"
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="a89c7-102">DataGrid 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a89c7-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="a89c7-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 `DataGrid` 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 `DataGrid` 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="a89c7-104">자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a89c7-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="a89c7-105">Windows Forms `DataGrid` 컨트롤은 데이터 집합을 ADO.NET 하 고, 테이블 형식 데이터를 표시 하 고, 데이터 소스를 업데이트할 수 있는 사용자 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-105">The Windows Forms `DataGrid` control provides a user interface to ADO.NET datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="a89c7-106">`DataGrid` 컨트롤이 유효한 데이터 소스로 설정되면 컨트롤에 데이터를 자동으로 채우고 데이터의 모양에 기반하여 열과 행을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="a89c7-107">`DataGrid` 컨트롤은 단일 테이블 또는 테이블 집합 간의 계층 관계를 표시하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a89c7-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a89c7-108">In This Section</span></span>  
 [<span data-ttu-id="a89c7-109">DataGrid 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="a89c7-109">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="a89c7-110">`DataGrid` 컨트롤의 기본 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="a89c7-111">방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 테이블 및 열 추가</span><span class="sxs-lookup"><span data-stu-id="a89c7-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="a89c7-112">디자이너를 사용하여 `DataGrid` 컨트롤에 테이블과 열을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="a89c7-113">방법: Windows Forms DataGrid 컨트롤에 테이블 및 열 추가</span><span class="sxs-lookup"><span data-stu-id="a89c7-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="a89c7-114">프로그래밍 방식으로 `DataGrid` 컨트롤에 테이블과 열을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="a89c7-115">방법: 디자이너를 사용하여 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="a89c7-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="a89c7-116">디자이너를 사용 하 여 ADO.NET 데이터 집합을 `DataGrid` 컨트롤에 바인딩하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-116">Describes how to bind an ADO.NET dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="a89c7-117">방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="a89c7-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="a89c7-118">ADO.NET 데이터 집합을 `DataGrid` 컨트롤에 바인딩하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-118">Describes how to bind an ADO.NET dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="a89c7-119">방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경</span><span class="sxs-lookup"><span data-stu-id="a89c7-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="a89c7-120">`DataGrid` 컨트롤에서 프로그래밍 방식으로 데이터를 변경하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="a89c7-121">방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 마스터-세부 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="a89c7-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="a89c7-122">디자이너를 사용하여 부모/자식 관계로 결합된 두 테이블을 별개의 두 `DataGrid` 컨트롤에 표시하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="a89c7-123">방법: Windows Forms DataGrid 컨트롤을 사용하여 마스터/세부 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="a89c7-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="a89c7-124">부모/자식 관계로 결합된 두 테이블을 별개의 두 `DataGrid` 컨트롤에 표시하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="a89c7-125">방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기</span><span class="sxs-lookup"><span data-stu-id="a89c7-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="a89c7-126">`DataGrid` 컨트롤에서 열을 제거하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="a89c7-127">방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤 서식 지정</span><span class="sxs-lookup"><span data-stu-id="a89c7-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="a89c7-128">디자이너를 사용하여 `DataGrid` 컨트롤의 모양과 관련된 속성을 변경하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="a89c7-129">방법: Windows Forms DataGrid 컨트롤 서식 지정</span><span class="sxs-lookup"><span data-stu-id="a89c7-129">How to: Format the Windows Forms DataGrid Control</span></span>](how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="a89c7-130">`DataGrid` 컨트롤의 모양과 관련된 속성을 변경하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="a89c7-131">Windows Forms DataGrid 컨트롤을 위한 바로 가기 키</span><span class="sxs-lookup"><span data-stu-id="a89c7-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="a89c7-132">`DataGrid` 컨트롤을 탐색하기 위한 바로 가기를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="a89c7-133">방법: Windows Forms DataGrid 컨트롤에서 클릭에 대한 응답</span><span class="sxs-lookup"><span data-stu-id="a89c7-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="a89c7-134">사용자가 `DataGrid` 컨트롤에서 클릭한 셀을 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="a89c7-135">방법: Windows Forms DataGrid 컨트롤을 사용하여 입력 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a89c7-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="a89c7-136">`DataGrid` 컨트롤에 바인딩된 데이터 세트의 입력에 대한 유효성을 검사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a89c7-137">참조</span><span class="sxs-lookup"><span data-stu-id="a89c7-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="a89c7-138"><xref:System.Windows.Forms.DataGrid> 클래스에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="a89c7-139">이 속성을 사용 하 여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 데이터에 바인딩하는 방법에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a89c7-140">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="a89c7-140">Related Sections</span></span>  
 [<span data-ttu-id="a89c7-141">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="a89c7-141">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="a89c7-142">Windows Forms의 데이터 바인딩과 관련된 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a89c7-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a89c7-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a89c7-143">See also</span></span>

- [<span data-ttu-id="a89c7-144">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a89c7-144">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="a89c7-145">Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점</span><span class="sxs-lookup"><span data-stu-id="a89c7-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)
