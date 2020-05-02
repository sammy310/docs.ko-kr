---
title: 메타데이터
ms.date: 12/13/2019
description: 데이터베이스에 대한 메타데이터를 검색하는 방법에 대해 알아봅니다.
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450431"
---
# <a name="metadata"></a><span data-ttu-id="46695-103">메타데이터</span><span class="sxs-lookup"><span data-stu-id="46695-103">Metadata</span></span>

<span data-ttu-id="46695-104">ADO.NET에서 메타데이터를 검색하기 위한 두 가지 API가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46695-104">There are two APIs for retrieving metadata in ADO.NET.</span></span> <span data-ttu-id="46695-105">하나는 쿼리 결과에 대한 메타데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="46695-105">One retrieves metadata about query results.</span></span> <span data-ttu-id="46695-106">다른 하나는 데이터베이스 스키마에 대한 메타데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="46695-106">The other retrieves metadata about the database schema.</span></span>

## <a name="query-result-metadata"></a><span data-ttu-id="46695-107">쿼리 결과 메타데이터</span><span class="sxs-lookup"><span data-stu-id="46695-107">Query result metadata</span></span>

<span data-ttu-id="46695-108">`SqliteDataReader`에서 <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> 메서드를 사용하여 쿼리 결과에 대한 메타데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46695-108">You can retrieve metadata about the results of a query using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method on `SqliteDataReader`.</span></span> <span data-ttu-id="46695-109">반환된 <xref:System.Data.DataTable>에는 다음과 같은 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46695-109">The returned <xref:System.Data.DataTable> contains the following columns:</span></span>

| <span data-ttu-id="46695-110">Column</span><span class="sxs-lookup"><span data-stu-id="46695-110">Column</span></span>             | <span data-ttu-id="46695-111">형식</span><span class="sxs-lookup"><span data-stu-id="46695-111">Type</span></span>    | <span data-ttu-id="46695-112">설명</span><span class="sxs-lookup"><span data-stu-id="46695-112">Description</span></span>                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | <span data-ttu-id="46695-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="46695-113">Boolean</span></span> | <span data-ttu-id="46695-114">원본 열이 NULL일 수 있으면 True입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-114">True if the origin column may be NULL.</span></span>                                    |
| `BaseCatalogName`  | <span data-ttu-id="46695-115">String</span><span class="sxs-lookup"><span data-stu-id="46695-115">String</span></span>  | <span data-ttu-id="46695-116">원본 열의 데이터베이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-116">The name of the origin column's database.</span></span> <span data-ttu-id="46695-117">식의 경우 항상 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-117">Always NULL for expressions.</span></span>    |
| `BaseColumnName`   | <span data-ttu-id="46695-118">String</span><span class="sxs-lookup"><span data-stu-id="46695-118">String</span></span>  | <span data-ttu-id="46695-119">원본 열의 unaliased 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-119">The unaliased name of the origin column.</span></span> <span data-ttu-id="46695-120">식의 경우 항상 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-120">Always NULL for expressions.</span></span>    |
| `BaseSchemaName`   | <span data-ttu-id="46695-121">String</span><span class="sxs-lookup"><span data-stu-id="46695-121">String</span></span>  | <span data-ttu-id="46695-122">항상 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-122">Always NULL.</span></span> <span data-ttu-id="46695-123">SQLite는 스키마를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46695-123">SQLite doesn't support schemas.</span></span>                              |
| `BaseServerName`   | <span data-ttu-id="46695-124">String</span><span class="sxs-lookup"><span data-stu-id="46695-124">String</span></span>  | <span data-ttu-id="46695-125">연결 문자열에 지정된 데이터베이스 파일에 대한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-125">The path to the database file specified in the connection string.</span></span>         |
| `BaseTableName`    | <span data-ttu-id="46695-126">String</span><span class="sxs-lookup"><span data-stu-id="46695-126">String</span></span>  | <span data-ttu-id="46695-127">원본 열의 테이블 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-127">The name of the origin column's table.</span></span> <span data-ttu-id="46695-128">식의 경우 항상 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-128">Always NULL for expressions.</span></span>       |
| `ColumnName`       | <span data-ttu-id="46695-129">String</span><span class="sxs-lookup"><span data-stu-id="46695-129">String</span></span>  | <span data-ttu-id="46695-130">결과 집합에 있는 열의 이름 또는 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-130">The name or alias of the column in the result set.</span></span>                        |
| `ColumnOrdinal`    | <span data-ttu-id="46695-131">Int32</span><span class="sxs-lookup"><span data-stu-id="46695-131">Int32</span></span>   | <span data-ttu-id="46695-132">결과 집합에 있는 열의 서수입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-132">The ordinal of the column in the result set.</span></span>                              |
| `ColumnSize`       | <span data-ttu-id="46695-133">Int32</span><span class="sxs-lookup"><span data-stu-id="46695-133">Int32</span></span>   | <span data-ttu-id="46695-134">항상 -1입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-134">Always -1.</span></span> <span data-ttu-id="46695-135">이는 `Microsoft.Data.Sqlite`의 이후 버전에서 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46695-135">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span>   |
| `DataType`         | <span data-ttu-id="46695-136">형식</span><span class="sxs-lookup"><span data-stu-id="46695-136">Type</span></span>    | <span data-ttu-id="46695-137">열의 기본 .NET 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-137">The default .NET data type of the column.</span></span>                                 |
| `DataTypeName`     | <span data-ttu-id="46695-138">String</span><span class="sxs-lookup"><span data-stu-id="46695-138">String</span></span>  | <span data-ttu-id="46695-139">열의 SQLite 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-139">The SQLite data type of the column.</span></span>                                       |
| `IsAliased`        | <span data-ttu-id="46695-140">Boolean</span><span class="sxs-lookup"><span data-stu-id="46695-140">Boolean</span></span> | <span data-ttu-id="46695-141">결과 집합에서 열 이름이 별칭이면 True입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-141">True if the column name is aliased in the result set.</span></span>                     |
| `IsAutoIncrement`  | <span data-ttu-id="46695-142">Boolean</span><span class="sxs-lookup"><span data-stu-id="46695-142">Boolean</span></span> | <span data-ttu-id="46695-143">원본 열이 AUTOINCREMENT 키워드로 만들어진 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-143">True if the origin column was created with the AUTOINCREMENT keyword.</span></span>     |
| `IsExpression`     | <span data-ttu-id="46695-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="46695-144">Boolean</span></span> | <span data-ttu-id="46695-145">열이 쿼리의 식에서 생성된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-145">True if the column originates from an expression in the query.</span></span>            |
| `IsKey`            | <span data-ttu-id="46695-146">Boolean</span><span class="sxs-lookup"><span data-stu-id="46695-146">Boolean</span></span> | <span data-ttu-id="46695-147">원본 열이 기본 키의 일부이면 True입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-147">True if the origin column is part of the PRIMARY KEY.</span></span>                     |
| `IsUnique`         | <span data-ttu-id="46695-148">Boolean</span><span class="sxs-lookup"><span data-stu-id="46695-148">Boolean</span></span> | <span data-ttu-id="46695-149">원본 열이 고유한 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-149">True if the origin column is UNIQUE.</span></span>                                      |
| `NumericPrecision` | <span data-ttu-id="46695-150">Int16</span><span class="sxs-lookup"><span data-stu-id="46695-150">Int16</span></span>   | <span data-ttu-id="46695-151">항상 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-151">Always NULL.</span></span> <span data-ttu-id="46695-152">이는 `Microsoft.Data.Sqlite`의 이후 버전에서 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46695-152">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |
| `NumericScale`     | <span data-ttu-id="46695-153">Int16</span><span class="sxs-lookup"><span data-stu-id="46695-153">Int16</span></span>   | <span data-ttu-id="46695-154">항상 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="46695-154">Always NULL.</span></span> <span data-ttu-id="46695-155">이는 `Microsoft.Data.Sqlite`의 이후 버전에서 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46695-155">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |

<span data-ttu-id="46695-156">다음 예제에서는 `GetSchemaTable`을 사용하여 결과에 대한 메타데이터를 표시하는 디버그 문자열을 만드는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="46695-156">The following example shows how to use `GetSchemaTable` to create a debug string that shows metadata about a result:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

<span data-ttu-id="46695-157">예를 들어 이 쿼리는 다음과 같은 디버그 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="46695-157">For example, this query would produce the following debug string:</span></span>

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

## <a name="schema-metadata"></a><span data-ttu-id="46695-158">스키마 메타데이터</span><span class="sxs-lookup"><span data-stu-id="46695-158">Schema metadata</span></span>

<span data-ttu-id="46695-159">Microsoft.Data.Sqlite는 DbConnection에서 GetSchema 메서드를 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46695-159">Microsoft.Data.Sqlite doesn't implement the GetSchema method on DbConnection.</span></span> <span data-ttu-id="46695-160">대신 [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) 테이블과 PRAGMA 문(예: [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) 및 [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list))을 사용하여 스키마 정보를 직접 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46695-160">Instead, you can query directly for schema information using the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and PRAGMA statements like [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) and [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span></span>

<span data-ttu-id="46695-161">예를 들어 이 쿼리는 데이터베이스의 모든 열에 대한 메타데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="46695-161">For example, this query will retrieve metadata about all the columns in the database.</span></span>

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a><span data-ttu-id="46695-162">참조</span><span class="sxs-lookup"><span data-stu-id="46695-162">See also</span></span>

* [<span data-ttu-id="46695-163">SQL Database 스키마의 스토리지</span><span class="sxs-lookup"><span data-stu-id="46695-163">Storage of the SQL Database Schema</span></span>](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [<span data-ttu-id="46695-164">PRAGMA 문</span><span class="sxs-lookup"><span data-stu-id="46695-164">PRAGMA Statements</span></span>](https://www.sqlite.org/pragma.html)
* [<span data-ttu-id="46695-165">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="46695-165">Data types</span></span>](types.md)
