---
title: SQL Server 및 ADO.NET
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: c58c6da7a6028c9167c73af820e922f59b528f15
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938090"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="b174f-102">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b174f-102">SQL Server and ADO.NET</span></span>
<span data-ttu-id="b174f-103">이 단원에서는 .NET Framework Data Provider for SQL Server(<xref:System.Data.SqlClient>)와 관련된 기능 및 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b174f-103">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="b174f-104"><xref:System.Data.SqlClient>는 데이터베이스 관련 프로토콜을 캡슐화하는 SQL Server 버전에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b174f-104"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="b174f-105">이 데이터 공급자의 기능은 OLE DB, ODBC 및 Oracle용 .NET Framework 데이터 공급자와 유사하게 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b174f-105">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="b174f-106"><xref:System.Data.SqlClient>에는 SQL Server와 직접 통신하기 위한 TDS(Tabular Data Stream) 파서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b174f-106"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b174f-107">.NET Framework Data Provider for SQL Server를 사용하려면 애플리케이션에서 <xref:System.Data.SqlClient> 네임스페이스를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b174f-107">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b174f-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b174f-108">In This Section</span></span>  
 [<span data-ttu-id="b174f-109">SQL Server 보안</span><span class="sxs-lookup"><span data-stu-id="b174f-109">SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="b174f-110">SQL Server 보안 기능에 대해 간략하게 설명하고 SQL Server를 대상으로 하는 안전한 ADO.NET 애플리케이션을 만드는 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b174f-110">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="b174f-111">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b174f-111">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 <span data-ttu-id="b174f-112">SQL Server 데이터 형식을 사용하는 방법 및 이러한 데이터 형식이 .NET Framework 데이터 형식과 상호 작용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b174f-112">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="b174f-113">SQL Server 이진 및 큰 값 데이터</span><span class="sxs-lookup"><span data-stu-id="b174f-113">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="b174f-114">SQL Server에서 큰 값 데이터로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b174f-114">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="b174f-115">ADO.NET에서 SQL Server 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="b174f-115">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 <span data-ttu-id="b174f-116">SQL Server에서 데이터로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b174f-116">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="b174f-117">대량 복사 작업, MARS, 비동기 작업 및 테이블 반환 매개 변수에 대해 설명하는 단원을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b174f-117">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="b174f-118">SQL Server 기능 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b174f-118">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 <span data-ttu-id="b174f-119">ADO.NET 애플리케이션 개발자에게 유용한 SQL Server 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b174f-119">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="b174f-120">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b174f-120">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="b174f-121">LINQ to SQL 애플리케이션을 만드는 데 필요한 기본 빌딩 블록, 프로세스 및 기술에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b174f-121">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="b174f-122">SQL Server 데이터베이스 엔진에 대한 자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b174f-122">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="b174f-123">SQL Server 온라인 설명서</span><span class="sxs-lookup"><span data-stu-id="b174f-123">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="b174f-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="b174f-124">See also</span></span>

- [<span data-ttu-id="b174f-125">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="b174f-125">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="b174f-126">ADO.NET에서 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="b174f-126">Data Type Mappings in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="b174f-127">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="b174f-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="b174f-128">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="b174f-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="b174f-129">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="b174f-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
