---
title: SQL Server 및 ADO.NET
description: 데이터베이스 관련 프로토콜을 캡슐화 하는 SQL Server에 대 한 .NET Framework Data Provider의 기능 및 동작에 대해 알아봅니다.
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: eeb0ab69a68dfc2fc0faa1b4e833f80b307fffe5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286444"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="373e6-103">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="373e6-103">SQL Server and ADO.NET</span></span>
<span data-ttu-id="373e6-104">이 단원에서는 .NET Framework Data Provider for SQL Server(<xref:System.Data.SqlClient>)와 관련된 기능 및 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="373e6-104">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="373e6-105"><xref:System.Data.SqlClient>는 데이터베이스 관련 프로토콜을 캡슐화하는 SQL Server 버전에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="373e6-105"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="373e6-106">이 데이터 공급자의 기능은 OLE DB, ODBC 및 Oracle용 .NET Framework 데이터 공급자와 유사하게 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="373e6-106">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="373e6-107"><xref:System.Data.SqlClient>에는 SQL Server와 직접 통신하기 위한 TDS(Tabular Data Stream) 파서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="373e6-107"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="373e6-108">.NET Framework Data Provider for SQL Server를 사용하려면 애플리케이션에서 <xref:System.Data.SqlClient> 네임스페이스를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="373e6-108">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="373e6-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="373e6-109">In This Section</span></span>  
 [<span data-ttu-id="373e6-110">SQL Server 보안</span><span class="sxs-lookup"><span data-stu-id="373e6-110">SQL Server Security</span></span>](sql-server-security.md)  
 <span data-ttu-id="373e6-111">SQL Server 보안 기능에 대해 간략하게 설명하고 SQL Server를 대상으로 하는 안전한 ADO.NET 애플리케이션을 만드는 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="373e6-111">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="373e6-112">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="373e6-112">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)  
 <span data-ttu-id="373e6-113">SQL Server 데이터 형식을 사용하는 방법 및 이러한 데이터 형식이 .NET Framework 데이터 형식과 상호 작용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="373e6-113">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="373e6-114">이진 및 대량 값 데이터 SQL Server</span><span class="sxs-lookup"><span data-stu-id="373e6-114">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="373e6-115">SQL Server에서 큰 값 데이터를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="373e6-115">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="373e6-116">ADO.NET의 SQL Server 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="373e6-116">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)  
 <span data-ttu-id="373e6-117">SQL Server에서 데이터를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="373e6-117">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="373e6-118">대량 복사 작업, MARS, 비동기 작업 및 테이블 반환 매개 변수에 관한 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="373e6-118">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="373e6-119">SQL Server 기능 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="373e6-119">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)  
 <span data-ttu-id="373e6-120">ADO.NET 애플리케이션 개발자에게 유용한 SQL Server 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="373e6-120">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="373e6-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="373e6-121">LINQ to SQL</span></span>](./linq/index.md)  
 <span data-ttu-id="373e6-122">LINQ to SQL 애플리케이션을 만드는 데 필요한 기본 빌딩 블록, 프로세스 및 기술에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="373e6-122">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="373e6-123">SQL Server 데이터베이스 엔진에 대한 자세한 내용은 사용 중인 SQL Server 버전에 해당하는 SQL Server 온라인 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="373e6-123">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="373e6-124">SQL Server 온라인 설명서</span><span class="sxs-lookup"><span data-stu-id="373e6-124">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="373e6-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="373e6-125">See also</span></span>

- [<span data-ttu-id="373e6-126">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="373e6-126">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="373e6-127">ADO.NET에서 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="373e6-127">Data Type Mappings in ADO.NET</span></span>](../data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="373e6-128">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="373e6-128">DataSets, DataTables, and DataViews</span></span>](../dataset-datatable-dataview/index.md)
- [<span data-ttu-id="373e6-129">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="373e6-129">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="373e6-130">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="373e6-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
