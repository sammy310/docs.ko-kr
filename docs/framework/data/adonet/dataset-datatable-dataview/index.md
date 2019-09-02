---
title: DataSets, DataTables 및 DataViews
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: 4b5e81f415685d6ee3529c7e4f9d389e8017427e
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203640"
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="72051-102">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="72051-102">DataSets, DataTables, and DataViews</span></span>
<span data-ttu-id="72051-103">ADO.NET <xref:System.Data.DataSet>은 포함된 데이터 소스에 관계없이 일관성 있는 관계형 프로그래밍 모델을 제공하는 데이터의 메모리 상주 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="72051-103">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="72051-104"><xref:System.Data.DataSet>은 데이터를 포함하고 제약하며 데이터의 순서를 지정하는 테이블과 각 테이블 간의 관계를 포함하는 데이터의 완전한 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="72051-104">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
 <span data-ttu-id="72051-105"><xref:System.Data.DataSet>을 사용하는 방법은 여러 가지가 있으며, 각 방법은 독립적으로 또는 조합하여 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72051-105">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="72051-106">다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72051-106">You can:</span></span>  
  
- <span data-ttu-id="72051-107"><xref:System.Data.DataTable> 내에 프로그래밍 방식으로 <xref:System.Data.DataRelation>, <xref:System.Data.Constraint> 및 <xref:System.Data.DataSet>를 만들고 각 테이블을 데이터로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="72051-107">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
- <span data-ttu-id="72051-108"><xref:System.Data.DataSet>를 사용하여 기존 관계형 데이터 소스의 데이터 테이블로 `DataAdapter`을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="72051-108">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
- <span data-ttu-id="72051-109">XML을 사용하여 <xref:System.Data.DataSet> 내용을 로드하고 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-109">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="72051-110">자세한 내용은 [데이터 세트에서 XML 사용](using-xml-in-a-dataset.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72051-110">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
 <span data-ttu-id="72051-111">또한 XML Web services를 사용하여 강력한 형식의 <xref:System.Data.DataSet>을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72051-111">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="72051-112"><xref:System.Data.DataSet>의 디자인은 XML Web services를 사용하는 데이터 전송에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-112">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="72051-113">XML Web services에 대한 개요는 [XML Web services 개요](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72051-113">For an overview of XML Web services, see [XML Web Services Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span></span> <span data-ttu-id="72051-114">XML Web services에서 <xref:System.Data.DataSet>를 사용하는 예제는 [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md)(XML Web services에서 데이터 세트 사용)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72051-114">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="72051-115">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="72051-115">In This Section</span></span>  
 [<span data-ttu-id="72051-116">데이터 집합 만들기</span><span class="sxs-lookup"><span data-stu-id="72051-116">Creating a DataSet</span></span>](creating-a-dataset.md)  
 <span data-ttu-id="72051-117"><xref:System.Data.DataSet>의 인스턴스를 만들기 위한 구문에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-117">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="72051-118">데이터 집합에 DataTable 추가</span><span class="sxs-lookup"><span data-stu-id="72051-118">Adding a DataTable to a DataSet</span></span>](adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="72051-119">테이블과 열을 만들어 <xref:System.Data.DataSet>에 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-119">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="72051-120">DataRelation 추가</span><span class="sxs-lookup"><span data-stu-id="72051-120">Adding DataRelations</span></span>](adding-datarelations.md)  
 <span data-ttu-id="72051-121"><xref:System.Data.DataSet>에 있는 테이블 사이의 관계를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-121">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="72051-122">DataRelation 탐색</span><span class="sxs-lookup"><span data-stu-id="72051-122">Navigating DataRelations</span></span>](navigating-datarelations.md)  
 <span data-ttu-id="72051-123"><xref:System.Data.DataSet>에 있는 테이블 사이의 관계를 사용하여 부모-자식 관계의 자식 또는 부모 행을 반환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-123">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="72051-124">데이터 집합 콘텐츠 병합</span><span class="sxs-lookup"><span data-stu-id="72051-124">Merging DataSet Contents</span></span>](merging-dataset-contents.md)  
 <span data-ttu-id="72051-125">하나의 <xref:System.Data.DataSet>, <xref:System.Data.DataTable> 또는 <xref:System.Data.DataRow> 배열의 내용을 다른 <xref:System.Data.DataSet>으로 병합하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-125">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="72051-126">데이터 집합 콘텐츠 복사</span><span class="sxs-lookup"><span data-stu-id="72051-126">Copying DataSet Contents</span></span>](copying-dataset-contents.md)  
 <span data-ttu-id="72051-127">스키마 및 지정한 데이터를 포함하는 <xref:System.Data.DataSet>의 복사본을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-127">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="72051-128">데이터 집합 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="72051-128">Handling DataSet Events</span></span>](handling-dataset-events.md)  
 <span data-ttu-id="72051-129"><xref:System.Data.DataSet>의 이벤트와 해당 이벤트를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-129">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="72051-130">형식화된 데이터 집합</span><span class="sxs-lookup"><span data-stu-id="72051-130">Typed DataSets</span></span>](typed-datasets.md)  
 <span data-ttu-id="72051-131">형식화된 <xref:System.Data.DataSet>의 정의와 이를 만들어 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-131">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="72051-132">DataTable</span><span class="sxs-lookup"><span data-stu-id="72051-132">DataTables</span></span>](datatables.md)  
 <span data-ttu-id="72051-133"><xref:System.Data.DataTable>을 만들고 스키마를 정의하며 데이터를 조작하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-133">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="72051-134">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="72051-134">DataTableReaders</span></span>](datatablereaders.md)  
 <span data-ttu-id="72051-135"><xref:System.Data.DataTableReader>를 만들고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-135">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="72051-136">DataView</span><span class="sxs-lookup"><span data-stu-id="72051-136">DataViews</span></span>](dataviews.md)  
 <span data-ttu-id="72051-137">`DataViews`를 만들고 작업하는 방법과 <xref:System.Data.DataView> 이벤트를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-137">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="72051-138">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="72051-138">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="72051-139"><xref:System.Data.DataSet>의 내용을 로드하여 XML 데이터로 유지하는 것을 포함하여 <xref:System.Data.DataSet>이 데이터 소스로서 XML과 상호 작용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-139">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="72051-140">XML Web services에서 데이터 집합 사용</span><span class="sxs-lookup"><span data-stu-id="72051-140">Consuming a DataSet from an XML Web Service</span></span>](consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="72051-141"><xref:System.Data.DataSet>을 사용하여 데이터를 전송하는 XML Web services를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-141">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="72051-142">관련 단원</span><span class="sxs-lookup"><span data-stu-id="72051-142">Related Sections</span></span>  
 [<span data-ttu-id="72051-143">ADO.NET의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="72051-143">What's New in ADO.NET</span></span>](../whats-new.md)  
 <span data-ttu-id="72051-144">ADO.NET에 새로 추가된 기능을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-144">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="72051-145">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="72051-145">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="72051-146">ADO.NET의 디자인 및 구성 요소에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-146">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="72051-147">DataAdapter에서 데이터 집합 채우기</span><span class="sxs-lookup"><span data-stu-id="72051-147">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="72051-148">데이터 원본의 데이터가 있는 **데이터 세트**를 로드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-148">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="72051-149">DataAdapter로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="72051-149">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="72051-150">**데이터 집합**의 데이터에 대한 변경 사항을 다시 데이터 원본에 적용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-150">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="72051-151">데이터 세트에 기존 제약 조건 추가</span><span class="sxs-lookup"><span data-stu-id="72051-151">Adding Existing Constraints to a DataSet</span></span>](../adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="72051-152">데이터 원본의 기본 키 정보로 **데이터 세트**를 채우는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72051-152">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72051-153">참고자료</span><span class="sxs-lookup"><span data-stu-id="72051-153">See also</span></span>

- [<span data-ttu-id="72051-154">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="72051-154">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="72051-155">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="72051-155">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
