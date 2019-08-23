---
title: DataTables
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: 369855d1aff854b60c251010ec42557b70c093c0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952658"
---
# <a name="datatables"></a><span data-ttu-id="1b728-102">DataTables</span><span class="sxs-lookup"><span data-stu-id="1b728-102">DataTables</span></span>
<span data-ttu-id="1b728-103"><xref:System.Data.DataSet>은 테이블 컬렉션, 관계 및 제약 조건으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-103">A <xref:System.Data.DataSet> is made up of a collection of tables, relationships, and constraints.</span></span> <span data-ttu-id="1b728-104">ADO.NET <xref:System.Data.DataTable> 에서 개체는 **데이터 집합**의 테이블을 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-104">In ADO.NET, <xref:System.Data.DataTable> objects are used to represent the tables in a **DataSet**.</span></span> <span data-ttu-id="1b728-105">**DataTable** 은 메모리 내 관계형 데이터의 한 테이블을 나타냅니다. 데이터는에 대해 로컬입니다. 이 파일이 상주 하지만 **dataadapter** 를 사용 하 여 Microsoft SQL Server와 같은 데이터 소스에서 채워질 수 있는 NET 기반 응용 프로그램 자세한 내용은 [Dataadapter에서 데이터 집합 채우기](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b728-105">A **DataTable** represents one table of in-memory relational data; the data is local to the .NET-based application in which it resides, but can be populated from a data source such as Microsoft SQL Server using a **DataAdapter** For more information, see [Populating a DataSet from a DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md).</span></span>  
  
 <span data-ttu-id="1b728-106">**DataTable** 클래스는 .NET Framework 클래스 라이브러리 내에서 system.xml 네임 스페이스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-106">The **DataTable** class is a member of the **System.Data** namespace within the .NET Framework class library.</span></span> <span data-ttu-id="1b728-107">**Datatable** 은 독립적으로 만들거나 **데이터 집합**의 멤버로 사용할 수 있으며,를 <xref:System.Data.DataView>비롯 한 다른 .NET Framework 개체와 함께 **datatable** 개체를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-107">You can create and use a **DataTable** independently or as a member of a **DataSet**, and **DataTable** objects can also be used in conjunction with other .NET Framework objects, including the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="1b728-108">Dataset 개체의 **tables** 속성을 통해 **데이터 집합** 의 테이블 컬렉션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-108">You access the collection of tables in a **DataSet** through the **Tables** property of the **DataSet** object.</span></span>  
  
 <span data-ttu-id="1b728-109">테이블의 스키마나 구조는 열이나 제약 조건에 의해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-109">The schema, or structure of a table is represented by columns and constraints.</span></span> <span data-ttu-id="1b728-110"><xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.DataColumn> 개체뿐만아니라개체를사용하여DataTable의스키마를정의<xref:System.Data.UniqueConstraint> 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-110">You define the schema of a **DataTable** using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="1b728-111">테이블 열은 데이터 소스 열에 매핑될 수 있습니다. 또한 이 열은 식에서 계산된 값을 포함하며 값을 자동으로 증가시키고 기본 키 값을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-111">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="1b728-112">스키마 외에도 **DataTable** 에는 데이터를 포함 하 고 주문 하는 행이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-112">In addition to a schema, a **DataTable** must also have rows to contain and order data.</span></span> <span data-ttu-id="1b728-113"><xref:System.Data.DataRow> 클래스는 테이블에 포함된 실제 데이터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-113">The <xref:System.Data.DataRow> class represents the actual data contained in a table.</span></span> <span data-ttu-id="1b728-114">**DataRow** 와 해당 속성 및 메서드를 사용 하 여 테이블의 데이터를 검색, 평가 및 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-114">You use the **DataRow** and its properties and methods to retrieve, evaluate, and manipulate the data in a table.</span></span> <span data-ttu-id="1b728-115">행 내에서 데이터를 액세스 하 고 변경할 때 **DataRow** 개체는 현재 상태와 원래 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-115">As you access and change the data within a row, the **DataRow** object maintains both its current and original state.</span></span>  
  
 <span data-ttu-id="1b728-116">테이블에서 하나 이상의 관련 열을 사용하면 테이블 간에 부모-자식 관계를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-116">You can create parent-child relationships between tables using one or more related columns in the tables.</span></span> <span data-ttu-id="1b728-117">을<xref:System.Data.DataRelation>사용 하 여 **DataTable** 개체 간의 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-117">You create a relationship between **DataTable** objects using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="1b728-118">그런 다음 **DataRelation** 개체를 사용 하 여 특정 행의 관련 자식 또는 부모 행을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-118">**DataRelation** objects can then be used to return the related child or parent rows of a particular row.</span></span> <span data-ttu-id="1b728-119">자세한 내용은 [DataRelations 추가](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b728-119">For more information, see [Adding DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b728-120">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1b728-120">In This Section</span></span>  
 [<span data-ttu-id="1b728-121">DataTable 만들기</span><span class="sxs-lookup"><span data-stu-id="1b728-121">Creating a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 <span data-ttu-id="1b728-122">**DataTable** 을 만들어 **데이터 집합**에 추가 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-122">Explains how to create a **DataTable** and add it to a **DataSet**.</span></span>  
  
 [<span data-ttu-id="1b728-123">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="1b728-123">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 <span data-ttu-id="1b728-124">**DataColumn** 개체 및 제약 조건을 만들고 사용 하는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-124">Provides information about creating and using **DataColumn** objects and constraints.</span></span>  
  
 [<span data-ttu-id="1b728-125">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="1b728-125">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 <span data-ttu-id="1b728-126">테이블에서 데이터를 추가, 수정 및 삭제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-126">Explains how to add, modify, and delete data in a table.</span></span> <span data-ttu-id="1b728-127">**DataTable** 이벤트를 사용 하 여 테이블의 데이터에 대 한 변경 내용을 검사 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-127">Explains how to use **DataTable** events to examine changes to data in the table.</span></span>  
  
 [<span data-ttu-id="1b728-128">DataTable 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="1b728-128">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 <span data-ttu-id="1b728-129">열 값을 수정 하 고 행을 추가 하거나 삭제할 때 이벤트를 비롯 하 여 **DataTable**과 함께 사용할 수 있는 이벤트에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-129">Provides information about the events available for use with a **DataTable**, including events when column values are modified and rows are added or deleted.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1b728-130">관련 단원</span><span class="sxs-lookup"><span data-stu-id="1b728-130">Related Sections</span></span>  
 [<span data-ttu-id="1b728-131">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1b728-131">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="1b728-132">ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, 이를 사용하여 기존 데이터 소스에 액세스하고 애플리케이션 데이터를 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-132">Describes the ADO.NET architecture and components, and how to use them to access existing data sources and manage application data.</span></span>  
  
 [<span data-ttu-id="1b728-133">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="1b728-133">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="1b728-134">테이블 간의 관계를 만드는 방법을 포함 하 여 ADO.NET **데이터 집합** 에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-134">Provides information about the ADO.NET **DataSet** including how to create relationships between tables.</span></span>  
  
 <xref:System.Data.Constraint>  
 <span data-ttu-id="1b728-135">**제약 조건** 개체에 대 한 참조 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-135">Provides reference information about the **Constraint** object.</span></span>  
  
 <xref:System.Data.DataColumn>  
 <span data-ttu-id="1b728-136">**DataColumn** 개체에 대 한 참조 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-136">Provides reference information about the **DataColumn** object.</span></span>  
  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="1b728-137">**DataSet** 개체에 대 한 참조 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-137">Provides reference information about the **DataSet** object.</span></span>  
  
 <xref:System.Data.DataTable>  
 <span data-ttu-id="1b728-138">**DataTable** 개체에 대 한 참조 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-138">Provides reference information about the **DataTable** object.</span></span>  
  
 [<span data-ttu-id="1b728-139">클래스 라이브러리 개요</span><span class="sxs-lookup"><span data-stu-id="1b728-139">Class Library Overview</span></span>](../../../../standard/class-library-overview.md)  
 <span data-ttu-id="1b728-140">**시스템** 네임 스페이스 뿐만 아니라 두 번째 수준 네임 스페이스인 **system.object**를 포함 하 여 .NET Framework 클래스 라이브러리에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b728-140">Provides an overview of the .NET Framework class library, including the **System** namespace as well as its second-level namespace, **System.Data**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b728-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="1b728-141">See also</span></span>

- [<span data-ttu-id="1b728-142">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="1b728-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
