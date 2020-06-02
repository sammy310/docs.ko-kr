---
title: DataAdapters 및 DataReaders
description: 데이터베이스에서 데이터를 검색 하는 ADO.NET DataReader와 데이터 원본에서 데이터를 검색 하 고 데이터 집합을 채우는 DataAdapter에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: 17463d65266baa53521bed9603c8abd96923277b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286975"
---
# <a name="dataadapters-and-datareaders"></a><span data-ttu-id="62cb2-103">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="62cb2-103">DataAdapters and DataReaders</span></span>
<span data-ttu-id="62cb2-104">ADO.NET **DataReader** 를 사용 하 여 데이터베이스에서 앞 으로만 이동 가능한 읽기 전용 데이터 스트림을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-104">You can use the ADO.NET **DataReader** to retrieve a read-only, forward-only stream of data from a database.</span></span> <span data-ttu-id="62cb2-105">결과는 쿼리가 실행 될 때 반환 되 고 **DataReader**의 **Read** 메서드를 사용 하 여 요청할 때까지 클라이언트의 네트워크 버퍼에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-105">Results are returned as the query executes, and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader**.</span></span> <span data-ttu-id="62cb2-106">**DataReader** 를 사용 하면 데이터를 사용할 수 있는 즉시 검색 하 고 (기본적으로) 한 번에 한 행만 메모리에 저장 하 여 시스템 오버 헤드를 줄임으로써 응용 프로그램 성능이 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-106">Using the **DataReader** can increase application performance both by retrieving data as soon as it is available, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="62cb2-107"><xref:System.Data.Common.DataAdapter>는 데이터 소스에서 데이터를 검색하고 <xref:System.Data.DataSet> 내의 테이블을 채우는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-107">A <xref:System.Data.Common.DataAdapter> is used to retrieve data from a data source and populate tables within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="62cb2-108">`DataAdapter`는 `DataSet`의 변경 내용을 다시 데이터 소스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-108">The `DataAdapter` also resolves changes made to the `DataSet` back to the data source.</span></span> <span data-ttu-id="62cb2-109">`DataAdapter`는 .NET Framework 데이터 공급자의 `Connection` 개체를 사용하여 데이터 소스에 연결하며 `Command` 개체를 사용하여 데이터 소스에서 데이터를 검색하고 변경 내용을 데이터 소스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-109">The `DataAdapter` uses the `Connection` object of the .NET Framework data provider to connect to a data source, and it uses `Command` objects to retrieve data from and resolve changes to the data source.</span></span>  
  
 <span data-ttu-id="62cb2-110">.NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbDataReader> 및 <xref:System.Data.Common.DbDataAdapter> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbDataReader> 및 <xref:System.Data.OleDb.OleDbDataAdapter> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlDataReader> 및 <xref:System.Data.SqlClient.SqlDataAdapter> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcDataReader> 및 <xref:System.Data.Odbc.OdbcDataAdapter> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleDataReader> 및 <xref:System.Data.OracleClient.OracleDataAdapter> 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-110">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbDataReader> and a <xref:System.Data.Common.DbDataAdapter> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbDataReader> and an <xref:System.Data.OleDb.OleDbDataAdapter> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlDataReader> and a <xref:System.Data.SqlClient.SqlDataAdapter> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcDataReader> and an <xref:System.Data.Odbc.OdbcDataAdapter> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleDataReader> and an <xref:System.Data.OracleClient.OracleDataAdapter> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62cb2-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="62cb2-111">In This Section</span></span>  
 [<span data-ttu-id="62cb2-112">DataReader를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="62cb2-112">Retrieving Data Using a DataReader</span></span>](retrieving-data-using-a-datareader.md)  
 <span data-ttu-id="62cb2-113">ADO.NET **DataReader** 개체와이 개체를 사용 하 여 데이터 소스에서 결과 스트림을 반환 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-113">Describes the ADO.NET **DataReader** object and how to use it to return a stream of results from a data source.</span></span>  
  
 [<span data-ttu-id="62cb2-114">DataAdapter에서 DataSet 채우기</span><span class="sxs-lookup"><span data-stu-id="62cb2-114">Populating a DataSet from a DataAdapter</span></span>](populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="62cb2-115">`DataSet`를 사용하여 테이블, 열 및 행으로 `DataAdapter`을 채우는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-115">Describes how to fill a `DataSet` with tables, columns, and rows by using a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="62cb2-116">DataAdapter 매개 변수</span><span class="sxs-lookup"><span data-stu-id="62cb2-116">DataAdapter Parameters</span></span>](dataadapter-parameters.md)  
 <span data-ttu-id="62cb2-117">`DataAdapter`의 열 내용을 명령 매개 변수에 매핑하는 방법을 비롯하여 `DataSet`의 명령 속성에 매개 변수를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-117">Describes how to use parameters with the command properties of a `DataAdapter` including how to map the contents of a column in a `DataSet` to a command parameter.</span></span>  
  
 [<span data-ttu-id="62cb2-118">데이터 세트에 기존 제약 조건 추가</span><span class="sxs-lookup"><span data-stu-id="62cb2-118">Adding Existing Constraints to a DataSet</span></span>](adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="62cb2-119">`DataSet`에 기존 제약 조건을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-119">Describes how to add existing constraints to a `DataSet`.</span></span>  
  
 [<span data-ttu-id="62cb2-120">DataAdapter DataTable 및 DataColumn 매핑</span><span class="sxs-lookup"><span data-stu-id="62cb2-120">DataAdapter DataTable and DataColumn Mappings</span></span>](dataadapter-datatable-and-datacolumn-mappings.md)  
 <span data-ttu-id="62cb2-121">`DataTableMappings`에 대해 `ColumnMappings` 및 `DataAdapter`를 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-121">Describes how to set up `DataTableMappings` and `ColumnMappings` for a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="62cb2-122">쿼리 결과를 통해 페이징</span><span class="sxs-lookup"><span data-stu-id="62cb2-122">Paging Through a Query Result</span></span>](paging-through-a-query-result.md)  
 <span data-ttu-id="62cb2-123">쿼리 결과를 데이터 페이지로 보는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-123">Provides an example of viewing the results of a query as pages of data.</span></span>  
  
 [<span data-ttu-id="62cb2-124">DataAdapters로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="62cb2-124">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="62cb2-125">`DataAdapter`를 사용하여 `DataSet`의 변경 내용을 데이터베이스에 적용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-125">Describes how to use a `DataAdapter` to resolve changes in a `DataSet` back to the database.</span></span>  
  
 [<span data-ttu-id="62cb2-126">DataAdapter 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="62cb2-126">Handling DataAdapter Events</span></span>](handling-dataadapter-events.md)  
 <span data-ttu-id="62cb2-127">`DataAdapter` 이벤트와 이벤트 사용 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-127">Describes `DataAdapter` events and how to use them.</span></span>  
  
 [<span data-ttu-id="62cb2-128">DataAdapter를 사용하여 일괄 작업 수행</span><span class="sxs-lookup"><span data-stu-id="62cb2-128">Performing Batch Operations Using DataAdapters</span></span>](performing-batch-operations-using-dataadapters.md)  
 <span data-ttu-id="62cb2-129">`DataSet`의 업데이트를 적용할 때 SQL Server로의 라운드트립 횟수를 줄여 애플리케이션의 성능을 향상시키는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="62cb2-129">Describes enhancing application performance by reducing the number of round trips to SQL Server when applying updates from the `DataSet`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62cb2-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62cb2-130">See also</span></span>

- [<span data-ttu-id="62cb2-131">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="62cb2-131">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="62cb2-132">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="62cb2-132">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="62cb2-133">트랜잭션 및 동시성</span><span class="sxs-lookup"><span data-stu-id="62cb2-133">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="62cb2-134">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="62cb2-134">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="62cb2-135">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="62cb2-135">ADO.NET Overview</span></span>](ado-net-overview.md)
