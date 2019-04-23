---
title: DataAdapters 및 DataReaders
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: af1d44b1e320557ab7906ce65dbeb5415b5c09dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189692"
---
# <a name="dataadapters-and-datareaders"></a><span data-ttu-id="45b9f-102">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="45b9f-102">DataAdapters and DataReaders</span></span>
<span data-ttu-id="45b9f-103">ADO.NET을 사용할 수 있습니다 **DataReader** 데이터베이스에서 데이터를 읽기 전용, 정방향 전용 스트림을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-103">You can use the ADO.NET **DataReader** to retrieve a read-only, forward-only stream of data from a database.</span></span> <span data-ttu-id="45b9f-104">쿼리가 실행 되 고 해당 작업을 요청할 때까지 클라이언트의 네트워크 버퍼에 저장 된 대로 결과가 반환 됩니다 사용 하 여는 **읽기** 메서드는 **DataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-104">Results are returned as the query executes, and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader**.</span></span> <span data-ttu-id="45b9f-105">사용 하는 **DataReader** (기본적으로) 및 사용 가능한 즉시 데이터를 검색 하 여 응용 프로그램 성능을 향상 시킬 수 시스템 오버 헤드를 줄임으로써 메모리에서 한 번에 하나의 행을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-105">Using the **DataReader** can increase application performance both by retrieving data as soon as it is available, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="45b9f-106"><xref:System.Data.Common.DataAdapter>는 데이터 소스에서 데이터를 검색하고 <xref:System.Data.DataSet> 내의 테이블을 채우는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-106">A <xref:System.Data.Common.DataAdapter> is used to retrieve data from a data source and populate tables within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="45b9f-107">`DataAdapter`는 `DataSet`의 변경 내용을 다시 데이터 소스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-107">The `DataAdapter` also resolves changes made to the `DataSet` back to the data source.</span></span> <span data-ttu-id="45b9f-108">`DataAdapter`는 .NET Framework 데이터 공급자의 `Connection` 개체를 사용하여 데이터 소스에 연결하며 `Command` 개체를 사용하여 데이터 소스에서 데이터를 검색하고 변경 내용을 데이터 소스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-108">The `DataAdapter` uses the `Connection` object of the .NET Framework data provider to connect to a data source, and it uses `Command` objects to retrieve data from and resolve changes to the data source.</span></span>  
  
 <span data-ttu-id="45b9f-109">.NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbDataReader> 및 <xref:System.Data.Common.DbDataAdapter> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbDataReader> 및 <xref:System.Data.OleDb.OleDbDataAdapter> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlDataReader> 및 <xref:System.Data.SqlClient.SqlDataAdapter> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcDataReader> 및 <xref:System.Data.Odbc.OdbcDataAdapter> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleDataReader> 및 <xref:System.Data.OracleClient.OracleDataAdapter> 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-109">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbDataReader> and a <xref:System.Data.Common.DbDataAdapter> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbDataReader> and an <xref:System.Data.OleDb.OleDbDataAdapter> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlDataReader> and a <xref:System.Data.SqlClient.SqlDataAdapter> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcDataReader> and an <xref:System.Data.Odbc.OdbcDataAdapter> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleDataReader> and an <xref:System.Data.OracleClient.OracleDataAdapter> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45b9f-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="45b9f-110">In This Section</span></span>  
 [<span data-ttu-id="45b9f-111">DataReader를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="45b9f-111">Retrieving Data Using a DataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 <span data-ttu-id="45b9f-112">ADO.NET에 설명 합니다 **DataReader** 개체 및 사용 데이터 소스에서 결과 스트림을 반환 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-112">Describes the ADO.NET **DataReader** object and how to use it to return a stream of results from a data source.</span></span>  
  
 [<span data-ttu-id="45b9f-113">DataAdapter에서 데이터 집합 채우기</span><span class="sxs-lookup"><span data-stu-id="45b9f-113">Populating a DataSet from a DataAdapter</span></span>](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="45b9f-114">`DataSet`를 사용하여 테이블, 열 및 행으로 `DataAdapter`을 채우는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-114">Describes how to fill a `DataSet` with tables, columns, and rows by using a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="45b9f-115">DataAdapter 매개 변수</span><span class="sxs-lookup"><span data-stu-id="45b9f-115">DataAdapter Parameters</span></span>](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 <span data-ttu-id="45b9f-116">`DataAdapter`의 열 내용을 명령 매개 변수에 매핑하는 방법을 비롯하여 `DataSet`의 명령 속성에 매개 변수를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-116">Describes how to use parameters with the command properties of a `DataAdapter` including how to map the contents of a column in a `DataSet` to a command parameter.</span></span>  
  
 [<span data-ttu-id="45b9f-117">데이터 집합에 기존 제약 조건 추가</span><span class="sxs-lookup"><span data-stu-id="45b9f-117">Adding Existing Constraints to a DataSet</span></span>](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="45b9f-118">`DataSet`에 기존 제약 조건을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-118">Describes how to add existing constraints to a `DataSet`.</span></span>  
  
 [<span data-ttu-id="45b9f-119">DataAdapter DataTable 및 DataColumn 매핑</span><span class="sxs-lookup"><span data-stu-id="45b9f-119">DataAdapter DataTable and DataColumn Mappings</span></span>](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 <span data-ttu-id="45b9f-120">`DataTableMappings`에 대해 `ColumnMappings` 및 `DataAdapter`를 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-120">Describes how to set up `DataTableMappings` and `ColumnMappings` for a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="45b9f-121">쿼리 결과를 통해 페이징</span><span class="sxs-lookup"><span data-stu-id="45b9f-121">Paging Through a Query Result</span></span>](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 <span data-ttu-id="45b9f-122">쿼리 결과를 데이터 페이지로 보는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-122">Provides an example of viewing the results of a query as pages of data.</span></span>  
  
 [<span data-ttu-id="45b9f-123">DataAdapter로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="45b9f-123">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="45b9f-124">`DataAdapter`를 사용하여 `DataSet`의 변경 내용을 데이터베이스에 적용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-124">Describes how to use a `DataAdapter` to resolve changes in a `DataSet` back to the database.</span></span>  
  
 [<span data-ttu-id="45b9f-125">DataAdapter 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="45b9f-125">Handling DataAdapter Events</span></span>](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 <span data-ttu-id="45b9f-126">`DataAdapter` 이벤트와 이벤트 사용 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-126">Describes `DataAdapter` events and how to use them.</span></span>  
  
 [<span data-ttu-id="45b9f-127">DataAdapter를 사용하여 일괄 작업 수행</span><span class="sxs-lookup"><span data-stu-id="45b9f-127">Performing Batch Operations Using DataAdapters</span></span>](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 <span data-ttu-id="45b9f-128">`DataSet`의 업데이트를 적용할 때 SQL Server로의 라운드트립 횟수를 줄여 응용 프로그램의 성능을 향상시키는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45b9f-128">Describes enhancing application performance by reducing the number of round trips to SQL Server when applying updates from the `DataSet`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45b9f-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="45b9f-129">See also</span></span>

- [<span data-ttu-id="45b9f-130">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="45b9f-130">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [<span data-ttu-id="45b9f-131">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="45b9f-131">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="45b9f-132">트랜잭션 및 동시성</span><span class="sxs-lookup"><span data-stu-id="45b9f-132">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [<span data-ttu-id="45b9f-133">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="45b9f-133">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="45b9f-134">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="45b9f-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
