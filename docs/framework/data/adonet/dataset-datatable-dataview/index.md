---
title: DataSets, DataTables 및 DataViews
description: 일관 된 관계형 프로그래밍 모델을 제공 하는 데이터의 메모리 상주 ADO.NET 데이터 집합을 사용 하는 여러 가지 방법을 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: f6562452261cbc1f7ee36fb264b858646a42e4f5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286897"
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="00b1b-103">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="00b1b-103">DataSets, DataTables, and DataViews</span></span>
<span data-ttu-id="00b1b-104">ADO.NET <xref:System.Data.DataSet>은 포함된 데이터 소스에 관계없이 일관성 있는 관계형 프로그래밍 모델을 제공하는 데이터의 메모리 상주 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-104">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="00b1b-105"><xref:System.Data.DataSet>은 데이터를 포함하고 제약하며 데이터의 순서를 지정하는 테이블과 각 테이블 간의 관계를 포함하는 데이터의 완전한 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-105">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
 <span data-ttu-id="00b1b-106"><xref:System.Data.DataSet>을 사용하는 방법은 여러 가지가 있으며, 각 방법은 독립적으로 또는 조합하여 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-106">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="00b1b-107">다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-107">You can:</span></span>  
  
- <span data-ttu-id="00b1b-108"><xref:System.Data.DataTable> 내에 프로그래밍 방식으로 <xref:System.Data.DataRelation>, <xref:System.Data.Constraint> 및 <xref:System.Data.DataSet>를 만들고 각 테이블을 데이터로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-108">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
- <span data-ttu-id="00b1b-109"><xref:System.Data.DataSet>를 사용하여 기존 관계형 데이터 소스의 데이터 테이블로 `DataAdapter`을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-109">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
- <span data-ttu-id="00b1b-110">XML을 사용하여 <xref:System.Data.DataSet> 내용을 로드하고 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-110">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="00b1b-111">자세한 내용은 [데이터 세트에서 XML 사용](using-xml-in-a-dataset.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00b1b-111">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
 <span data-ttu-id="00b1b-112">또한 XML Web services를 사용하여 강력한 형식의 <xref:System.Data.DataSet>을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-112">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="00b1b-113"><xref:System.Data.DataSet>의 디자인은 XML Web services를 사용하는 데이터 전송에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-113">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="00b1b-114">XML Web services에 대한 개요는 [XML Web services 개요](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00b1b-114">For an overview of XML Web services, see [XML Web Services Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span></span> <span data-ttu-id="00b1b-115">XML Web services에서 <xref:System.Data.DataSet>를 사용하는 예제는 [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md)(XML Web services에서 데이터 세트 사용)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00b1b-115">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="00b1b-116">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="00b1b-116">In This Section</span></span>  
 [<span data-ttu-id="00b1b-117">데이터 세트 만들기</span><span class="sxs-lookup"><span data-stu-id="00b1b-117">Creating a DataSet</span></span>](creating-a-dataset.md)  
 <span data-ttu-id="00b1b-118"><xref:System.Data.DataSet>의 인스턴스를 만들기 위한 구문에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-118">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="00b1b-119">데이터 세트에 DataTable 추가</span><span class="sxs-lookup"><span data-stu-id="00b1b-119">Adding a DataTable to a DataSet</span></span>](adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="00b1b-120">테이블과 열을 만들어 <xref:System.Data.DataSet>에 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-120">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="00b1b-121">DataRelation 추가</span><span class="sxs-lookup"><span data-stu-id="00b1b-121">Adding DataRelations</span></span>](adding-datarelations.md)  
 <span data-ttu-id="00b1b-122"><xref:System.Data.DataSet>에 있는 테이블 사이의 관계를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-122">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="00b1b-123">DataRelation 탐색</span><span class="sxs-lookup"><span data-stu-id="00b1b-123">Navigating DataRelations</span></span>](navigating-datarelations.md)  
 <span data-ttu-id="00b1b-124"><xref:System.Data.DataSet>에 있는 테이블 사이의 관계를 사용하여 부모-자식 관계의 자식 또는 부모 행을 반환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-124">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="00b1b-125">DataSet 콘텐츠 병합</span><span class="sxs-lookup"><span data-stu-id="00b1b-125">Merging DataSet Contents</span></span>](merging-dataset-contents.md)  
 <span data-ttu-id="00b1b-126">하나의 <xref:System.Data.DataSet>, <xref:System.Data.DataTable> 또는 <xref:System.Data.DataRow> 배열의 내용을 다른 <xref:System.Data.DataSet>으로 병합하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-126">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="00b1b-127">데이터 세트 콘텐츠 복사</span><span class="sxs-lookup"><span data-stu-id="00b1b-127">Copying DataSet Contents</span></span>](copying-dataset-contents.md)  
 <span data-ttu-id="00b1b-128">스키마 및 지정한 데이터를 포함하는 <xref:System.Data.DataSet>의 복사본을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-128">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="00b1b-129">데이터 세트 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="00b1b-129">Handling DataSet Events</span></span>](handling-dataset-events.md)  
 <span data-ttu-id="00b1b-130"><xref:System.Data.DataSet>의 이벤트와 해당 이벤트를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-130">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="00b1b-131">형식화된 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="00b1b-131">Typed DataSets</span></span>](typed-datasets.md)  
 <span data-ttu-id="00b1b-132">형식화된 <xref:System.Data.DataSet>의 정의와 이를 만들어 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-132">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="00b1b-133">DataTables</span><span class="sxs-lookup"><span data-stu-id="00b1b-133">DataTables</span></span>](datatables.md)  
 <span data-ttu-id="00b1b-134"><xref:System.Data.DataTable>을 만들고 스키마를 정의하며 데이터를 조작하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-134">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="00b1b-135">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="00b1b-135">DataTableReaders</span></span>](datatablereaders.md)  
 <span data-ttu-id="00b1b-136"><xref:System.Data.DataTableReader>를 만들고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-136">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="00b1b-137">데이터 보기</span><span class="sxs-lookup"><span data-stu-id="00b1b-137">DataViews</span></span>](dataviews.md)  
 <span data-ttu-id="00b1b-138">`DataViews`를 만들고 작업하는 방법과 <xref:System.Data.DataView> 이벤트를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-138">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="00b1b-139">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="00b1b-139">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="00b1b-140"><xref:System.Data.DataSet>의 내용을 로드하여 XML 데이터로 유지하는 것을 포함하여 <xref:System.Data.DataSet>이 데이터 소스로서 XML과 상호 작용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-140">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="00b1b-141">XML Web Service에서 데이터 세트 사용</span><span class="sxs-lookup"><span data-stu-id="00b1b-141">Consuming a DataSet from an XML Web Service</span></span>](consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="00b1b-142"><xref:System.Data.DataSet>을 사용하여 데이터를 전송하는 XML Web services를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-142">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="00b1b-143">관련 단원</span><span class="sxs-lookup"><span data-stu-id="00b1b-143">Related Sections</span></span>  
 [<span data-ttu-id="00b1b-144">ADO.NET의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="00b1b-144">What's New in ADO.NET</span></span>](../whats-new.md)  
 <span data-ttu-id="00b1b-145">ADO.NET에 새로 추가된 기능을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-145">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="00b1b-146">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="00b1b-146">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="00b1b-147">ADO.NET의 디자인 및 구성 요소에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-147">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="00b1b-148">DataAdapter에서 DataSet 채우기</span><span class="sxs-lookup"><span data-stu-id="00b1b-148">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="00b1b-149">데이터 원본의 데이터가 있는 **데이터 세트**를 로드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-149">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="00b1b-150">DataAdapters로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="00b1b-150">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="00b1b-151">**데이터 세트**의 데이터에 대한 변경 사항을 다시 데이터 원본에 적용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-151">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="00b1b-152">데이터 세트에 기존 제약 조건 추가</span><span class="sxs-lookup"><span data-stu-id="00b1b-152">Adding Existing Constraints to a DataSet</span></span>](../adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="00b1b-153">데이터 원본의 기본 키 정보로 **데이터 세트**를 채우는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00b1b-153">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b1b-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00b1b-154">See also</span></span>

- [<span data-ttu-id="00b1b-155">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="00b1b-155">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="00b1b-156">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="00b1b-156">ADO.NET Overview</span></span>](../ado-net-overview.md)
