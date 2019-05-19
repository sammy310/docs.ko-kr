---
title: ADO.NET에서 데이터 검색 및 수정
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: a5ac8fbd2a53d2670471c1ef5e59508f582ed944
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881428"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="86a98-102">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="86a98-102">Retrieving and Modifying Data in ADO.NET</span></span>
<span data-ttu-id="86a98-103">데이터베이스 응용 프로그램의 기본 기능은 데이터 소스에 연결하여 포함된 데이터를 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-103">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="86a98-104">ADO.NET의.NET Framework 데이터 공급자를 사용 하 여 데이터 검색 뿐 아니라 명령을 실행할 수 있는 응용 프로그램 및 데이터 원본 간의 다리 역할을 **DataReader** 또는 **DataAdapter** .</span><span class="sxs-lookup"><span data-stu-id="86a98-104">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="86a98-105">모든 데이터베이스 응용 프로그램의 한 가지 핵심 기능은 데이터베이스에 저장된 데이터를 업데이트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-105">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="86a98-106">Ado.net에서 데이터를 업데이트 하는 중 사용 하는 것은 **DataAdapter** 및 <xref:System.Data.DataSet>, 및 **명령** 개체 및이 포함 될 수도 있습니다 트랜잭션을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-106">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="86a98-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="86a98-107">In This Section</span></span>  
 [<span data-ttu-id="86a98-108">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="86a98-108">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 <span data-ttu-id="86a98-109">데이터 소스에 대한 연결을 설정하고 연결 이벤트로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-109">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="86a98-110">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="86a98-110">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 <span data-ttu-id="86a98-111">연결 문자열 키워드, 보안 정보와 이에 대한 저장 및 검색을 비롯하여 다양한 연결 문자열 사용 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-111">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="86a98-112">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="86a98-112">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 <span data-ttu-id="86a98-113">.NET Framework 데이터 공급자의 연결 풀링에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-113">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="86a98-114">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="86a98-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 <span data-ttu-id="86a98-115">명령 및 명령 작성기를 만드는 방법, 매개 변수를 구성하는 방법 및 명령을 실행하여 데이터를 검색하고 수정하는 방법에 대한 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-115">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="86a98-116">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="86a98-116">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 <span data-ttu-id="86a98-117">DataReaders, DataAdapters, 매개 변수, DataAdapter 이벤트 처리 및 배치 작업 수행 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-117">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="86a98-118">트랜잭션 및 동시성</span><span class="sxs-lookup"><span data-stu-id="86a98-118">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 <span data-ttu-id="86a98-119">로컬 트랜잭션, 분산 트랜잭션 및 낙관적 동시성 관련 작업의 수행 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-119">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="86a98-120">ID 또는 일련 번호 값 검색</span><span class="sxs-lookup"><span data-stu-id="86a98-120">Retrieving Identity or Autonumber Values</span></span>](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="86a98-121">에 대 한 생성 된 값에 매핑하는 예제를 제공는 **identity** 또는 SQL Server 테이블의 열을 **일련 번호** 테이블에 삽입된 된 행의 열에는 Microsoft Access 테이블의 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-121">Provides an example of mapping the values generated for an **identity** column in a SQL Server table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="86a98-122">`DataTable`에서의 ID 값 병합에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-122">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="86a98-123">이진 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="86a98-123">Retrieving Binary Data</span></span>](../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 <span data-ttu-id="86a98-124">이진 데이터 또는 대형 데이터 구조를 사용 하 여 검색 하는 방법에 설명 `CommandBehavior`합니다.`SequentialAccess`</span><span class="sxs-lookup"><span data-stu-id="86a98-124">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="86a98-125">기본 동작을 수정 하는 `DataReader`합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-125">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="86a98-126">저장 프로시저로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="86a98-126">Modifying Data with Stored Procedures</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="86a98-127">저장 프로시저 입력 매개 변수와 출력 매개 변수를 사용하여 데이터베이스에 행을 삽입하여 새 ID 값을 반환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-127">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="86a98-128">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="86a98-128">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 <span data-ttu-id="86a98-129">데이터 소스에서 사용 가능한 데이터베이스나 카탈로그, 데이터베이스의 테이블 및 뷰를 비롯하여 테이블에 대한 제약 조건 및 기타 스키마 정보를 가져오는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-129">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="86a98-130">DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="86a98-130">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="86a98-131">공급자 팩터리 모델에 대해 설명하고 `System.Data.Common` 네임스페이스의 기본 클래스를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-131">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="86a98-132">ADO.NET의 데이터 추적</span><span class="sxs-lookup"><span data-stu-id="86a98-132">Data Tracing in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-tracing.md)  
 <span data-ttu-id="86a98-133">ADO.NET에서 기본 제공 데이터 추적 기능을 제공하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-133">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="86a98-134">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="86a98-134">Performance Counters</span></span>](../../../../docs/framework/data/adonet/performance-counters.md)  
 <span data-ttu-id="86a98-135">`SqlClient` 및 `OracleClient`에서 사용할 수 있는 성능 카운터에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-135">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="86a98-136">비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="86a98-136">Asynchronous Programming</span></span>](../../../../docs/framework/data/adonet/asynchronous-programming.md)  
 <span data-ttu-id="86a98-137">비동기 프로그래밍에 대 한 ADO.NET 지원을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-137">Describes ADO.NET support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="86a98-138">SqlClient 스트리밍 지원</span><span class="sxs-lookup"><span data-stu-id="86a98-138">SqlClient Streaming Support</span></span>](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)  
 <span data-ttu-id="86a98-139">응용 프로그램을 작성할 해당 스트림 데이터에서 SQL Server 없이 완전히 메모리에 로드 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="86a98-139">Discusses how to write applications that stream data from SQL Server without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a98-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="86a98-140">See also</span></span>

- [<span data-ttu-id="86a98-141">ADO.NET에서 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="86a98-141">Data Type Mappings in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="86a98-142">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="86a98-142">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="86a98-143">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="86a98-143">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="86a98-144">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="86a98-144">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)
- [<span data-ttu-id="86a98-145">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="86a98-145">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
