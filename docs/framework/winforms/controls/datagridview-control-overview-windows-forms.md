---
title: DataGridView 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- DataGridView
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- grid controls [Windows Forms]
- tables [Windows Forms], displaying in DataGridView control
- tables [Windows Forms], binding to DataGridView control
- columns [Windows Forms], DataGridView control
- bound controls [Windows Forms], dataGridView control
- datasets [Windows Forms], binding to DataGridView control
- data grids [Windows Forms], about data grids
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- grids [Windows Forms]
- data binding [Windows Forms], DataGridView control
- data sources [Windows Forms], binding to DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
ms.openlocfilehash: 74de5b449525be9ff93fcbef0ddabd041470177c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742485"
---
# <a name="datagridview-control-overview-windows-forms"></a><span data-ttu-id="1e45a-102">DataGridView 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1e45a-102">DataGridView Control Overview (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="1e45a-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="1e45a-104">자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e45a-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="1e45a-105"><xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하 여 다양 한 종류의 데이터 원본에서 테이블 형식 데이터를 표시 하 고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-105">With the <xref:System.Windows.Forms.DataGridView> control, you can display and edit tabular data from many different kinds of data sources.</span></span>  
  
 <span data-ttu-id="1e45a-106">데이터를 <xref:System.Windows.Forms.DataGridView> 컨트롤에 바인딩하는 것은 간단 하 고 직관적 이며, 대부분의 경우 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성을 설정 하는 것 만큼 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-106">Binding data to the <xref:System.Windows.Forms.DataGridView> control is straightforward and intuitive, and in many cases it is as simple as setting the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span> <span data-ttu-id="1e45a-107">여러 목록이 나 테이블이 포함 된 데이터 원본에 바인딩하는 경우 <xref:System.Windows.Forms.DataGridView.DataMember%2A> 속성을 바인딩할 목록이 나 테이블을 지정 하는 문자열로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-107">When you bind to a data source that contains multiple lists or tables, set the <xref:System.Windows.Forms.DataGridView.DataMember%2A> property to a string that specifies the list or table to bind to.</span></span>  
  
 <span data-ttu-id="1e45a-108"><xref:System.Windows.Forms.DataGridView> 컨트롤은 표준 Windows Forms 데이터 바인딩 모델을 지원 하므로 다음 목록에서 설명 하는 클래스의 인스턴스에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-108">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to instances of classes described in the following list:</span></span>  
  
- <span data-ttu-id="1e45a-109">1 차원 배열을 포함 하 여 <xref:System.Collections.IList> 인터페이스를 구현 하는 모든 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-109">Any class that implements the <xref:System.Collections.IList> interface, including one-dimensional arrays.</span></span>  
  
- <span data-ttu-id="1e45a-110"><xref:System.Data.DataTable> 및 <xref:System.Data.DataSet> 클래스와 같은 <xref:System.ComponentModel.IListSource> 인터페이스를 구현 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-110">Any class that implements the <xref:System.ComponentModel.IListSource> interface, such as the <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes.</span></span>  
  
- <span data-ttu-id="1e45a-111"><xref:System.ComponentModel.BindingList%601> 클래스와 같은 <xref:System.ComponentModel.IBindingList> 인터페이스를 구현 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-111">Any class that implements the <xref:System.ComponentModel.IBindingList> interface, such as the <xref:System.ComponentModel.BindingList%601> class.</span></span>  
  
- <span data-ttu-id="1e45a-112"><xref:System.Windows.Forms.BindingSource> 클래스와 같은 <xref:System.ComponentModel.IBindingListView> 인터페이스를 구현 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-112">Any class that implements the <xref:System.ComponentModel.IBindingListView> interface, such as the <xref:System.Windows.Forms.BindingSource> class.</span></span>  
  
 <span data-ttu-id="1e45a-113"><xref:System.Windows.Forms.DataGridView> 컨트롤은 반환 된 개체에서 구현 되는 경우 이러한 인터페이스 또는 <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스에서 반환 된 속성 컬렉션에 의해 반환 되는 개체의 공용 속성에 대 한 데이터 바인딩을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-113">The <xref:System.Windows.Forms.DataGridView> control supports data binding to the public properties of the objects returned by these interfaces or to the properties collection returned by an <xref:System.ComponentModel.ICustomTypeDescriptor> interface, if implemented on the returned objects.</span></span>  
  
 <span data-ttu-id="1e45a-114">일반적으로 바인딩할를 <xref:System.Windows.Forms.BindingSource> 구성 요소 및 바인딩은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 다른 데이터 원본 또는 비즈니스 개체를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-114">Typically, you will bind to a <xref:System.Windows.Forms.BindingSource> component and bind the <xref:System.Windows.Forms.BindingSource> component to another data source or populate it with business objects.</span></span> <span data-ttu-id="1e45a-115"><xref:System.Windows.Forms.BindingSource> 다양 한 데이터 원본에 바인딩할 수 있습니다 하 고 많은 데이터 바인딩 문제를 자동으로 해결할 수 있기 때문에 구성 요소는 기본 데이터 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-115">The <xref:System.Windows.Forms.BindingSource> component is the preferred data source because it can bind to a wide variety of data sources and can resolve many data binding issues automatically.</span></span> <span data-ttu-id="1e45a-116">자세한 내용은 [BindingSource 구성 요소](bindingsource-component.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1e45a-116">For more information, see [BindingSource Component](bindingsource-component.md).</span></span>  
  
 <span data-ttu-id="1e45a-117">기본 데이터 저장소가 없는 *바인딩되지* 않은 모드 에서도 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-117">The <xref:System.Windows.Forms.DataGridView> control can also be used in *unbound* mode, with no underlying data store.</span></span> <span data-ttu-id="1e45a-118">바인딩되지 않은 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하는 코드 예제는 [연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1e45a-118">For a code example that uses an unbound <xref:System.Windows.Forms.DataGridView> control, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="1e45a-119"><xref:System.Windows.Forms.DataGridView> 컨트롤은 매우 구성 가능 하 고 확장 가능 하며 여러 속성, 메서드 및 이벤트를 제공 하 여 모양과 동작을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-119">The <xref:System.Windows.Forms.DataGridView> control is highly configurable and extensible, and it provides many properties, methods, and events to customize its appearance and behavior.</span></span> <span data-ttu-id="1e45a-120">Windows Forms 응용 프로그램에서 표 형식 데이터를 표시 하려면 다른 컨트롤 앞에 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하는 것이 좋습니다 (예: <xref:System.Windows.Forms.DataGrid>).</span><span class="sxs-lookup"><span data-stu-id="1e45a-120">When you want your Windows Forms application to display tabular data, consider using the <xref:System.Windows.Forms.DataGridView> control before others (for example, <xref:System.Windows.Forms.DataGrid>).</span></span> <span data-ttu-id="1e45a-121">읽기 전용 값의 작은 그리드를 표시 하거나 사용자가 수백만 개의 레코드를 사용 하 여 테이블을 편집할 수 있도록 설정 하는 경우 <xref:System.Windows.Forms.DataGridView> 컨트롤은 메모리 효율이 뛰어난 프로그래밍 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-121">If you are displaying a small grid of read-only values, or if you are enabling a user to edit a table with millions of records, the <xref:System.Windows.Forms.DataGridView> control will provide you with a readily programmable, memory-efficient solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e45a-122">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1e45a-122">In This Section</span></span>  
 [<span data-ttu-id="1e45a-123">DataGridView 컨트롤 기술 요약</span><span class="sxs-lookup"><span data-stu-id="1e45a-123">DataGridView Control Technology Summary</span></span>](datagridview-control-technology-summary-windows-forms.md)  
 <span data-ttu-id="1e45a-124">관련 클래스의 개념 및 사용을 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-124">Summarizes <xref:System.Windows.Forms.DataGridView> control concepts and the use of related classes.</span></span>  
  
 [<span data-ttu-id="1e45a-125">DataGridView 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="1e45a-125">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)  
 <span data-ttu-id="1e45a-126">해당 형식 계층 구조 및 상속 구조를 설명 하는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 아키텍처에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-126">Describes the architecture of the <xref:System.Windows.Forms.DataGridView> control, explaining its type hierarchy and inheritance structure.</span></span>  
  
 [<span data-ttu-id="1e45a-127">DataGridView 컨트롤 시나리오</span><span class="sxs-lookup"><span data-stu-id="1e45a-127">DataGridView Control Scenarios</span></span>](datagridview-control-scenarios-windows-forms.md)  
 <span data-ttu-id="1e45a-128"><xref:System.Windows.Forms.DataGridView> 컨트롤이 사용 되는 가장 일반적인 시나리오를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-128">Describes the most common scenarios in which <xref:System.Windows.Forms.DataGridView> controls are used.</span></span>  
  
 [<span data-ttu-id="1e45a-129">DataGridView 컨트롤 코드 디렉터리</span><span class="sxs-lookup"><span data-stu-id="1e45a-129">DataGridView Control Code Directory</span></span>](datagridview-control-code-directory-windows-forms.md)  
 <span data-ttu-id="1e45a-130">다양 한 <xref:System.Windows.Forms.DataGridView> 작업에 대 한 설명서의 코드 예제에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-130">Provides links to code examples in the documentation for various <xref:System.Windows.Forms.DataGridView> tasks.</span></span> <span data-ttu-id="1e45a-131">이러한 예제는 작업 형식별로 분류되어 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-131">These examples are categorized by task type.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1e45a-132">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="1e45a-132">Related Sections</span></span>  
 [<span data-ttu-id="1e45a-133">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="1e45a-133">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="1e45a-134">정보를 표시 하는 데 사용 되는 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤의 열 형식에 대해 설명 하 고 사용자가 정보를 수정 또는 추가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-134">Discusses the column types in the Windows Forms <xref:System.Windows.Forms.DataGridView> control used to display information and allow users to modify or add information.</span></span>  
  
 [<span data-ttu-id="1e45a-135">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="1e45a-135">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="1e45a-136">수동으로 또는 외부 데이터 소스에서 컨트롤을 데이터로 채우는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-136">Provides topics that describe how to populate the control with data either manually, or from an external data source.</span></span>  
  
 [<span data-ttu-id="1e45a-137">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1e45a-137">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="1e45a-138"><xref:System.Windows.Forms.DataGridView> 셀 및 행의 사용자 지정 그리기를 수행하고 파생된 셀, 열 및 행 형식을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-138">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="1e45a-139">Windows Forms DataGridView 컨트롤의 성능 조정</span><span class="sxs-lookup"><span data-stu-id="1e45a-139">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="1e45a-140">컨트롤을 효율적으로 사용하여 대용량 데이터를 사용할 때 성능 문제를 방지하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e45a-140">Provides topics that describe how to use the control efficiently to avoid performance problems when working with large amounts of data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e45a-141">참조</span><span class="sxs-lookup"><span data-stu-id="1e45a-141">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="1e45a-142">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1e45a-142">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="1e45a-143">Windows Forms DataGridView 컨트롤의 기본 기능</span><span class="sxs-lookup"><span data-stu-id="1e45a-143">Default Functionality in the Windows Forms DataGridView Control</span></span>](default-functionality-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1e45a-144">Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리</span><span class="sxs-lookup"><span data-stu-id="1e45a-144">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
