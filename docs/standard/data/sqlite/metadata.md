---
title: 메타데이터
ms.date: 12/13/2019
description: 데이터베이스에 대 한 메타 데이터를 검색 하는 방법을 알아봅니다.
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450431"
---
# <a name="metadata"></a><span data-ttu-id="7e0d3-103">메타데이터</span><span class="sxs-lookup"><span data-stu-id="7e0d3-103">Metadata</span></span>

<span data-ttu-id="7e0d3-104">ADO.NET에서 메타 데이터를 검색 하는 데는 두 가지 Api가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-104">There are two APIs for retrieving metadata in ADO.NET.</span></span> <span data-ttu-id="7e0d3-105">하나는 쿼리 결과에 대 한 메타 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-105">One retrieves metadata about query results.</span></span> <span data-ttu-id="7e0d3-106">다른는 데이터베이스 스키마에 대 한 메타 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-106">The other retrieves metadata about the database schema.</span></span>

## <a name="query-result-metadata"></a><span data-ttu-id="7e0d3-107">쿼리 결과 메타 데이터</span><span class="sxs-lookup"><span data-stu-id="7e0d3-107">Query result metadata</span></span>

<span data-ttu-id="7e0d3-108">`SqliteDataReader`에서 <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> 메서드를 사용 하 여 쿼리 결과에 대 한 메타 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-108">You can retrieve metadata about the results of a query using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method on `SqliteDataReader`.</span></span> <span data-ttu-id="7e0d3-109">반환 된 <xref:System.Data.DataTable>에는 다음 열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-109">The returned <xref:System.Data.DataTable> contains the following columns:</span></span>

| <span data-ttu-id="7e0d3-110">열</span><span class="sxs-lookup"><span data-stu-id="7e0d3-110">Column</span></span>             | <span data-ttu-id="7e0d3-111">형식</span><span class="sxs-lookup"><span data-stu-id="7e0d3-111">Type</span></span>    | <span data-ttu-id="7e0d3-112">설명</span><span class="sxs-lookup"><span data-stu-id="7e0d3-112">Description</span></span>                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | <span data-ttu-id="7e0d3-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="7e0d3-113">Boolean</span></span> | <span data-ttu-id="7e0d3-114">원본 열이 NULL 일 수 있으면 True입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-114">True if the origin column may be NULL.</span></span>                                    |
| `BaseCatalogName`  | <span data-ttu-id="7e0d3-115">문자열</span><span class="sxs-lookup"><span data-stu-id="7e0d3-115">String</span></span>  | <span data-ttu-id="7e0d3-116">원본 열 데이터베이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-116">The name of the origin column's database.</span></span> <span data-ttu-id="7e0d3-117">식의 경우 항상 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-117">Always NULL for expressions.</span></span>    |
| `BaseColumnName`   | <span data-ttu-id="7e0d3-118">문자열</span><span class="sxs-lookup"><span data-stu-id="7e0d3-118">String</span></span>  | <span data-ttu-id="7e0d3-119">원본 열의 unaliased 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-119">The unaliased name of the origin column.</span></span> <span data-ttu-id="7e0d3-120">식의 경우 항상 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-120">Always NULL for expressions.</span></span>    |
| `BaseSchemaName`   | <span data-ttu-id="7e0d3-121">문자열</span><span class="sxs-lookup"><span data-stu-id="7e0d3-121">String</span></span>  | <span data-ttu-id="7e0d3-122">항상 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-122">Always NULL.</span></span> <span data-ttu-id="7e0d3-123">SQLite는 스키마를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-123">SQLite doesn't support schemas.</span></span>                              |
| `BaseServerName`   | <span data-ttu-id="7e0d3-124">문자열</span><span class="sxs-lookup"><span data-stu-id="7e0d3-124">String</span></span>  | <span data-ttu-id="7e0d3-125">연결 문자열에 지정 된 데이터베이스 파일에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-125">The path to the database file specified in the connection string.</span></span>         |
| `BaseTableName`    | <span data-ttu-id="7e0d3-126">문자열</span><span class="sxs-lookup"><span data-stu-id="7e0d3-126">String</span></span>  | <span data-ttu-id="7e0d3-127">원본 열의 테이블 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-127">The name of the origin column's table.</span></span> <span data-ttu-id="7e0d3-128">식의 경우 항상 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-128">Always NULL for expressions.</span></span>       |
| `ColumnName`       | <span data-ttu-id="7e0d3-129">문자열</span><span class="sxs-lookup"><span data-stu-id="7e0d3-129">String</span></span>  | <span data-ttu-id="7e0d3-130">결과 집합에 있는 열의 이름 또는 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-130">The name or alias of the column in the result set.</span></span>                        |
| `ColumnOrdinal`    | <span data-ttu-id="7e0d3-131">Int32</span><span class="sxs-lookup"><span data-stu-id="7e0d3-131">Int32</span></span>   | <span data-ttu-id="7e0d3-132">결과 집합의 열 서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-132">The ordinal of the column in the result set.</span></span>                              |
| `ColumnSize`       | <span data-ttu-id="7e0d3-133">Int32</span><span class="sxs-lookup"><span data-stu-id="7e0d3-133">Int32</span></span>   | <span data-ttu-id="7e0d3-134">항상-1입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-134">Always -1.</span></span> <span data-ttu-id="7e0d3-135">이는 `Microsoft.Data.Sqlite`의 이후 버전에서 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-135">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span>   |
| `DataType`         | <span data-ttu-id="7e0d3-136">형식</span><span class="sxs-lookup"><span data-stu-id="7e0d3-136">Type</span></span>    | <span data-ttu-id="7e0d3-137">열의 기본 .NET 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-137">The default .NET data type of the column.</span></span>                                 |
| `DataTypeName`     | <span data-ttu-id="7e0d3-138">문자열</span><span class="sxs-lookup"><span data-stu-id="7e0d3-138">String</span></span>  | <span data-ttu-id="7e0d3-139">열의 SQLite 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-139">The SQLite data type of the column.</span></span>                                       |
| `IsAliased`        | <span data-ttu-id="7e0d3-140">Boolean</span><span class="sxs-lookup"><span data-stu-id="7e0d3-140">Boolean</span></span> | <span data-ttu-id="7e0d3-141">결과 집합에서 열 이름이 별칭으로 지정 되 면 True입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-141">True if the column name is aliased in the result set.</span></span>                     |
| `IsAutoIncrement`  | <span data-ttu-id="7e0d3-142">Boolean</span><span class="sxs-lookup"><span data-stu-id="7e0d3-142">Boolean</span></span> | <span data-ttu-id="7e0d3-143">원본 열이 AUTOINCREMENT 키워드를 사용 하 여 만들어진 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-143">True if the origin column was created with the AUTOINCREMENT keyword.</span></span>     |
| `IsExpression`     | <span data-ttu-id="7e0d3-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="7e0d3-144">Boolean</span></span> | <span data-ttu-id="7e0d3-145">열의 식이 쿼리에서 생성 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-145">True if the column originates from an expression in the query.</span></span>            |
| `IsKey`            | <span data-ttu-id="7e0d3-146">Boolean</span><span class="sxs-lookup"><span data-stu-id="7e0d3-146">Boolean</span></span> | <span data-ttu-id="7e0d3-147">원본 열이 기본 키의 일부 이면 True입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-147">True if the origin column is part of the PRIMARY KEY.</span></span>                     |
| `IsUnique`         | <span data-ttu-id="7e0d3-148">Boolean</span><span class="sxs-lookup"><span data-stu-id="7e0d3-148">Boolean</span></span> | <span data-ttu-id="7e0d3-149">원본 열이 고유한 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-149">True if the origin column is UNIQUE.</span></span>                                      |
| `NumericPrecision` | <span data-ttu-id="7e0d3-150">Int16</span><span class="sxs-lookup"><span data-stu-id="7e0d3-150">Int16</span></span>   | <span data-ttu-id="7e0d3-151">항상 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-151">Always NULL.</span></span> <span data-ttu-id="7e0d3-152">이는 `Microsoft.Data.Sqlite`의 이후 버전에서 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-152">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |
| `NumericScale`     | <span data-ttu-id="7e0d3-153">Int16</span><span class="sxs-lookup"><span data-stu-id="7e0d3-153">Int16</span></span>   | <span data-ttu-id="7e0d3-154">항상 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-154">Always NULL.</span></span> <span data-ttu-id="7e0d3-155">이는 `Microsoft.Data.Sqlite`의 이후 버전에서 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-155">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |

<span data-ttu-id="7e0d3-156">다음 예제에서는 `GetSchemaTable`를 사용 하 여 결과에 대 한 메타 데이터를 표시 하는 디버그 문자열을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-156">The following example shows how to use `GetSchemaTable` to create a debug string that shows metadata about a result:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

<span data-ttu-id="7e0d3-157">예를 들어이 쿼리는 다음 디버그 문자열을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-157">For example, this query would produce the following debug string:</span></span>

```sql
SELECT id AS post_id,
       title,
       body,
       random() AS random
FROM post
```

```output
post.id AS post_id INTEGER PRIMARY KEY AUTOINCREMENT
post.title TEXT NOT NULL UNIQUE
post.body TEXT
(expression) AS random BLOB
```

## <a name="schema-metadata"></a><span data-ttu-id="7e0d3-158">스키마 메타 데이터</span><span class="sxs-lookup"><span data-stu-id="7e0d3-158">Schema metadata</span></span>

<span data-ttu-id="7e0d3-159">DbConnection에서 GetSchema 메서드를 구현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-159">Microsoft.Data.Sqlite doesn't implement the GetSchema method on DbConnection.</span></span> <span data-ttu-id="7e0d3-160">대신 [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) 테이블 및 PRAGMA 문 (예: [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) 및 [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list))을 사용 하 여 스키마 정보를 직접 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-160">Instead, you can query directly for schema information using the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and PRAGMA statements like [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) and [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span></span>

<span data-ttu-id="7e0d3-161">예를 들어이 쿼리는 데이터베이스의 모든 열에 대 한 메타 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0d3-161">For example, this query will retrieve metadata about all the columns in the database.</span></span>

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a><span data-ttu-id="7e0d3-162">참조</span><span class="sxs-lookup"><span data-stu-id="7e0d3-162">See also</span></span>

* [<span data-ttu-id="7e0d3-163">SQL Database 스키마의 저장소</span><span class="sxs-lookup"><span data-stu-id="7e0d3-163">Storage of the SQL Database Schema</span></span>](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [<span data-ttu-id="7e0d3-164">PRAGMA 문</span><span class="sxs-lookup"><span data-stu-id="7e0d3-164">PRAGMA Statements</span></span>](https://www.sqlite.org/pragma.html)
* [<span data-ttu-id="7e0d3-165">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7e0d3-165">Data types</span></span>](types.md)
