---
title: 큰 UDT
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: f55f6eccf3566a2391204e1ca4349ae5dff01954
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148558"
---
# <a name="large-udts"></a><span data-ttu-id="1123d-102">큰 UDT</span><span class="sxs-lookup"><span data-stu-id="1123d-102">Large UDTs</span></span>
<span data-ttu-id="1123d-103">UDT(사용자 정의 형식)는 개발자가 CLR(공용 언어 런타임) 개체를 SQL Server 데이터베이스에 저장하여 서버의 스칼라 형식 시스템을 확장할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-103">User-defined types (UDTs) allow a developer to extend the server's scalar type system by storing common language runtime (CLR) objects in a SQL Server database.</span></span> <span data-ttu-id="1123d-104">UDT는 단일 SQL Server 시스템 데이터 형식으로 구성된 일반적인 별칭 데이터 형식과 달리 여러 요소를 포함할 수 있으며 관련 동작이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-104">UDTs can contain multiple elements and can have behaviors, unlike the traditional alias data types, which consist of a single SQL Server system data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1123d-105">큰 UDT에 대한 지원이 향상된 SqlClient를 활용하려면 .NET Framework 3.5 SP1 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-105">You must install the .NET Framework 3.5 SP1 (or later) to take advantage of the enhanced SqlClient support for large UDTs.</span></span>  
  
 <span data-ttu-id="1123d-106">이전에는 UDT의 최대 크기가 8KB로 제한되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-106">Previously, UDTs were restricted to a maximum size of 8 kilobytes.</span></span> <span data-ttu-id="1123d-107">SQL Server 2008에서 <xref:Microsoft.SqlServer.Server.Format.UserDefined> 형식인 UDT에서는 이 제한이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-107">In SQL Server 2008, this restriction has been removed for UDTs that have a format of <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span></span>  
  
 <span data-ttu-id="1123d-108">사용자 정의 형식에 대한 자세한 내용은 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1123d-108">For the complete documentation for user-defined types, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="1123d-109">**SQL 서버 설명서**</span><span class="sxs-lookup"><span data-stu-id="1123d-109">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="1123d-110">CLR 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="1123d-110">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a><span data-ttu-id="1123d-111">GetSchema를 사용하여 UDT 스키마 검색</span><span class="sxs-lookup"><span data-stu-id="1123d-111">Retrieving UDT Schemas Using GetSchema</span></span>  
 <span data-ttu-id="1123d-112"><xref:System.Data.SqlClient.SqlConnection>의 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> 메서드는 <xref:System.Data.DataTable>에서 데이터베이스 스키마 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-112">The <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of <xref:System.Data.SqlClient.SqlConnection> returns database schema information in a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="1123d-113">자세한 내용은 [SQL 서버 스키마 컬렉션을](../sql-server-schema-collections.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1123d-113">For more information, see [SQL Server Schema Collections](../sql-server-schema-collections.md).</span></span>  
  
### <a name="getschematable-column-values-for-udts"></a><span data-ttu-id="1123d-114">UDT의 GetSchemaTable 열 값</span><span class="sxs-lookup"><span data-stu-id="1123d-114">GetSchemaTable Column Values for UDTs</span></span>  
 <span data-ttu-id="1123d-115"><xref:System.Data.SqlClient.SqlDataReader>의 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> 메서드는 열 메타데이터를 설명하는 <xref:System.Data.DataTable>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-115">The <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> method of a <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.DataTable> that describes column metadata.</span></span> <span data-ttu-id="1123d-116">다음 표에서는 SQL Server 2005와 SQL Server 2008 사이에 큰 UDT에 대한 열 메타데이터의 차이점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-116">The following table describes the differences in the column metadata for large UDTs between SQL Server 2005 and SQL Server 2008.</span></span>  
  
|<span data-ttu-id="1123d-117">SqlDataReader 열</span><span class="sxs-lookup"><span data-stu-id="1123d-117">SqlDataReader column</span></span>|<span data-ttu-id="1123d-118">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="1123d-118">SQL Server 2005</span></span>|<span data-ttu-id="1123d-119">SQL Server 2008 이상</span><span class="sxs-lookup"><span data-stu-id="1123d-119">SQL Server 2008 and later</span></span>|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|<span data-ttu-id="1123d-120">다양함</span><span class="sxs-lookup"><span data-stu-id="1123d-120">Varies</span></span>|<span data-ttu-id="1123d-121">다양함</span><span class="sxs-lookup"><span data-stu-id="1123d-121">Varies</span></span>|  
|`NumericPrecision`|<span data-ttu-id="1123d-122">255</span><span class="sxs-lookup"><span data-stu-id="1123d-122">255</span></span>|<span data-ttu-id="1123d-123">255</span><span class="sxs-lookup"><span data-stu-id="1123d-123">255</span></span>|  
|`NumericScale`|<span data-ttu-id="1123d-124">255</span><span class="sxs-lookup"><span data-stu-id="1123d-124">255</span></span>|<span data-ttu-id="1123d-125">255</span><span class="sxs-lookup"><span data-stu-id="1123d-125">255</span></span>|  
|`DataType`|`Byte[]`|<span data-ttu-id="1123d-126">UDT 인스턴스</span><span class="sxs-lookup"><span data-stu-id="1123d-126">UDT instance</span></span>|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|<span data-ttu-id="1123d-127">UDT 인스턴스</span><span class="sxs-lookup"><span data-stu-id="1123d-127">UDT instance</span></span>|  
|`ProviderType`|<span data-ttu-id="1123d-128">21 (`SqlDbType.VarBinary`)</span><span class="sxs-lookup"><span data-stu-id="1123d-128">21 (`SqlDbType.VarBinary`)</span></span>|<span data-ttu-id="1123d-129">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="1123d-129">29 (`SqlDbType.Udt`)</span></span>|  
|`NonVersionedProviderType`|<span data-ttu-id="1123d-130">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="1123d-130">29 (`SqlDbType.Udt`)</span></span>|<span data-ttu-id="1123d-131">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="1123d-131">29 (`SqlDbType.Udt`)</span></span>|  
|`DataTypeName`|`SqlDbType.VarBinary`|<span data-ttu-id="1123d-132">*Database.SchemaName.TypeName*과 같이 세 부분으로 지정되는 이름</span><span class="sxs-lookup"><span data-stu-id="1123d-132">The three part name specified as *Database.SchemaName.TypeName*.</span></span>|  
|`IsLong`|<span data-ttu-id="1123d-133">다양함</span><span class="sxs-lookup"><span data-stu-id="1123d-133">Varies</span></span>|<span data-ttu-id="1123d-134">다양함</span><span class="sxs-lookup"><span data-stu-id="1123d-134">Varies</span></span>|  
  
## <a name="sqldatareader-considerations"></a><span data-ttu-id="1123d-135">SqlDataReader 고려 사항</span><span class="sxs-lookup"><span data-stu-id="1123d-135">SqlDataReader Considerations</span></span>  
 <span data-ttu-id="1123d-136"><xref:System.Data.SqlClient.SqlDataReader>는 큰 UDT 값 검색을 지원하도록 SQL Server 2008부터 확장되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-136">The <xref:System.Data.SqlClient.SqlDataReader> has been extended beginning in SQL Server 2008 to support retrieving large UDT values.</span></span> <span data-ttu-id="1123d-137"><xref:System.Data.SqlClient.SqlDataReader>에 의해 처리되는 큰 UDT 값은 사용하는 SQL Server 버전과 연결 문자열에 지정된 `Type System Version`에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-137">How large UDT values are processed by a <xref:System.Data.SqlClient.SqlDataReader> depends on the version of SQL Server you are using, as well as on the `Type System Version` specified in the connection string.</span></span> <span data-ttu-id="1123d-138">자세한 내용은 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1123d-138">For more information, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
 <span data-ttu-id="1123d-139">다음 <xref:System.Data.SqlClient.SqlDataReader> 메서드는 `Type System Version`이 SQL Server 2005로 설정된 경우 UDT 대신 <xref:System.Data.SqlTypes.SqlBinary>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-139">The following methods of <xref:System.Data.SqlClient.SqlDataReader> will return a <xref:System.Data.SqlTypes.SqlBinary> instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 <span data-ttu-id="1123d-140">다음 메서드는 `Type System Version`이 SQL Server 2005로 설정된 경우 UDT 대신 `Byte[]` 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-140">The following methods will return an array of `Byte[]` instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 <span data-ttu-id="1123d-141">ADO.NET의 현재 버전에 대해서는 변환이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-141">Note that no conversions are made for the current version of ADO.NET.</span></span>  
  
## <a name="specifying-sqlparameters"></a><span data-ttu-id="1123d-142">SqlParameters 지정</span><span class="sxs-lookup"><span data-stu-id="1123d-142">Specifying SqlParameters</span></span>  
 <span data-ttu-id="1123d-143">다음 <xref:System.Data.SqlClient.SqlParameter> 속성이 큰 UDT를 사용하도록 확장되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-143">The following <xref:System.Data.SqlClient.SqlParameter> properties have been extended to work with large UDTs.</span></span>  
  
|<span data-ttu-id="1123d-144">SqlParameter 속성</span><span class="sxs-lookup"><span data-stu-id="1123d-144">SqlParameter Property</span></span>|<span data-ttu-id="1123d-145">Description</span><span class="sxs-lookup"><span data-stu-id="1123d-145">Description</span></span>|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="1123d-146">매개 변수의 값을 나타내는 개체를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-146">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="1123d-147">기본값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-147">The default is null.</span></span> <span data-ttu-id="1123d-148">이 속성은 `SqlBinary`, `Byte[]` 또는 관리 개체일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-148">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="1123d-149">매개 변수의 값을 나타내는 개체를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-149">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="1123d-150">기본값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-150">The default is null.</span></span> <span data-ttu-id="1123d-151">이 속성은 `SqlBinary`, `Byte[]` 또는 관리 개체일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-151">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="1123d-152">확인할 매개 변수 값의 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-152">Gets or sets the size of the parameter value to resolve.</span></span> <span data-ttu-id="1123d-153">기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-153">The default value is 0.</span></span> <span data-ttu-id="1123d-154">이 속성은 매개 변수 값의 크기를 나타내는 정수일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-154">The property can be an integer that represents the size of the parameter value.</span></span> <span data-ttu-id="1123d-155">큰 UDT의 경우 UDT의 실제 크기이거나 -1(알 수 없는 경우)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-155">For large UDTs, it can be the actual size of the UDT, or -1 for unknown.</span></span>|  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="1123d-156">데이터 검색 예제</span><span class="sxs-lookup"><span data-stu-id="1123d-156">Retrieving Data Example</span></span>  
 <span data-ttu-id="1123d-157">다음 코드 조각에서는 큰 UDT 데이터를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-157">The following code fragment demonstrates how to retrieve large UDT data.</span></span> <span data-ttu-id="1123d-158">`connectionString` 변수는 SQL Server 데이터베이스에 대한 유효한 연결을 가정하고 `commandString` 변수는 먼저 나열된 기본 키 열을 사용하는 올바른 SELECT 문을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1123d-158">The `connectionString` variable assumes a valid connection to a SQL Server database and the `commandString` variable assumes a valid SELECT statement with the primary key column listed first.</span></span>  
  
```csharp  
using (SqlConnection connection = new SqlConnection(
    connectionString, commandString))  
{  
  connection.Open();  
  SqlCommand command = new SqlCommand(commandString);  
  SqlDataReader reader = command.ExecuteReader();  
  while (reader.Read())  
  {  
    // Retrieve the value of the Primary Key column.  
    int id = reader.GetInt32(0);  
  
    // Retrieve the value of the UDT.  
    LargeUDT udt = (LargeUDT)reader[1];  
  
    // You can also use GetSqlValue and GetValue.  
    // LargeUDT udt = (LargeUDT)reader.GetSqlValue(1);  
    // LargeUDT udt = (LargeUDT)reader.GetValue(1);  
  
    Console.WriteLine(  
     "ID={0} LargeUDT={1}", id, udt);  
  }  
reader.close  
}  
```  
  
```vb  
Using connection As New SqlConnection( _  
    connectionString, commandString)  
    connection.Open()  
    Dim command As New SqlCommand(commandString, connection)  
    Dim reader As SqlDataReader  
    reader = command.ExecuteReader  
  
    While reader.Read()  
      ' Retrieve the value of the Primary Key column.  
      Dim id As Int32 = reader.GetInt32(0)  
  
      ' Retrieve the value of the UDT.  
      Dim udt As LargeUDT = CType(reader(1), LargeUDT)  
  
     ' You can also use GetSqlValue and GetValue.  
     ' Dim udt As LargeUDT = CType(reader.GetSqlValue(1), LargeUDT)  
     ' Dim udt As LargeUDT = CType(reader.GetValue(1), LargeUDT)  
  
      ' Print values.  
      Console.WriteLine("ID={0} LargeUDT={1}", id, udt)  
    End While  
    reader.Close()  
End Using  
```  
  
## <a name="see-also"></a><span data-ttu-id="1123d-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1123d-159">See also</span></span>

- [<span data-ttu-id="1123d-160">매개 변수 및 매개 변수 데이터 형식 구성</span><span class="sxs-lookup"><span data-stu-id="1123d-160">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="1123d-161">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="1123d-161">Retrieving Database Schema Information</span></span>](../retrieving-database-schema-information.md)
- [<span data-ttu-id="1123d-162">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="1123d-162">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="1123d-163">SQL 서버 바이너리 및 대값 데이터</span><span class="sxs-lookup"><span data-stu-id="1123d-163">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="1123d-164">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="1123d-164">ADO.NET Overview</span></span>](../ado-net-overview.md)
