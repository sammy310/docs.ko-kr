---
title: SQL Server 데이터 형식 및 ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: f727c69b1dd5c23c6a89911005256de70255fd4c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452333"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="9382a-102">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9382a-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="9382a-103">SQL Server와 .NET Framework는 서로 다른 형식 시스템을 기반으로 하기 때문에 데이터가 손실될 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="9382a-104">.NET Framework Data Provider for SQL Server(<xref:System.Data.SqlClient>)에서는 데이터 무결성을 유지하기 위해 SQL Server 데이터로 작업할 때 형식화된 접근자 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="9382a-105"><xref:System.Data.SqlDbType> 클래스의 열거형을 사용하여 <xref:System.Data.SqlClient.SqlParameter> 데이터 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="9382a-106">SQL Server와 .NET Framework 데이터 형식 간의 데이터 형식 매핑을 설명 하는 테이블 및 자세한 내용은 [SQL Server 데이터 형식 매핑](../sql-server-data-type-mappings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9382a-106">For more information and a table that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="9382a-107">SQL Server 2008에서는 날짜와 시간, 구조화된 데이터, 반구조적 데이터 및 구조화되지 않은 데이터로 작업해야 하는 비즈니스 요구 사항을 충족하도록 디자인된 새로운 데이터 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="9382a-108">이 내용은 SQL Server 2008 온라인 설명서에 문서화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="9382a-109">애플리케이션에서 사용할 수 있는 SQL Server 데이터 형식은 현재 사용하고 있는 SQL Server 버전에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="9382a-110">자세한 내용은 다음 표에서 해당되는 SQL Server 온라인 설명서 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9382a-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="9382a-111">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="9382a-111">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="9382a-112">데이터 형식(Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9382a-112">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a><span data-ttu-id="9382a-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="9382a-113">In This Section</span></span>  
 [<span data-ttu-id="9382a-114">SqlTypes 및 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="9382a-114">SqlTypes and the DataSet</span></span>](sqltypes-and-the-dataset.md)  
 <span data-ttu-id="9382a-115">`SqlTypes`의 `DataSet`에 대한 형식 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="9382a-116">Null 값 처리</span><span class="sxs-lookup"><span data-stu-id="9382a-116">Handling Null Values</span></span>](handling-null-values.md)  
 <span data-ttu-id="9382a-117">null 값 및 3중값 논리로 작업하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="9382a-118">GUID 및 uniqueidentifier 값 비교</span><span class="sxs-lookup"><span data-stu-id="9382a-118">Comparing GUID and uniqueidentifier Values</span></span>](comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="9382a-119">SQL Server 및 .NET Framework에서 GUID 및 uniqueidentifier 값으로 작업하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="9382a-120">날짜 및 시간 데이터</span><span class="sxs-lookup"><span data-stu-id="9382a-120">Date and Time Data</span></span>](date-and-time-data.md)  
 <span data-ttu-id="9382a-121">SQL Server 2008에서 지원하는 새로운 날짜 및 시간 데이터 형식의 사용 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="9382a-122">큰 UDT</span><span class="sxs-lookup"><span data-stu-id="9382a-122">Large UDTs</span></span>](large-udts.md)  
 <span data-ttu-id="9382a-123">SQL Server 2008에서 지원하는 큰 값 UDT에서 데이터를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="9382a-124">SQL Server의 XML 데이터</span><span class="sxs-lookup"><span data-stu-id="9382a-124">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)  
 <span data-ttu-id="9382a-125">SQL Server에서 검색한 XML 데이터로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9382a-126">참조</span><span class="sxs-lookup"><span data-stu-id="9382a-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="9382a-127">`DataSet` 클래스와 해당 멤버 전체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="9382a-128">`SqlTypes` 네임스페이스와 해당 멤버 전체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="9382a-129">`SqlDbType` 열거형과 해당 멤버 전체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="9382a-130">`DbType` 열거형과 해당 멤버 전체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9382a-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9382a-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9382a-131">See also</span></span>

- [<span data-ttu-id="9382a-132">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="9382a-132">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="9382a-133">매개 변수 및 매개 변수 데이터 형식 구성</span><span class="sxs-lookup"><span data-stu-id="9382a-133">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="9382a-134">테이블 반환 매개 변수</span><span class="sxs-lookup"><span data-stu-id="9382a-134">Table-Valued Parameters</span></span>](table-valued-parameters.md)
- [<span data-ttu-id="9382a-135">SQL Server 이진 및 큰 값 데이터</span><span class="sxs-lookup"><span data-stu-id="9382a-135">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="9382a-136">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="9382a-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
