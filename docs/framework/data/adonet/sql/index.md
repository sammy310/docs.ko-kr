---
title: SQL Server 및 ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: 6e88c35936de72f0d426c23493bbe5a08e707ee1
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979978"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="0f7c7-102">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0f7c7-102">SQL Server and ADO.NET</span></span>
<span data-ttu-id="0f7c7-103">이 단원에서는 .NET Framework Data Provider for SQL Server(<xref:System.Data.SqlClient>)와 관련된 기능 및 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-103">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="0f7c7-104"><xref:System.Data.SqlClient>는 데이터베이스 관련 프로토콜을 캡슐화하는 SQL Server 버전에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-104"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="0f7c7-105">이 데이터 공급자의 기능은 OLE DB, ODBC 및 Oracle용 .NET Framework 데이터 공급자와 유사하게 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-105">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="0f7c7-106"><xref:System.Data.SqlClient>에는 SQL Server와 직접 통신하기 위한 TDS(Tabular Data Stream) 파서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-106"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f7c7-107">.NET Framework Data Provider for SQL Server를 사용하려면 애플리케이션에서 <xref:System.Data.SqlClient> 네임스페이스를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-107">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f7c7-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0f7c7-108">In This Section</span></span>  
 [<span data-ttu-id="0f7c7-109">SQL Server 보안</span><span class="sxs-lookup"><span data-stu-id="0f7c7-109">SQL Server Security</span></span>](sql-server-security.md)  
 <span data-ttu-id="0f7c7-110">SQL Server 보안 기능에 대해 간략하게 설명하고 SQL Server를 대상으로 하는 안전한 ADO.NET 애플리케이션을 만드는 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-110">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="0f7c7-111">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0f7c7-111">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)  
 <span data-ttu-id="0f7c7-112">SQL Server 데이터 형식을 사용하는 방법 및 이러한 데이터 형식이 .NET Framework 데이터 형식과 상호 작용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-112">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="0f7c7-113">SQL Server 이진 및 큰 값 데이터</span><span class="sxs-lookup"><span data-stu-id="0f7c7-113">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="0f7c7-114">SQL Server에서 큰 값 데이터로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-114">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="0f7c7-115">ADO.NET에서 SQL Server 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="0f7c7-115">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)  
 <span data-ttu-id="0f7c7-116">SQL Server에서 데이터로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-116">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="0f7c7-117">대량 복사 작업, MARS, 비동기 작업 및 테이블 반환 매개 변수에 대해 설명하는 단원을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-117">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="0f7c7-118">SQL Server 기능 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0f7c7-118">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)  
 <span data-ttu-id="0f7c7-119">ADO.NET 애플리케이션 개발자에게 유용한 SQL Server 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-119">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="0f7c7-120">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0f7c7-120">LINQ to SQL</span></span>](./linq/index.md)  
 <span data-ttu-id="0f7c7-121">LINQ to SQL 애플리케이션을 만드는 데 필요한 기본 빌딩 블록, 프로세스 및 기술에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-121">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="0f7c7-122">SQL Server 데이터베이스 엔진에 대한 자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f7c7-122">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="0f7c7-123">SQL Server 온라인 설명서</span><span class="sxs-lookup"><span data-stu-id="0f7c7-123">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="0f7c7-124">참조</span><span class="sxs-lookup"><span data-stu-id="0f7c7-124">See also</span></span>

- [<span data-ttu-id="0f7c7-125">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="0f7c7-125">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="0f7c7-126">ADO.NET에서 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="0f7c7-126">Data Type Mappings in ADO.NET</span></span>](../data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="0f7c7-127">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="0f7c7-127">DataSets, DataTables, and DataViews</span></span>](../dataset-datatable-dataview/index.md)
- [<span data-ttu-id="0f7c7-128">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="0f7c7-128">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="0f7c7-129">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="0f7c7-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
