---
title: 대량 값 (max) 데이터 수정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: 4748740379df689669ee87f66dce58a7015d1217
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172699"
---
# <a name="modifying-large-value-max-data-in-adonet"></a><span data-ttu-id="25340-102">ADO.NET에서 큰 값(최대값) 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="25340-102">Modifying Large-Value (max) Data in ADO.NET</span></span>

<span data-ttu-id="25340-103">LOB(Large Object) 데이터 형식은 최대 행 크기가 8KB를 초과하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="25340-103">Large object (LOB) data types are those that exceed the maximum row size of 8 kilobytes (KB).</span></span> <span data-ttu-id="25340-104">SQL Server는 `max`, `varchar` 및 `nvarchar` 데이터 형식에 사용할 수 있는 `varbinary` 지정자를 도입하여 2^32바이트에 이르는 큰 값도 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-104">SQL Server provides a `max` specifier for `varchar`, `nvarchar`, and `varbinary` data types to allow storage of values as large as 2^32 bytes.</span></span> <span data-ttu-id="25340-105">테이블 열과 Transact-SQL 변수는 `varchar(max)`, `nvarchar(max)` 또는 `varbinary(max)` 데이터 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-105">Table columns and Transact-SQL variables may specify `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` data types.</span></span> <span data-ttu-id="25340-106">ADO.NET에서는 `max`를 사용하여 `DataReader` 데이터 형식을 가져올 수 있을 뿐 아니라 특별한 처리 없이도 입력 및 출력 매개 변수 값을 모두 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-106">In ADO.NET, the `max` data types can be fetched by a `DataReader`, and can also be specified as both input and output parameter values without any special handling.</span></span> <span data-ttu-id="25340-107">큰 `varchar` 데이터 형식의 경우 데이터를 증분 방식으로 검색하고 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-107">For large `varchar` data types, data can be retrieved and updated incrementally.</span></span>  
  
 <span data-ttu-id="25340-108">`max` 데이터 형식을 사용하여 비교 및 연결 작업을 수행할 수 있으며, 비교를 수행할 경우에는 Transact-SQL 변수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-108">The `max` data types can be used for comparisons, as Transact-SQL variables, and for concatenation.</span></span> <span data-ttu-id="25340-109">SELECT 문의 DISTINCT, ORDER BY, GROUP BY 절에서뿐 아니라 집계, 조인 및 하위 쿼리에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-109">They can also be used in the DISTINCT, ORDER BY, GROUP BY clauses of a SELECT statement as well as in aggregates, joins, and subqueries.</span></span>  
  
 <span data-ttu-id="25340-110">다음 표에는 SQL Server 온라인 설명서의 문서에 대한 링크가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-110">The following table provides links to the documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="25340-111">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="25340-111">**SQL Server documentation**</span></span>  
  
1. <span data-ttu-id="25340-112">[큰 값 데이터 형식 사용](/previous-versions/sql/sql-server-2008/ms178158(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="25340-112">[Using Large-Value Data Types](/previous-versions/sql/sql-server-2008/ms178158(v=sql.100))</span></span>  
  
## <a name="large-value-type-restrictions"></a><span data-ttu-id="25340-113">큰 값 형식 제한 사항</span><span class="sxs-lookup"><span data-stu-id="25340-113">Large-Value Type Restrictions</span></span>  

 <span data-ttu-id="25340-114">`max` 데이터 형식에는 더 작은 데이터 형식에서는 존재하지 않는 다음 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25340-114">The following restrictions apply to the `max` data types, which do not exist for smaller data types:</span></span>  
  
- <span data-ttu-id="25340-115">`sql_variant`는 큰 `varchar` 데이터 형식을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-115">A `sql_variant` cannot contain a large `varchar` data type.</span></span>  
  
- <span data-ttu-id="25340-116">긴 `varchar` 열을 인덱스의 키 열로 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-116">Large `varchar` columns cannot be specified as a key column in an index.</span></span> <span data-ttu-id="25340-117">비클러스터형 인덱스의 포괄 열에는 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25340-117">They are allowed in an included column in a non-clustered index.</span></span>  
  
- <span data-ttu-id="25340-118">큰 `varchar` 열을 분할 키 열로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-118">Large `varchar` columns cannot be used as partitioning key columns.</span></span>  
  
## <a name="working-with-large-value-types-in-transact-sql"></a><span data-ttu-id="25340-119">Transact-SQL에서 큰 값 형식 사용</span><span class="sxs-lookup"><span data-stu-id="25340-119">Working with Large-Value Types in Transact-SQL</span></span>  

 <span data-ttu-id="25340-120">Transact-SQL `OPENROWSET` 함수는 원격 데이터에 연결하고 액세스하는 일회성 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="25340-120">The Transact-SQL `OPENROWSET` function is a one-time method of connecting and accessing remote data.</span></span> <span data-ttu-id="25340-121">이 함수에는 OLE DB 데이터 소스에서 원격 데이터에 액세스하는 데 필요한 모든 연결 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-121">It includes all of the connection information necessary to access remote data from an OLE DB data source.</span></span> <span data-ttu-id="25340-122">`OPENROWSET`는 테이블 이름처럼 쿼리의 FROM 절에서 참조될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-122">`OPENROWSET` can be referenced in the FROM clause of a query as though it were a table name.</span></span> <span data-ttu-id="25340-123">또한 OLE DB 공급자의 기능에 따라 INSERT, UPDATE 또는 DELETE 문의 대상 테이블로 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-123">It can also be referenced as the target table of an INSERT, UPDATE, or DELETE statement, subject to the capabilities of the OLE DB provider.</span></span>  
  
 <span data-ttu-id="25340-124">`OPENROWSET` 함수에는 `BULK` 행 집합 공급자가 포함되어 있어 데이터를 대상 테이블에 로드하지 않고 파일에서 직접 데이터를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-124">The `OPENROWSET` function includes the `BULK` rowset provider, which allows you to read data directly from a file without loading the data into a target table.</span></span> <span data-ttu-id="25340-125">따라서 간단한 INSERT SELECT 문에서도 `OPENROWSET`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-125">This enables you to use `OPENROWSET` in a simple INSERT SELECT statement.</span></span>  
  
 <span data-ttu-id="25340-126">`OPENROWSET BULK` 선택적 인수를 사용하면 데이터 읽기의 시작 및 종료 지점, 오류 처리 방법 및 데이터 해석 방법을 효과적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-126">The `OPENROWSET BULK` option arguments provide significant control over where to begin and end reading data, how to deal with errors, and how data is interpreted.</span></span> <span data-ttu-id="25340-127">예를 들어 `varbinary`, `varchar` 또는 `nvarchar` 형식의 단일 행 및 단일 열로 된 행 집합으로 데이터 파일을 읽도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-127">For example, you can specify that the data file be read as a single-row, single-column rowset of type `varbinary`, `varchar`, or `nvarchar`.</span></span> <span data-ttu-id="25340-128">전체 구문 및 옵션에 대한 자세한 내용은 SQL Server 온라인 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25340-128">For the complete syntax and options, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="25340-129">다음 예제에서는 AdventureWorks 샘플 데이터베이스의 ProductPhoto 테이블에 사진을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-129">The following example inserts a photo into the ProductPhoto table in the AdventureWorks sample database.</span></span> <span data-ttu-id="25340-130">`BULK OPENROWSET` 공급자를 사용하는 경우 모든 열에 값을 삽입하지 않더라도 명명된 열 목록을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-130">When using the `BULK OPENROWSET` provider, you must supply the named list of columns even if you aren't inserting values into every column.</span></span> <span data-ttu-id="25340-131">이 경우 기본 키는 ID 열로 정의되며 열 목록에서 생략될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-131">The primary key in this case is defined as an identity column, and may be omitted from the column list.</span></span> <span data-ttu-id="25340-132">또한 `OPENROWSET` 문의 끝에 상관 관계 이름을 제공해야 합니다. 이 경우에는 ThumbnailPhoto입니다.</span><span class="sxs-lookup"><span data-stu-id="25340-132">Note that you must also supply a correlation name at the end of the `OPENROWSET` statement, which in this case is ThumbnailPhoto.</span></span> <span data-ttu-id="25340-133">이는 파일이 로드되는 `ProductPhoto` 테이블의 열과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-133">This correlates with the column in the `ProductPhoto` table into which the file is being loaded.</span></span>  
  
```sql  
INSERT Production.ProductPhoto (  
    ThumbnailPhoto,
    ThumbnailPhotoFilePath,
    LargePhoto,
    LargePhotoFilePath)  
SELECT ThumbnailPhoto.*, null, null, N'tricycle_pink.gif'  
FROM OPENROWSET
    (BULK 'c:\images\tricycle.jpg', SINGLE_BLOB) ThumbnailPhoto  
```  
  
## <a name="updating-data-using-update-write"></a><span data-ttu-id="25340-134">UPDATE .WRITE를 사용하여 데이터 업데이트</span><span class="sxs-lookup"><span data-stu-id="25340-134">Updating Data Using UPDATE .WRITE</span></span>  

 <span data-ttu-id="25340-135">Transact-SQL UPDATE 문에는 `varchar(max)`, `nvarchar(max)` 또는 `varbinary(max)` 열의 내용을 수정하기 위한 새로운 WRITE 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-135">The Transact-SQL UPDATE statement has new WRITE syntax for modifying the contents of `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` columns.</span></span> <span data-ttu-id="25340-136">이 구문을 사용하면 데이터 부분 업데이트를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-136">This allows you to perform partial updates of the data.</span></span> <span data-ttu-id="25340-137">UPDATE .WRITE 구문은 다음과 같이 축약된 형식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="25340-137">The UPDATE .WRITE syntax is shown here in abbreviated form:</span></span>  
  
 <span data-ttu-id="25340-138">UPDATE</span><span class="sxs-lookup"><span data-stu-id="25340-138">UPDATE</span></span>  
  
 <span data-ttu-id="25340-139">{ *\<object>* }</span><span class="sxs-lookup"><span data-stu-id="25340-139">{ *\<object>* }</span></span>  
  
 <span data-ttu-id="25340-140">SET</span><span class="sxs-lookup"><span data-stu-id="25340-140">SET</span></span>  
  
 <span data-ttu-id="25340-141">{ *column_name* = {. WRITE ( *expression* , @Offset , @Length )}</span><span class="sxs-lookup"><span data-stu-id="25340-141">{ *column_name* = { .WRITE ( *expression* , @Offset , @Length ) }</span></span>  
  
 <span data-ttu-id="25340-142">WRITE 메서드에서는 *column_name* 값의 일정 부분이 수정되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-142">The WRITE method specifies that a section of the value of the *column_name* will be modified.</span></span> <span data-ttu-id="25340-143">식은 *column_name*에 복사되는 값이고, `@Offset`은 식이 작성되는 시작점이며, `@Length` 인수는 열에 있는 일정 부분의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="25340-143">The expression is the value that will be copied to the *column_name*, the `@Offset` is the beginning point at which the expression will be written, and the `@Length` argument is the length of the section in the column.</span></span>  
  
|<span data-ttu-id="25340-144">조건</span><span class="sxs-lookup"><span data-stu-id="25340-144">If</span></span>|<span data-ttu-id="25340-145">결과</span><span class="sxs-lookup"><span data-stu-id="25340-145">Then</span></span>|  
|--------|----------|  
|<span data-ttu-id="25340-146">식이 NULL로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-146">The expression is set to NULL</span></span>|<span data-ttu-id="25340-147">`@Length`가 무시되고 *column_name*의 값은 지정된 `@Offset`에서 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="25340-147">`@Length` is ignored and the value in *column_name* is truncated at the specified `@Offset`.</span></span>|  
|<span data-ttu-id="25340-148">`@Offset`은 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="25340-148">`@Offset` is NULL</span></span>|<span data-ttu-id="25340-149">업데이트 작업을 통해 기존 *column_name* 값의 끝에 식이 추가되고 `@Length`는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="25340-149">The update operation appends the expression at the end of the existing *column_name* value and `@Length` is ignored.</span></span>|  
|<span data-ttu-id="25340-150">`@Offset`이 column_name 값의 길이 보다 큰 경우</span><span class="sxs-lookup"><span data-stu-id="25340-150">`@Offset` is greater than the length of the column_name value</span></span>|<span data-ttu-id="25340-151">SQL Server에서 오류를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-151">SQL Server returns an error.</span></span>|  
|<span data-ttu-id="25340-152">`@Length`은 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="25340-152">`@Length` is NULL</span></span>|<span data-ttu-id="25340-153">업데이트 작업 시 `@Offset`에서부터 `column_name` 값의 끝까지 모든 데이터를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-153">The update operation removes all data from `@Offset` to the end of the `column_name` value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="25340-154">`@Offset` 및 `@Length` 모두 음수일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-154">Neither `@Offset` nor `@Length` can be a negative number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25340-155">예제</span><span class="sxs-lookup"><span data-stu-id="25340-155">Example</span></span>  

 <span data-ttu-id="25340-156">이 Transact-SQL 예제는 AdventureWorks 데이터베이스의 Document 테이블에 있는 `nvarchar(max)` 열인 DocumentSummary에서 부분 값을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-156">This Transact-SQL example updates a partial value in DocumentSummary, an `nvarchar(max)` column in the Document table in the AdventureWorks database.</span></span> <span data-ttu-id="25340-157">대체 단어, 기존 데이터에서 대체할 단어의 시작 위치(오프셋), 그리고 대체할 문자 수(길이)를 지정함으로써 ‘구성 요소’가 로 ‘기능’으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="25340-157">The word 'components' is replaced by the word 'features' by specifying the replacement word, the beginning location (offset) of the word to be replaced in the existing data, and the number of characters to be replaced (length).</span></span> <span data-ttu-id="25340-158">예제에는 결과를 비교하기 위해 UPDATE 문 앞뒤에 SELECT 문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-158">The example includes SELECT statements before and after the UPDATE statement to compare results.</span></span>  
  
```sql
USE AdventureWorks;  
GO  
--View the existing value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety components of your bicycle.  
  
--Modify a single word in the DocumentSummary column  
UPDATE Production.Document  
SET DocumentSummary .WRITE (N'features',28,10)  
WHERE DocumentID = 3 ;  
GO
--View the modified value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety features of your bicycle.  
```  
  
## <a name="working-with-large-value-types-in-adonet"></a><span data-ttu-id="25340-159">ADO.NET에서 큰 값 형식 사용</span><span class="sxs-lookup"><span data-stu-id="25340-159">Working with Large-Value Types in ADO.NET</span></span>  

 <span data-ttu-id="25340-160">ADO.NET에서는 <xref:System.Data.SqlClient.SqlDataReader>에서 <xref:System.Data.SqlClient.SqlParameter> 개체로 지정하여 결과 집합을 반환하거나 <xref:System.Data.SqlClient.SqlDataAdapter>를 사용하여 `DataSet`/`DataTable`을 채우는 방식으로 큰 값 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-160">You can work with large value types in ADO.NET by specifying large value types as <xref:System.Data.SqlClient.SqlParameter> objects in a <xref:System.Data.SqlClient.SqlDataReader> to return a result set, or by using a <xref:System.Data.SqlClient.SqlDataAdapter> to fill a `DataSet`/`DataTable`.</span></span> <span data-ttu-id="25340-161">큰 값 형식을 사용하는 방식과 이와 관련된 작은 값 데이터 형식을 사용하는 방법에는 차이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-161">There is no difference between the way you work with a large value type and its related, smaller value data type.</span></span>  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a><span data-ttu-id="25340-162">GetSqlBytes를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="25340-162">Using GetSqlBytes to Retrieve Data</span></span>  

 <span data-ttu-id="25340-163"><xref:System.Data.SqlClient.SqlDataReader>의 `GetSqlBytes` 메서드를 사용하여 `varbinary(max)` 열의 내용을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-163">The `GetSqlBytes` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="25340-164">다음 코드 조각에서는 테이블에서 `varbinary(max)` 데이터를 선택하는 `cmd`라는 <xref:System.Data.SqlClient.SqlCommand> 개체와 <xref:System.Data.SqlTypes.SqlBytes>로 데이터를 검색하는 `reader`라는 <xref:System.Data.SqlClient.SqlDataReader> 개체를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-164">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as <xref:System.Data.SqlTypes.SqlBytes>.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim bytes As SqlBytes = reader.GetSqlBytes(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBytes bytes = reader.GetSqlBytes(0);  
    }  
```  
  
### <a name="using-getsqlchars-to-retrieve-data"></a><span data-ttu-id="25340-165">GetSqlChars를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="25340-165">Using GetSqlChars to Retrieve Data</span></span>  

 <span data-ttu-id="25340-166"><xref:System.Data.SqlClient.SqlDataReader>의 `GetSqlChars` 메서드를 사용하여 `varchar(max)` 또는 `nvarchar(max)` 열의 내용을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-166">The `GetSqlChars` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varchar(max)` or `nvarchar(max)` column.</span></span> <span data-ttu-id="25340-167">다음 코드 조각에서는 테이블에서 `nvarchar(max)` 데이터를 선택하는 `cmd`라는 <xref:System.Data.SqlClient.SqlCommand> 개체와 데이터를 검색하는 `reader`라는 <xref:System.Data.SqlClient.SqlDataReader> 개체를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-167">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `nvarchar(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim buffer As SqlChars = reader.GetSqlChars(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
{  
    SqlChars buffer = reader.GetSqlChars(0);  
}  
```  
  
### <a name="using-getsqlbinary-to-retrieve-data"></a><span data-ttu-id="25340-168">GetSqlBinary를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="25340-168">Using GetSqlBinary to Retrieve Data</span></span>  

 <span data-ttu-id="25340-169"><xref:System.Data.SqlClient.SqlDataReader>의 `GetSqlBinary` 메서드를 사용하여 `varbinary(max)` 열의 내용을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-169">The `GetSqlBinary` method of a <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="25340-170">다음 코드 조각에서는 테이블에서 `varbinary(max)` 데이터를 선택하는 `cmd`라는 <xref:System.Data.SqlClient.SqlCommand> 개체와 <xref:System.Data.SqlTypes.SqlBinary> 스트림으로 데이터를 검색하는 `reader`라는 <xref:System.Data.SqlClient.SqlDataReader> 개체를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-170">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as a <xref:System.Data.SqlTypes.SqlBinary> stream.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim binaryStream As SqlBinary = reader.GetSqlBinary(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBinary binaryStream = reader.GetSqlBinary(0);  
    }  
```  
  
### <a name="using-getbytes-to-retrieve-data"></a><span data-ttu-id="25340-171">GetBytes를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="25340-171">Using GetBytes to Retrieve Data</span></span>  

 <span data-ttu-id="25340-172"><xref:System.Data.SqlClient.SqlDataReader>의 `GetBytes` 메서드는 지정된 열 오프셋의 바이트 스트림을 지정된 배열 오프셋에서 시작하는 바이트 배열로 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="25340-172">The `GetBytes` method of a <xref:System.Data.SqlClient.SqlDataReader> reads a stream of bytes from the specified column offset into a byte array starting at the specified array offset.</span></span> <span data-ttu-id="25340-173">다음 코드 조각에서는 바이트를 바이트 배열로 검색하는 `reader`라는 <xref:System.Data.SqlClient.SqlDataReader> 개체를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-173">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves bytes into a byte array.</span></span> <span data-ttu-id="25340-174">`GetSqlBytes`와 달리 `GetBytes`에는 배열 버퍼의 크기가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-174">Note that, unlike `GetSqlBytes`, `GetBytes` requires a size for the array buffer.</span></span>  
  
```vb  
While reader.Read()  
    Dim buffer(4000) As Byte  
    Dim byteCount As Integer = _  
    CInt(reader.GetBytes(1, 0, buffer, 0, 4000))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    byte[] buffer = new byte[4000];  
    long byteCount = reader.GetBytes(1, 0, buffer, 0, 4000);  
}  
```  
  
### <a name="using-getvalue-to-retrieve-data"></a><span data-ttu-id="25340-175">GetValue를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="25340-175">Using GetValue to Retrieve Data</span></span>  

 <span data-ttu-id="25340-176"><xref:System.Data.SqlClient.SqlDataReader>의 `GetValue` 메서드는 지정된 열 오프셋에서 배열로 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-176">The `GetValue` method of a <xref:System.Data.SqlClient.SqlDataReader> reads the value from the specified column offset into an array.</span></span> <span data-ttu-id="25340-177">다음 코드 조각에서는 첫 번째 열 오프셋에서 이진 데이터를 검색한 다음 두 번째 열 오프셋에서 문자열 데이터를 검색하는 `reader`라는 <xref:System.Data.SqlClient.SqlDataReader> 개체를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-177">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves binary data from the first column offset, and then string data from the second column offset.</span></span>  
  
```vb  
While reader.Read()  
    ' Read the data from varbinary(max) column  
    Dim binaryData() As Byte = CByte(reader.GetValue(0))  
  
    ' Read the data from varchar(max) or nvarchar(max) column  
    Dim stringData() As String = Cstr((reader.GetValue(1))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    // Read the data from varbinary(max) column  
    byte[] binaryData = (byte[])reader.GetValue(0);  
  
    // Read the data from varchar(max) or nvarchar(max) column  
    String stringData = (String)reader.GetValue(1);  
}  
```  
  
## <a name="converting-from-large-value-types-to-clr-types"></a><span data-ttu-id="25340-178">큰 값 형식을 CLR 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="25340-178">Converting from Large Value Types to CLR Types</span></span>  

 <span data-ttu-id="25340-179">`ToString` 같은 문자열 변환 메서드를 사용하여 `varchar(max)` 또는 `nvarchar(max)` 열의 내용을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-179">You can convert the contents of a `varchar(max)` or `nvarchar(max)` column using any of the string conversion methods, such as `ToString`.</span></span> <span data-ttu-id="25340-180">다음 코드 조각에서는 데이터를 검색하는 `reader`라는 <xref:System.Data.SqlClient.SqlDataReader> 개체를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-180">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
While reader.Read()  
    Dim str as String = reader(0).ToString()  
    Console.WriteLine(str)  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
     string str = reader[0].ToString();  
     Console.WriteLine(str);  
}  
```  
  
### <a name="example"></a><span data-ttu-id="25340-181">예제</span><span class="sxs-lookup"><span data-stu-id="25340-181">Example</span></span>  

 <span data-ttu-id="25340-182">다음 코드는 `AdventureWorks` 데이터베이스의 `ProductPhoto` 테이블에서 이름 및 `LargePhoto` 개체를 검색하여 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-182">The following code retrieves the name and the `LargePhoto` object from the `ProductPhoto` table in the `AdventureWorks` database and saves it to a file.</span></span> <span data-ttu-id="25340-183">어셈블리는 <xref:System.Drawing> 네임스페이스에 대한 참조를 사용하여 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-183">The assembly needs to be compiled with a reference to the <xref:System.Drawing> namespace.</span></span>  <span data-ttu-id="25340-184"><xref:System.Data.SqlClient.SqlDataReader>의 <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> 메서드는 `Stream` 속성을 노출하는 <xref:System.Data.SqlTypes.SqlBytes> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-184">The <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> method of the <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.SqlTypes.SqlBytes> object that exposes a `Stream` property.</span></span> <span data-ttu-id="25340-185">코드에서는 이 개체를 사용하여 새 `Bitmap` 개체를 만든 다음 Gif `ImageFormat`으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-185">The code uses this to create a new `Bitmap` object, and then saves it in the Gif `ImageFormat`.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a><span data-ttu-id="25340-186">큰 값 형식 매개 변수 사용</span><span class="sxs-lookup"><span data-stu-id="25340-186">Using Large Value Type Parameters</span></span>  

 <span data-ttu-id="25340-187"><xref:System.Data.SqlClient.SqlParameter> 개체에서 더 작은 값 형식을 사용하는 것과 같은 방법으로 <xref:System.Data.SqlClient.SqlParameter> 개체에서 큰 값 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-187">Large value types can be used in <xref:System.Data.SqlClient.SqlParameter> objects the same way you use smaller value types in <xref:System.Data.SqlClient.SqlParameter> objects.</span></span> <span data-ttu-id="25340-188">다음 예제에서처럼 큰 값 형식은 <xref:System.Data.SqlClient.SqlParameter> 값으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25340-188">You can retrieve large value types as <xref:System.Data.SqlClient.SqlParameter> values, as shown in the following example.</span></span> <span data-ttu-id="25340-189">이 코드에서는 다음 GetDocumentSummary 저장 프로시저가 AdventureWorks 샘플 데이터베이스에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-189">The code assumes that the following GetDocumentSummary stored procedure exists in the AdventureWorks sample database.</span></span> <span data-ttu-id="25340-190">저장 프로시저는 @DocumentID라는 입력 매개 변수를 사용하여 @DocumentSummary 출력 매개 변수에 DocumentSummary 열의 내용을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-190">The stored procedure takes an input parameter named @DocumentID and returns the contents of the DocumentSummary column in the @DocumentSummary output parameter.</span></span>  
  
```sql
CREATE PROCEDURE GetDocumentSummary
(  
    @DocumentID int,  
    @DocumentSummary nvarchar(MAX) OUTPUT  
)  
AS  
SET NOCOUNT ON  
SELECT  @DocumentSummary=Convert(nvarchar(MAX), DocumentSummary)  
FROM    Production.Document  
WHERE   DocumentID=@DocumentID  
```  
  
### <a name="example"></a><span data-ttu-id="25340-191">예제</span><span class="sxs-lookup"><span data-stu-id="25340-191">Example</span></span>  

 <span data-ttu-id="25340-192">ADO.NET 코드는 <xref:System.Data.SqlClient.SqlConnection> 및 <xref:System.Data.SqlClient.SqlCommand> 개체를 만들어 GetDocumentSummary 저장 프로시저를 실행하고 문서 요약을 검색하여 큰 값 형식으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-192">The ADO.NET code creates <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to execute the GetDocumentSummary stored procedure and retrieve the document summary, which is stored as a large value type.</span></span> <span data-ttu-id="25340-193">이 코드에서는 @DocumentID 입력 매개 변수 값을 전달한 다음 콘솔 창에 @DocumentSummary 출력 매개 변수에 다시 전달된 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="25340-193">The code passes a value for the @DocumentID input parameter, and displays the results passed back in the @DocumentSummary output parameter in the Console window.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="25340-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25340-194">See also</span></span>

- [<span data-ttu-id="25340-195">이진 및 대량 값 데이터 SQL Server</span><span class="sxs-lookup"><span data-stu-id="25340-195">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="25340-196">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="25340-196">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="25340-197">ADO.NET의 SQL Server 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="25340-197">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="25340-198">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="25340-198">ADO.NET Overview</span></span>](../ado-net-overview.md)
