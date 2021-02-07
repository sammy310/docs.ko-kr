---
description: '자세히 알아보기: 데이터베이스 스키마 정보 검색'
title: 데이터베이스 스키마 정보 검색
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 84ac94a72b23d0b1d6924600f2fd33b2a285eab8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663406"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="3d94d-103">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="3d94d-103">Retrieving Database Schema Information</span></span>

<span data-ttu-id="3d94d-104">데이터베이스에서 스키마 정보를 가져오려면 스키마 검색 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-104">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="3d94d-105">스키마 검색을 사용하면 애플리케이션에서 관리되는 공급자가 지정된 데이터베이스의 데이터베이스 스키마(‘메타데이터’라고도 함)에 관한 정보를 찾아 반환하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-105">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="3d94d-106">테이블, 열 및 저장 프로시저 같은 다양한 데이터베이스 스키마 요소는 스키마 컬렉션을 통해 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-106">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="3d94d-107">각 스키마 컬렉션에는 사용하는 공급자와 관련된 다양한 스키마 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-107">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="3d94d-108">.NET Framework 관리 되는 각 공급자는 **Connection** 클래스에서 **getschema** 메서드를 구현 하며 **getschema** 메서드에서 반환 되는 스키마 정보는 형식으로 제공 됩니다 <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="3d94d-108">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="3d94d-109">**GetSchema** 메서드는 스키마 컬렉션이 반환되도록 지정하고 반환되는 정보의 양을 제한하기 위한 선택적 매개 변수를 제공하는 오버로드 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-109">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="3d94d-110">OLE DB, ODBC, Oracle 및 SqlClient에 대 한 .NET Framework 데이터 공급자는 **DataReader** 의 열 메타 데이터를 설명 하는 DataTable을 반환 하는 **getschematable** 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-110">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="3d94d-111">또한 .NET Framework Data Provider for OLE DB에서는 <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> 개체의 <xref:System.Data.OleDb.OleDbConnection> 메서드를 사용하여 스키마 정보를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-111">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="3d94d-112">인수로  <xref:System.Data.OleDb.OleDbSchemaGuid> 반환 되는 스키마 정보를 식별 하는와 반환 된 열에 대 한 제한의 배열을 사용 하 여 getoledbschematable은 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-112">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="3d94d-113">**Getoledbschematable은** 는 <xref:System.Data.DataTable> 요청 된 스키마 정보를 사용 하 여 채워진를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-113">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d94d-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="3d94d-114">In This Section</span></span>  

 [<span data-ttu-id="3d94d-115">GetSchema 및 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="3d94d-115">GetSchema and Schema Collections</span></span>](getschema-and-schema-collections.md)  
 <span data-ttu-id="3d94d-116">**GetSchema** 메서드와 이를 사용하여 데이터베이스에서 스키마 정보를 검색하고 제한하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-116">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="3d94d-117">스키마 제한</span><span class="sxs-lookup"><span data-stu-id="3d94d-117">Schema Restrictions</span></span>  
 <span data-ttu-id="3d94d-118">**GetSchema** 와 함께 사용할 수 있는 스키마 제한을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-118">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="3d94d-119">공용 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="3d94d-119">Common Schema Collections</span></span>](common-schema-collections.md)  
 <span data-ttu-id="3d94d-120">모든 .NET Framework 관리 공급자에서 지원하는 모든 공통 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-120">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="3d94d-121">SQL Server 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="3d94d-121">SQL Server Schema Collections</span></span>](sql-server-schema-collections.md)  
 <span data-ttu-id="3d94d-122">.NET Framework Provider for SQL Server에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-122">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="3d94d-123">Oracle 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="3d94d-123">Oracle Schema Collections</span></span>](oracle-schema-collections.md)  
 <span data-ttu-id="3d94d-124">.NET Framework Provider for Oracle에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-124">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="3d94d-125">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="3d94d-125">ODBC Schema Collections</span></span>](odbc-schema-collections.md)  
 <span data-ttu-id="3d94d-126">ODBC 드라이버의 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-126">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="3d94d-127">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="3d94d-127">OLE DB Schema Collections</span></span>](ole-db-schema-collections.md)  
 <span data-ttu-id="3d94d-128">OLE DB 공급자의 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-128">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3d94d-129">참조</span><span class="sxs-lookup"><span data-stu-id="3d94d-129">Reference</span></span>  

 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="3d94d-130"><xref:System.Data.Common.DbConnection> 클래스의 **GetSchema** 메서드에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-130">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="3d94d-131"><xref:System.Data.Odbc.OdbcConnection> 클래스의 **GetSchema** 메서드에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-131">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="3d94d-132"><xref:System.Data.OleDb.OleDbConnection> 클래스의 **GetSchema** 메서드에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-132">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="3d94d-133"><xref:System.Data.OracleClient.OracleConnection> 클래스의 **GetSchema** 메서드에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-133">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="3d94d-134"><xref:System.Data.SqlClient.SqlConnection> 클래스의 **GetSchema** 메서드에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-134">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="3d94d-135"><xref:System.Data.Common.DbDataReader> 클래스의 **GetSchemaTable** 메서드에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="3d94d-136"><xref:System.Data.Odbc.OdbcDataReader> 클래스의 **GetSchemaTable** 메서드에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-136">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="3d94d-137"><xref:System.Data.OleDb.OleDbDataReader> 클래스의 **GetSchemaTable** 메서드에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="3d94d-138"><xref:System.Data.OracleClient.OracleDataReader> 클래스의 **GetSchemaTable** 메서드에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-138">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="3d94d-139"><xref:System.Data.SqlClient.SqlDataReader> 클래스의 **GetSchemaTable** 메서드에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94d-139">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d94d-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d94d-140">See also</span></span>

- [<span data-ttu-id="3d94d-141">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="3d94d-141">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="3d94d-142">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="3d94d-142">ADO.NET Overview</span></span>](ado-net-overview.md)
