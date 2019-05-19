---
title: DataGrid 컨트롤(Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- datasets [Windows Forms], user interface
- DataGrid control [Windows Forms]
- datasets [Windows Forms], displaying in DataGrid control
- displaying data [Windows Forms], on forms
- data [Windows Forms], displaying on Windows Forms
ms.assetid: 1d9d5683-43d2-42dd-b6c3-e43f4cf0de99
ms.openlocfilehash: 5a69605901eef7366c7a9ff9930e5f4ec6cece23
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878764"
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="f9a5a-102">DataGrid 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f9a5a-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="f9a5a-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 `DataGrid` 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 `DataGrid` 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="f9a5a-104">자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="f9a5a-105">Windows Forms `DataGrid` 컨트롤은 ADO.NET 데이터 집합을 표 형식 데이터를 표시 하 고 데이터 원본에 대 한 업데이트를 사용 하도록 설정 하기 위한 사용자 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-105">The Windows Forms `DataGrid` control provides a user interface to ADO.NET datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="f9a5a-106">`DataGrid` 컨트롤이 유효한 데이터 소스로 설정되면 컨트롤에 데이터를 자동으로 채우고 데이터의 모양에 기반하여 열과 행을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="f9a5a-107">`DataGrid` 컨트롤은 단일 테이블 또는 테이블 집합 간의 계층 관계를 표시하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9a5a-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f9a5a-108">In This Section</span></span>  
 [<span data-ttu-id="f9a5a-109">DataGrid 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="f9a5a-109">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="f9a5a-110">`DataGrid` 컨트롤의 기본 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f9a5a-111">방법: 디자이너를 사용 하 여 Windows Forms DataGrid 컨트롤에 테이블과 열 추가</span><span class="sxs-lookup"><span data-stu-id="f9a5a-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="f9a5a-112">디자이너를 사용하여 `DataGrid` 컨트롤에 테이블과 열을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="f9a5a-113">방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가</span><span class="sxs-lookup"><span data-stu-id="f9a5a-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="f9a5a-114">프로그래밍 방식으로 `DataGrid` 컨트롤에 테이블과 열을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="f9a5a-115">방법: 디자이너를 사용 하 여 데이터 원본에 Windows Forms DataGrid 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="f9a5a-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="f9a5a-116">ADO.NET 데이터 집합을 바인딩하는 방법을 설명 합니다 `DataGrid` 디자이너를 사용 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-116">Describes how to bind an ADO.NET dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="f9a5a-117">방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="f9a5a-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="f9a5a-118">ADO.NET 데이터 집합을 바인딩하는 방법을 설명 합니다 `DataGrid` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-118">Describes how to bind an ADO.NET dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f9a5a-119">방법: 런타임에 Windows Forms DataGrid 컨트롤에서 표시 된 데이터 변경</span><span class="sxs-lookup"><span data-stu-id="f9a5a-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="f9a5a-120">`DataGrid` 컨트롤에서 프로그래밍 방식으로 데이터를 변경하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f9a5a-121">방법: 디자이너를 사용 하 여 Windows Forms DataGrid 컨트롤을 사용 하 여 마스터-세부 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="f9a5a-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="f9a5a-122">디자이너를 사용하여 부모/자식 관계로 결합된 두 테이블을 별개의 두 `DataGrid` 컨트롤에 표시하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="f9a5a-123">방법: Windows Forms DataGrid 컨트롤을 사용 하 여 마스터-세부 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="f9a5a-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="f9a5a-124">부모/자식 관계로 결합된 두 테이블을 별개의 두 `DataGrid` 컨트롤에 표시하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="f9a5a-125">방법: Windows Forms DataGrid 컨트롤에서 열 숨기기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="f9a5a-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="f9a5a-126">`DataGrid` 컨트롤에서 열을 제거하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f9a5a-127">방법: 디자이너를 사용 하 여 Windows Forms DataGrid 컨트롤 서식 지정</span><span class="sxs-lookup"><span data-stu-id="f9a5a-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="f9a5a-128">디자이너를 사용하여 `DataGrid` 컨트롤의 모양과 관련된 속성을 변경하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="f9a5a-129">방법: Windows Forms DataGrid 컨트롤 서식 지정</span><span class="sxs-lookup"><span data-stu-id="f9a5a-129">How to: Format the Windows Forms DataGrid Control</span></span>](how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="f9a5a-130">`DataGrid` 컨트롤의 모양과 관련된 속성을 변경하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f9a5a-131">Windows Forms DataGrid 컨트롤을 위한 바로 가기 키</span><span class="sxs-lookup"><span data-stu-id="f9a5a-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="f9a5a-132">`DataGrid` 컨트롤을 탐색하기 위한 바로 가기를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f9a5a-133">방법: Windows Forms DataGrid 컨트롤에서 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="f9a5a-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="f9a5a-134">사용자가 `DataGrid` 컨트롤에서 클릭한 셀을 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f9a5a-135">방법: Windows Forms DataGrid 컨트롤을 사용 하 여 입력 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f9a5a-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="f9a5a-136">`DataGrid` 컨트롤에 바인딩된 데이터 집합의 입력에 대한 유효성을 검사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f9a5a-137">참조</span><span class="sxs-lookup"><span data-stu-id="f9a5a-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="f9a5a-138">개요를 제공 합니다 <xref:System.Windows.Forms.DataGrid> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="f9a5a-139">바인딩할이 속성을 사용 하는 방법에 대 한 세부 정보를 제공 합니다 <xref:System.Windows.Forms.DataGrid> 데이터 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f9a5a-140">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f9a5a-140">Related Sections</span></span>  
 [<span data-ttu-id="f9a5a-141">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="f9a5a-141">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="f9a5a-142">Windows Forms의 데이터 바인딩과 관련된 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a5a-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a5a-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="f9a5a-143">See also</span></span>

- [<span data-ttu-id="f9a5a-144">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f9a5a-144">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="f9a5a-145">Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점</span><span class="sxs-lookup"><span data-stu-id="f9a5a-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)
