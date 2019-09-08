---
title: 데이터베이스 스키마 정보 검색
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 26b234e35a0d0849914d87b61f4e8c8a87599448
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782732"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="22d99-102">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="22d99-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="22d99-103">데이터베이스에서 스키마 정보를 가져오려면 스키마 검색 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="22d99-104">스키마 검색을 사용 하면 응용 프로그램에서 관리 되는 공급자가 지정 된 데이터베이스의 데이터베이스 스키마 ( *메타 데이터*라고도 함)에 대 한 정보를 찾아 반환 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="22d99-105">테이블, 열 및 저장 프로시저 같은 다양한 데이터베이스 스키마 요소는 스키마 컬렉션을 통해 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="22d99-106">각 스키마 컬렉션에는 사용하는 공급자와 관련된 다양한 스키마 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="22d99-107">.NET Framework 관리 되는 각 공급자는 **Connection** 클래스에서 **getschema** 메서드를 구현 하며 **getschema** 메서드에서 반환 되는 스키마 정보는 형식 <xref:System.Data.DataTable>으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="22d99-108">**GetSchema** 메서드는 반환할 스키마 컬렉션을 지정 하 고 반환 되는 정보의 양을 제한 하는 선택적 매개 변수를 제공 하는 오버 로드 된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="22d99-109">OLE DB, ODBC, Oracle 및 SqlClient에 대 한 .NET Framework 데이터 공급자는 **DataReader**의 열 메타 데이터를 설명 하는 DataTable을 반환 하는 **getschematable** 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="22d99-110">또한 .NET Framework Data Provider for OLE DB에서는 <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> 개체의 <xref:System.Data.OleDb.OleDbConnection> 메서드를 사용하여 스키마 정보를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="22d99-111">인수로 반환 <xref:System.Data.OleDb.OleDbSchemaGuid> 되는 스키마 정보를 식별 하는와 반환 된 열에 대 한 제한의 배열을 사용 하 여 **getoledbschematable은** 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="22d99-112">**Getoledbschematable은** 는 요청 <xref:System.Data.DataTable> 된 스키마 정보를 사용 하 여 채워진를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22d99-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="22d99-113">In This Section</span></span>  
 [<span data-ttu-id="22d99-114">GetSchema 및 Schema 컬렉션</span><span class="sxs-lookup"><span data-stu-id="22d99-114">GetSchema and Schema Collections</span></span>](getschema-and-schema-collections.md)  
 <span data-ttu-id="22d99-115">**GetSchema** 메서드와이 메서드를 사용 하 여 데이터베이스에서 스키마 정보를 검색 하 고 제한 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="22d99-116">스키마 제한</span><span class="sxs-lookup"><span data-stu-id="22d99-116">Schema Restrictions</span></span>  
 <span data-ttu-id="22d99-117">**GetSchema**에서 사용할 수 있는 스키마 제한 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="22d99-118">공통 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="22d99-118">Common Schema Collections</span></span>](common-schema-collections.md)  
 <span data-ttu-id="22d99-119">모든 .NET Framework 관리 공급자에서 지원하는 모든 공통 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="22d99-120">SQL Server 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="22d99-120">SQL Server Schema Collections</span></span>](sql-server-schema-collections.md)  
 <span data-ttu-id="22d99-121">.NET Framework Provider for SQL Server에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="22d99-122">Oracle 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="22d99-122">Oracle Schema Collections</span></span>](oracle-schema-collections.md)  
 <span data-ttu-id="22d99-123">.NET Framework Provider for Oracle에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="22d99-124">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="22d99-124">ODBC Schema Collections</span></span>](odbc-schema-collections.md)  
 <span data-ttu-id="22d99-125">ODBC 드라이버의 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="22d99-126">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="22d99-126">OLE DB Schema Collections</span></span>](ole-db-schema-collections.md)  
 <span data-ttu-id="22d99-127">OLE DB 공급자의 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="22d99-128">참조</span><span class="sxs-lookup"><span data-stu-id="22d99-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="22d99-129"><xref:System.Data.Common.DbConnection> 클래스의 **GetSchema** 메서드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="22d99-130"><xref:System.Data.Odbc.OdbcConnection> 클래스의 **GetSchema** 메서드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="22d99-131"><xref:System.Data.OleDb.OleDbConnection> 클래스의 **GetSchema** 메서드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="22d99-132"><xref:System.Data.OracleClient.OracleConnection> 클래스의 **GetSchema** 메서드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="22d99-133"><xref:System.Data.SqlClient.SqlConnection> 클래스의 **GetSchema** 메서드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="22d99-134"><xref:System.Data.Common.DbDataReader> 클래스의 **getschematable 평가할** 때이 메서드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="22d99-135"><xref:System.Data.Odbc.OdbcDataReader> 클래스의 **getschematable 평가할** 때이 메서드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="22d99-136"><xref:System.Data.OleDb.OleDbDataReader> 클래스의 **getschematable 평가할** 때이 메서드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="22d99-137"><xref:System.Data.OracleClient.OracleDataReader> 클래스의 **getschematable 평가할** 때이 메서드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="22d99-138"><xref:System.Data.SqlClient.SqlDataReader> 클래스의 **getschematable 평가할** 때이 메서드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d99-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d99-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="22d99-139">See also</span></span>

- [<span data-ttu-id="22d99-140">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="22d99-140">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="22d99-141">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="22d99-141">ADO.NET Overview</span></span>](ado-net-overview.md)
