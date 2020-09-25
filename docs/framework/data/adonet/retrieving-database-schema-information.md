---
title: 데이터베이스 스키마 정보 검색
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: c0aaadc82771d1c2a36d797bc157d88b8d3cacdc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177360"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="73576-102">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="73576-102">Retrieving Database Schema Information</span></span>

<span data-ttu-id="73576-103">데이터베이스에서 스키마 정보를 가져오려면 스키마 검색 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73576-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="73576-104">스키마 검색을 사용 하면 응용 프로그램에서 관리 되는 공급자가 지정 된 데이터베이스의 데이터베이스 스키마 ( *메타 데이터*라고도 함)에 대 한 정보를 찾아 반환 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73576-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="73576-105">테이블, 열 및 저장 프로시저 같은 다양한 데이터베이스 스키마 요소는 스키마 컬렉션을 통해 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="73576-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="73576-106">각 스키마 컬렉션에는 사용하는 공급자와 관련된 다양한 스키마 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73576-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="73576-107">.NET Framework 관리 되는 각 공급자는 **Connection** 클래스에서 **getschema** 메서드를 구현 하며 **getschema** 메서드에서 반환 되는 스키마 정보는 형식으로 제공 됩니다 <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="73576-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="73576-108">**GetSchema** 메서드는 반환할 스키마 컬렉션을 지정 하 고 반환 되는 정보의 양을 제한 하는 선택적 매개 변수를 제공 하는 오버 로드 된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="73576-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="73576-109">OLE DB, ODBC, Oracle 및 SqlClient에 대 한 .NET Framework 데이터 공급자는 **DataReader**의 열 메타 데이터를 설명 하는 DataTable을 반환 하는 **getschematable** 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73576-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="73576-110">또한 .NET Framework Data Provider for OLE DB에서는 <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> 개체의 <xref:System.Data.OleDb.OleDbConnection> 메서드를 사용하여 스키마 정보를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="73576-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="73576-111">인수로 **GetOleDbSchemaTable** <xref:System.Data.OleDb.OleDbSchemaGuid> 반환 되는 스키마 정보를 식별 하는와 반환 된 열에 대 한 제한의 배열을 사용 하 여 getoledbschematable은 합니다.</span><span class="sxs-lookup"><span data-stu-id="73576-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="73576-112">**Getoledbschematable은** 는 <xref:System.Data.DataTable> 요청 된 스키마 정보를 사용 하 여 채워진를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="73576-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73576-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="73576-113">In This Section</span></span>  

 [<span data-ttu-id="73576-114">GetSchema 및 Schema 컬렉션</span><span class="sxs-lookup"><span data-stu-id="73576-114">GetSchema and Schema Collections</span></span>](getschema-and-schema-collections.md)  
 <span data-ttu-id="73576-115">**GetSchema** 메서드와이 메서드를 사용 하 여 데이터베이스에서 스키마 정보를 검색 하 고 제한 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="73576-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="73576-116">스키마 제한</span><span class="sxs-lookup"><span data-stu-id="73576-116">Schema Restrictions</span></span>  
 <span data-ttu-id="73576-117">**GetSchema**에서 사용할 수 있는 스키마 제한 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="73576-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="73576-118">공용 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="73576-118">Common Schema Collections</span></span>](common-schema-collections.md)  
 <span data-ttu-id="73576-119">모든 .NET Framework 관리 공급자에서 지원하는 모든 공통 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73576-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="73576-120">SQL Server 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="73576-120">SQL Server Schema Collections</span></span>](sql-server-schema-collections.md)  
 <span data-ttu-id="73576-121">.NET Framework Provider for SQL Server에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73576-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="73576-122">Oracle 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="73576-122">Oracle Schema Collections</span></span>](oracle-schema-collections.md)  
 <span data-ttu-id="73576-123">.NET Framework Provider for Oracle에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73576-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="73576-124">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="73576-124">ODBC Schema Collections</span></span>](odbc-schema-collections.md)  
 <span data-ttu-id="73576-125">ODBC 드라이버의 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73576-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="73576-126">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="73576-126">OLE DB Schema Collections</span></span>](ole-db-schema-collections.md)  
 <span data-ttu-id="73576-127">OLE DB 공급자의 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73576-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="73576-128">참조</span><span class="sxs-lookup"><span data-stu-id="73576-128">Reference</span></span>  

 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="73576-129">클래스의 **GetSchema** 메서드에 대해 설명 합니다 <xref:System.Data.Common.DbConnection> .</span><span class="sxs-lookup"><span data-stu-id="73576-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="73576-130">클래스의 **GetSchema** 메서드에 대해 설명 합니다 <xref:System.Data.Odbc.OdbcConnection> .</span><span class="sxs-lookup"><span data-stu-id="73576-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="73576-131">클래스의 **GetSchema** 메서드에 대해 설명 합니다 <xref:System.Data.OleDb.OleDbConnection> .</span><span class="sxs-lookup"><span data-stu-id="73576-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="73576-132">클래스의 **GetSchema** 메서드에 대해 설명 합니다 <xref:System.Data.OracleClient.OracleConnection> .</span><span class="sxs-lookup"><span data-stu-id="73576-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="73576-133">클래스의 **GetSchema** 메서드에 대해 설명 합니다 <xref:System.Data.SqlClient.SqlConnection> .</span><span class="sxs-lookup"><span data-stu-id="73576-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="73576-134">클래스의 **Getschematable 평가할** 때이 메서드에 대해 설명 합니다 <xref:System.Data.Common.DbDataReader> .</span><span class="sxs-lookup"><span data-stu-id="73576-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="73576-135">클래스의 **Getschematable 평가할** 때이 메서드에 대해 설명 합니다 <xref:System.Data.Odbc.OdbcDataReader> .</span><span class="sxs-lookup"><span data-stu-id="73576-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="73576-136">클래스의 **Getschematable 평가할** 때이 메서드에 대해 설명 합니다 <xref:System.Data.OleDb.OleDbDataReader> .</span><span class="sxs-lookup"><span data-stu-id="73576-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="73576-137">클래스의 **Getschematable 평가할** 때이 메서드에 대해 설명 합니다 <xref:System.Data.OracleClient.OracleDataReader> .</span><span class="sxs-lookup"><span data-stu-id="73576-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="73576-138">클래스의 **Getschematable 평가할** 때이 메서드에 대해 설명 합니다 <xref:System.Data.SqlClient.SqlDataReader> .</span><span class="sxs-lookup"><span data-stu-id="73576-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73576-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73576-139">See also</span></span>

- [<span data-ttu-id="73576-140">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="73576-140">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="73576-141">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="73576-141">ADO.NET Overview</span></span>](ado-net-overview.md)
