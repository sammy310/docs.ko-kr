---
title: 데이터베이스 스키마 정보 검색
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 885d3c9ad61c9099c960ddb0c0f77fa8a98dbefa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61664248"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="6d19d-102">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="6d19d-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="6d19d-103">데이터베이스에서 스키마 정보를 가져오려면 스키마 검색 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="6d19d-104">스키마 검색을 사용 하면 응용 프로그램을 관리 되는 공급자 찾아 라고도 데이터베이스 스키마에 대 한 정보 반환을 요청 *메타 데이터*, 지정된 된 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="6d19d-105">테이블, 열 및 저장 프로시저 같은 다양한 데이터베이스 스키마 요소는 스키마 컬렉션을 통해 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="6d19d-106">각 스키마 컬렉션에는 사용하는 공급자와 관련된 다양한 스키마 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="6d19d-107">각.NET Framework 관리 공급자 구현 합니다 **GetSchema** 에서 메서드는 **연결** 에서 반환 되는 스키마 정보와 클래스는 **GetSchema**형태로 제공 되는 메서드를 <xref:System.Data.DataTable>입니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="6d19d-108">합니다 **GetSchema** 메서드는 스키마 컬렉션이 반환 되도록 지정 하 고 반환 되는 정보의 양을 제한에 대 한 선택적 매개 변수를 제공 하는 오버 로드 된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="6d19d-109">OLE DB, ODBC, Oracle 및 SqlClient에 대 한.NET Framework 데이터 공급자를 제공 된 **GetSchemaTable** 의 열 메타 데이터를 설명 하는 DataTable을 반환 하는 메서드는 **DataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="6d19d-110">또한 .NET Framework Data Provider for OLE DB에서는 <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> 개체의 <xref:System.Data.OleDb.OleDbConnection> 메서드를 사용하여 스키마 정보를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="6d19d-111">인수로 **GetOleDbSchemaTable** 사용을 <xref:System.Data.OleDb.OleDbSchemaGuid> 반환할 스키마 정보를 식별 하 고 반환 된 열에 대 한 제한 배열을 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="6d19d-112">**GetOleDbSchemaTable** 반환을 <xref:System.Data.DataTable> 요청한 스키마 정보로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d19d-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6d19d-113">In This Section</span></span>  
 [<span data-ttu-id="6d19d-114">GetSchema 및 Schema 컬렉션</span><span class="sxs-lookup"><span data-stu-id="6d19d-114">GetSchema and Schema Collections</span></span>](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 <span data-ttu-id="6d19d-115">에 대해 설명 합니다 **GetSchema** 메서드와 사용할 수 있는 방법을 검색 하 고 데이터베이스에서 스키마 정보를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="6d19d-116">스키마 제한</span><span class="sxs-lookup"><span data-stu-id="6d19d-116">Schema Restrictions</span></span>  
 <span data-ttu-id="6d19d-117">사용 하 여 사용할 수 있는 스키마 제한을 설명 합니다 **GetSchema**합니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="6d19d-118">공통 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="6d19d-118">Common Schema Collections</span></span>](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 <span data-ttu-id="6d19d-119">모든 .NET Framework 관리 공급자에서 지원하는 모든 공통 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="6d19d-120">SQL Server 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="6d19d-120">SQL Server Schema Collections</span></span>](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 <span data-ttu-id="6d19d-121">.NET Framework Provider for SQL Server에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="6d19d-122">Oracle 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="6d19d-122">Oracle Schema Collections</span></span>](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 <span data-ttu-id="6d19d-123">.NET Framework Provider for Oracle에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="6d19d-124">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="6d19d-124">ODBC Schema Collections</span></span>](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 <span data-ttu-id="6d19d-125">ODBC 드라이버의 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="6d19d-126">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="6d19d-126">OLE DB Schema Collections</span></span>](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 <span data-ttu-id="6d19d-127">OLE DB 공급자의 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6d19d-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6d19d-128">참조</span><span class="sxs-lookup"><span data-stu-id="6d19d-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="6d19d-129">에 대해 설명 합니다 **GetSchema** 메서드를 <xref:System.Data.Common.DbConnection> 클래스.</span><span class="sxs-lookup"><span data-stu-id="6d19d-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="6d19d-130">에 대해 설명 합니다 **GetSchema** 메서드를 <xref:System.Data.Odbc.OdbcConnection> 클래스.</span><span class="sxs-lookup"><span data-stu-id="6d19d-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="6d19d-131">에 대해 설명 합니다 **GetSchema** 메서드를 <xref:System.Data.OleDb.OleDbConnection> 클래스.</span><span class="sxs-lookup"><span data-stu-id="6d19d-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="6d19d-132">에 대해 설명 합니다 **GetSchema** 메서드를 <xref:System.Data.OracleClient.OracleConnection> 클래스.</span><span class="sxs-lookup"><span data-stu-id="6d19d-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="6d19d-133">에 대해 설명 합니다 **GetSchema** 메서드를 <xref:System.Data.SqlClient.SqlConnection> 클래스.</span><span class="sxs-lookup"><span data-stu-id="6d19d-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="6d19d-134">에 대해 설명 합니다 **GetSchemaTable** 메서드를 <xref:System.Data.Common.DbDataReader> 클래스.</span><span class="sxs-lookup"><span data-stu-id="6d19d-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="6d19d-135">에 대해 설명 합니다 **GetSchemaTable** 메서드를 <xref:System.Data.Odbc.OdbcDataReader> 클래스.</span><span class="sxs-lookup"><span data-stu-id="6d19d-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="6d19d-136">에 대해 설명 합니다 **GetSchemaTable** 메서드를 <xref:System.Data.OleDb.OleDbDataReader> 클래스.</span><span class="sxs-lookup"><span data-stu-id="6d19d-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="6d19d-137">에 대해 설명 합니다 **GetSchemaTable** 메서드를 <xref:System.Data.OracleClient.OracleDataReader> 클래스.</span><span class="sxs-lookup"><span data-stu-id="6d19d-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="6d19d-138">에 대해 설명 합니다 **GetSchemaTable** 메서드를 <xref:System.Data.SqlClient.SqlDataReader> 클래스.</span><span class="sxs-lookup"><span data-stu-id="6d19d-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d19d-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="6d19d-139">See also</span></span>

- [<span data-ttu-id="6d19d-140">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="6d19d-140">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="6d19d-141">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="6d19d-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
