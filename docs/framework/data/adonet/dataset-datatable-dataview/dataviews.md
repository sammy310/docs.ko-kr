---
title: 데이터 보기
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: 1b202af052c05ed9dc671fa20c9c366f280ec5c7
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774158"
---
# <a name="dataviews"></a><span data-ttu-id="908f4-102">데이터 보기</span><span class="sxs-lookup"><span data-stu-id="908f4-102">DataViews</span></span>
<span data-ttu-id="908f4-103"><xref:System.Data.DataView>는 데이터 바인딩 애플리케이션에서 자주 사용되는 기능으로, 이 기능을 사용하면 <xref:System.Data.DataTable>에 저장되어 있는 데이터에 대해 서로 다른 뷰를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-103">A <xref:System.Data.DataView> enables you to create different views of the data stored in a <xref:System.Data.DataTable>, a capability that is often used in data-binding applications.</span></span> <span data-ttu-id="908f4-104">**DataView**를 사용 하 여 테이블의 데이터를 여러 정렬 순서로 노출 시킬 수 있으며 행 상태별 또는 필터 식을 기준으로 데이터를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-104">Using a **DataView**, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span>

 <span data-ttu-id="908f4-105">**DataView** 는 원본 **DataTable**의 데이터에 대 한 동적 뷰를 제공 합니다. 내용, 순서 및 멤버 자격은 변경 내용이 발생 하면이를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-105">A **DataView** provides a dynamic view of data in the underlying **DataTable**: the content, ordering, and membership reflect changes as they occur.</span></span> <span data-ttu-id="908f4-106">이 동작은 특정 필터 및/또는 정렬 순서에 따라 테이블에서 <xref:System.Data.DataRow> 배열을 반환 하는 **DataTable**의 **Select** 메서드와는 다릅니다 .이 콘텐츠는 기본 테이블에 대 한 변경 내용을 반영 하지만 해당 멤버 자격 및 순서 지정을 반영 합니다. 정적 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-106">This behavior differs from the **Select** method of the **DataTable**, which returns a <xref:System.Data.DataRow> array from a table based on a particular filter and/or sort order: this content reflects changes to the underlying table, but its membership and ordering remain static.</span></span> <span data-ttu-id="908f4-107">**DataView** 의 동적 기능을 통해 데이터 바인딩 응용 프로그램에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-107">The dynamic capabilities of the **DataView** make it ideal for data-binding applications.</span></span>

 <span data-ttu-id="908f4-108">**DataView** 는 데이터베이스 뷰와 매우 유사 하 게 단일 데이터 집합에 대 한 동적 뷰를 제공 하 여 다양 한 정렬 및 필터링 기준을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-108">A **DataView** provides you with a dynamic view of a single set of data, much like a database view, to which you can apply different sorting and filtering criteria.</span></span> <span data-ttu-id="908f4-109">그러나 데이터베이스 뷰와 달리 **DataView** 는 테이블로 처리 될 수 없으며 조인 된 테이블에 대 한 뷰를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-109">Unlike a database view, however, a **DataView** cannot be treated as a table and cannot provide a view of joined tables.</span></span> <span data-ttu-id="908f4-110">또한 원본 테이블에 존재 하는 열을 제외 하거나 계산 열과 같이 원본 테이블에 없는 열을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-110">You also cannot exclude columns that exist in the source table or append columns that do not exist in the source table, such as computational columns.</span></span>

 <span data-ttu-id="908f4-111">@No__t_0를 사용 하 여 **데이터 집합**의 모든 테이블에 대 한 뷰 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-111">You can use a <xref:System.Data.DataView.DataViewManager%2A> to manage view settings for all the tables in a **DataSet**.</span></span> <span data-ttu-id="908f4-112">**DataViewManager** 에서는 각 테이블에 대 한 기본 뷰 설정을 편리 하 게 관리할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-112">The **DataViewManager** provides you with a convenient way to manage default view settings for each table.</span></span> <span data-ttu-id="908f4-113">컨트롤을 **데이터 집합**의 둘 이상의 테이블에 바인딩하는 경우 **DataViewManager** 에 대 한 바인딩이 이상적인 선택입니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-113">When binding a control to more than one table of a **DataSet**, binding to a **DataViewManager** is the ideal choice.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="908f4-114">단원 내용</span><span class="sxs-lookup"><span data-stu-id="908f4-114">In This Section</span></span>
 <span data-ttu-id="908f4-115">[DataView 만들기](creating-a-dataview.md) **DataTable**에 대해 **DataView** 를 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-115">[Creating a DataView](creating-a-dataview.md) Describes how to create a **DataView** for a **DataTable**.</span></span>

 <span data-ttu-id="908f4-116">[데이터 정렬 및 필터링](sorting-and-filtering-data.md) 특정 필터 조건을 충족 하는 데이터 행의 하위 집합을 반환 하거나 특정 정렬 순서로 데이터를 반환 하도록 **DataView** 의 속성을 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-116">[Sorting and Filtering Data](sorting-and-filtering-data.md) Describes how to set the properties of a **DataView** to return subsets of data rows meeting specific filter criteria, or to return data in a particular sort order.</span></span>

 <span data-ttu-id="908f4-117">[Datarow 및 datarowview](datarows-and-datarowviews.md) **DataView**에서 노출 하는 데이터에 액세스 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-117">[DataRows and DataRowViews](datarows-and-datarowviews.md) Describes how to access the data exposed by the **DataView**.</span></span>

 <span data-ttu-id="908f4-118">[행 찾기](finding-rows.md) **DataView**에서 특정 행을 찾는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-118">[Finding Rows](finding-rows.md) Describes how to find a particular row in a **DataView**.</span></span>

 <span data-ttu-id="908f4-119">[Childviews 및 관계](childviews-and-relations.md) **DataView**를 사용 하 여 부모-자식 관계에서 데이터 뷰를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-119">[ChildViews and Relations](childviews-and-relations.md) Describes how to create views of data from a parent-child relationship using a **DataView**.</span></span>

 <span data-ttu-id="908f4-120">[DataViews 수정](modifying-dataviews.md) 업데이트를 사용 하거나 사용 하지 않도록 설정 하는 등 **DataView**를 통해 기본 **DataTable** 의 데이터를 수정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-120">[Modifying DataViews](modifying-dataviews.md) Describes how to modify the data in the underlying **DataTable** via the **DataView**, including enabling or disabling updates.</span></span>

 <span data-ttu-id="908f4-121">[DataView 이벤트 처리](handling-dataview-events.md) **ListChanged** 이벤트를 사용 하 여 **DataView** 의 내용 또는 순서가 업데이트 될 때 알림을 받는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-121">[Handling DataView Events](handling-dataview-events.md) Describes how to use the **ListChanged** event to receive notification when the contents or order of a **DataView** is being updated.</span></span>

 <span data-ttu-id="908f4-122">[DataViews 관리](managing-dataviews.md) **DataViewManager** 를 사용 하 여 **데이터 집합**의 각 테이블에 대 한 **DataView** 설정을 관리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-122">[Managing DataViews](managing-dataviews.md) Describes how to use a **DataViewManager** to manage **DataView** settings for each table in a **DataSet**.</span></span>

## <a name="related-sections"></a><span data-ttu-id="908f4-123">관련 단원</span><span class="sxs-lookup"><span data-stu-id="908f4-123">Related Sections</span></span>
 <span data-ttu-id="908f4-124">[ASP.NET 웹 응용 프로그램](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100)) ASP.NET 응용 프로그램, Web Forms 및 웹 서비스를 만들기 위한 개요 및 자세한 단계별 절차를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-124">[ASP.NET Web Applications](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100)) Provides overviews and detailed, step-by-step procedures for creating ASP.NET applications, Web Forms, and Web Services.</span></span>

 <span data-ttu-id="908f4-125">[Windows 응용 프로그램](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100)) Windows Forms 및 콘솔 응용 프로그램 작업에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-125">[Windows Applications](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100)) Provides detailed information about working with Windows Forms and console applications.</span></span>

 <span data-ttu-id="908f4-126">[Dataset, datatable 및 DataViews](index.md) **DataSet** 개체와이 개체를 사용 하 여 응용 프로그램 데이터를 관리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-126">[DataSets, DataTables, and DataViews](index.md) Describes the **DataSet** object and how you can use it to manage application data.</span></span>

 <span data-ttu-id="908f4-127">[Datatable](datatables.md) **DataTable** 개체와이 개체를 사용 하 여 자체적으로 또는 **데이터 집합**의 일부로 응용 프로그램 데이터를 관리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-127">[DataTables](datatables.md) Describes the **DataTable** object and how you can use it to manage application data by itself or as part of a **DataSet**.</span></span>

 <span data-ttu-id="908f4-128">[ADO.NET](../index.md) ADO.NET 아키텍처 및 구성 요소와 ADO.NET를 사용 하 여 기존 데이터 원본에 액세스 하 고 응용 프로그램 데이터를 관리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f4-128">[ADO.NET](../index.md) Describes the ADO.NET architecture and components, and how to use ADO.NET to access existing data sources and manage application data.</span></span>

## <a name="see-also"></a><span data-ttu-id="908f4-129">참조</span><span class="sxs-lookup"><span data-stu-id="908f4-129">See also</span></span>

- [<span data-ttu-id="908f4-130">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="908f4-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
