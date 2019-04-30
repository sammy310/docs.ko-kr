---
title: 데이터 보기
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: aff4d6f648fa091130bfd9951f2a5001947b09a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034335"
---
# <a name="dataviews"></a><span data-ttu-id="73b25-102">데이터 보기</span><span class="sxs-lookup"><span data-stu-id="73b25-102">DataViews</span></span>
<span data-ttu-id="73b25-103"><xref:System.Data.DataView>는 데이터 바인딩 응용 프로그램에서 자주 사용되는 기능으로, 이 기능을 사용하면 <xref:System.Data.DataTable>에 저장되어 있는 데이터에 대해 서로 다른 뷰를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-103">A <xref:System.Data.DataView> enables you to create different views of the data stored in a <xref:System.Data.DataTable>, a capability that is often used in data-binding applications.</span></span> <span data-ttu-id="73b25-104">사용 하는 **DataView**, 서로 다른 정렬 순서를 사용 하 여 테이블의 데이터를 노출 시킬 수 있으며 행 상태 또는 필터 식을 기반으로 데이터를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-104">Using a **DataView**, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span>  
  
 <span data-ttu-id="73b25-105">A **DataView** 데이터 원본에 대 한 동적 뷰를 제공 **DataTable**: 콘텐츠, 순서 및 멤버 발생 하는 변경 내용을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-105">A **DataView** provides a dynamic view of data in the underlying **DataTable**: the content, ordering, and membership reflect changes as they occur.</span></span> <span data-ttu-id="73b25-106">다르게이 동작 합니다 **선택** 메서드의 **DataTable**를 반환 하는 <xref:System.Data.DataRow> 특정 필터 및/또는 정렬 순서를 기준으로 테이블에서 배열:이 콘텐츠는 변경 내용을 반영를 기본 테이블, 하지만 해당 멤버 및 순서 정적으로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-106">This behavior differs from the **Select** method of the **DataTable**, which returns a <xref:System.Data.DataRow> array from a table based on a particular filter and/or sort order: this content reflects changes to the underlying table, but its membership and ordering remain static.</span></span> <span data-ttu-id="73b25-107">동적 기능은 합니다 **DataView** 데이터 바인딩 응용 프로그램에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-107">The dynamic capabilities of the **DataView** make it ideal for data-binding applications.</span></span>  
  
 <span data-ttu-id="73b25-108">A **DataView** 다른 정렬 및 필터링 기준을 적용할 수 있는 데이터베이스 뷰와 마찬가지로 데이터의 단일 집합의 동적 뷰를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-108">A **DataView** provides you with a dynamic view of a single set of data, much like a database view, to which you can apply different sorting and filtering criteria.</span></span> <span data-ttu-id="73b25-109">그러나 데이터베이스 뷰와 달리를 **DataView** 테이블로 처리할 수 없습니다 및 조인 된 테이블의 뷰를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-109">Unlike a database view, however, a **DataView** cannot be treated as a table and cannot provide a view of joined tables.</span></span> <span data-ttu-id="73b25-110">또한 소스 테이블에 있는 열을 제외하거나 계산을 통해 만들어지는 열과 같이 소스 테이블에 없는 열을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-110">You also cannot exclude columns that exist in the source table, nor can you append columns, such as computational columns, that do not exist in the source table.</span></span>  
  
 <span data-ttu-id="73b25-111">사용할 수는 <xref:System.Data.DataView.DataViewManager%2A> 에 있는 모든 테이블에 대 한 뷰 설정을 관리할 수는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-111">You can use a <xref:System.Data.DataView.DataViewManager%2A> to manage view settings for all the tables in a **DataSet**.</span></span> <span data-ttu-id="73b25-112">합니다 **DataViewManager** 각 테이블에 대 한 기본 뷰 설정을 관리할 수 있는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-112">The **DataViewManager** provides you with a convenient way to manage default view settings for each table.</span></span> <span data-ttu-id="73b25-113">컨트롤의 둘 이상의 테이블을 바인딩하는 경우는 **데이터 집합**바인딩하는 **DataViewManager** 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-113">When binding a control to more than one table of a **DataSet**, binding to a **DataViewManager** is the ideal choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73b25-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="73b25-114">In This Section</span></span>  
 [<span data-ttu-id="73b25-115">DataView 만들기</span><span class="sxs-lookup"><span data-stu-id="73b25-115">Creating a DataView</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 <span data-ttu-id="73b25-116">만드는 방법을 설명 합니다는 **DataView** 에 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-116">Describes how to create a **DataView** for a **DataTable**.</span></span>  
  
 [<span data-ttu-id="73b25-117">데이터 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="73b25-117">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 <span data-ttu-id="73b25-118">속성을 설정 하는 방법에 설명 된 **DataView** 특정 필터 조건에 맞는 데이터 행의 하위 집합을 반환 하거나 특정 정렬 순서로 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-118">Describes how to set the properties of a **DataView** to return subsets of data rows meeting specific filter criteria, or to return data in a particular sort order.</span></span>  
  
 [<span data-ttu-id="73b25-119">DataRow 및 DataRowView</span><span class="sxs-lookup"><span data-stu-id="73b25-119">DataRows and DataRowViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 <span data-ttu-id="73b25-120">제공 하는 데이터에 액세스 하는 방법에 설명 합니다 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-120">Describes how to access the data exposed by the **DataView**.</span></span>  
  
 [<span data-ttu-id="73b25-121">행 찾기</span><span class="sxs-lookup"><span data-stu-id="73b25-121">Finding Rows</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 <span data-ttu-id="73b25-122">특정 행을 찾는 방법에 설명 된 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-122">Describes how to find a particular row in a **DataView**.</span></span>  
  
 [<span data-ttu-id="73b25-123">ChildView 및 관계</span><span class="sxs-lookup"><span data-stu-id="73b25-123">ChildViews and Relations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 <span data-ttu-id="73b25-124">뷰를 사용 하 여 부모-자식 관계를 만드는 방법에 설명 된 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-124">Describes how to create views of data from a parent-child relationship using a **DataView**.</span></span>  
  
 [<span data-ttu-id="73b25-125">데이터 보기 수정</span><span class="sxs-lookup"><span data-stu-id="73b25-125">Modifying DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 <span data-ttu-id="73b25-126">기본 데이터를 수정 하는 방법에 설명 **DataTable** 를 통해 합니다 **DataView**업데이트 활성화 또는 비활성화 등입니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-126">Describes how to modify the data in the underlying **DataTable** via the **DataView**, including enabling or disabling updates.</span></span>  
  
 [<span data-ttu-id="73b25-127">DataView 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="73b25-127">Handling DataView Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 <span data-ttu-id="73b25-128">사용 하는 방법에 설명 합니다 **ListChanged** 이벤트 알림을 받을 수 때 내용 또는 순서가의 **DataView** 업데이트 하는.</span><span class="sxs-lookup"><span data-stu-id="73b25-128">Describes how to use the **ListChanged** event to receive notification when the contents or order of a **DataView** is being updated.</span></span>  
  
 [<span data-ttu-id="73b25-129">데이터 보기 관리</span><span class="sxs-lookup"><span data-stu-id="73b25-129">Managing DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 <span data-ttu-id="73b25-130">사용 하는 방법에 설명 합니다는 **DataViewManager** 관리 하 **DataView** 의 각 테이블에 대 한 설정을 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-130">Describes how to use a **DataViewManager** to manage **DataView** settings for each table in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="73b25-131">관련 단원</span><span class="sxs-lookup"><span data-stu-id="73b25-131">Related Sections</span></span>  
 <span data-ttu-id="73b25-132">[ASP.NET 웹 응용 프로그램](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="73b25-132">[ASP.NET Web Applications](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))</span></span>  
 <span data-ttu-id="73b25-133">ASP.NET 응용 프로그램, Web Forms 및 Web Services를 만들기 위한 개요 및 자세한 단계별 절차를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-133">Provides overviews and detailed, step-by-step procedures for creating ASP.NET applications, Web Forms, and Web Services.</span></span>  
  
 <span data-ttu-id="73b25-134">[Windows 응용 프로그램](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="73b25-134">[Windows Applications](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))</span></span>  
 <span data-ttu-id="73b25-135">Windows Forms 및 콘솔 응용 프로그램 작업에 대한 자세한 내용을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-135">Provides detailed information about working with Windows Forms and console applications.</span></span>  
  
 [<span data-ttu-id="73b25-136">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="73b25-136">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="73b25-137">에 대해 설명 합니다 **데이터 집합** 개체 및 사용 하 여 응용 프로그램 데이터를 관리 하는 방법을 합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-137">Describes the **DataSet** object and how you can use it to manage application data.</span></span>  
  
 [<span data-ttu-id="73b25-138">DataTable</span><span class="sxs-lookup"><span data-stu-id="73b25-138">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="73b25-139">에 대해 설명 합니다 **DataTable** 개체와 사용 하 여 자체적으로 또는의 일부로 응용 프로그램 데이터를 관리 하는 방법을 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-139">Describes the **DataTable** object and how you can use it to manage application data by itself or as part of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="73b25-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="73b25-140">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="73b25-141">ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, ADO.NET을 사용하여 기존 데이터 소스에 액세스하고 응용 프로그램 데이터를 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73b25-141">Describes the ADO.NET architecture and components, and how to use ADO.NET to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b25-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="73b25-142">See also</span></span>

- [<span data-ttu-id="73b25-143">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="73b25-143">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
