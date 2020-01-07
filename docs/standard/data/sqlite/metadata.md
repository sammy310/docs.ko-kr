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
# <a name="metadata"></a>메타데이터

ADO.NET에서 메타 데이터를 검색 하는 데는 두 가지 Api가 있습니다. 하나는 쿼리 결과에 대 한 메타 데이터를 검색 합니다. 다른는 데이터베이스 스키마에 대 한 메타 데이터를 검색 합니다.

## <a name="query-result-metadata"></a>쿼리 결과 메타 데이터

`SqliteDataReader`에서 <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> 메서드를 사용 하 여 쿼리 결과에 대 한 메타 데이터를 검색할 수 있습니다. 반환 된 <xref:System.Data.DataTable>에는 다음 열이 포함 됩니다.

| 열             | 형식    | 설명                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | Boolean | 원본 열이 NULL 일 수 있으면 True입니다.                                    |
| `BaseCatalogName`  | 문자열  | 원본 열 데이터베이스의 이름입니다. 식의 경우 항상 NULL입니다.    |
| `BaseColumnName`   | 문자열  | 원본 열의 unaliased 이름입니다. 식의 경우 항상 NULL입니다.    |
| `BaseSchemaName`   | 문자열  | 항상 NULL입니다. SQLite는 스키마를 지원 하지 않습니다.                              |
| `BaseServerName`   | 문자열  | 연결 문자열에 지정 된 데이터베이스 파일에 대 한 경로입니다.         |
| `BaseTableName`    | 문자열  | 원본 열의 테이블 이름입니다. 식의 경우 항상 NULL입니다.       |
| `ColumnName`       | 문자열  | 결과 집합에 있는 열의 이름 또는 별칭입니다.                        |
| `ColumnOrdinal`    | Int32   | 결과 집합의 열 서 수입니다.                              |
| `ColumnSize`       | Int32   | 항상-1입니다. 이는 `Microsoft.Data.Sqlite`의 이후 버전에서 변경 될 수 있습니다.   |
| `DataType`         | 형식    | 열의 기본 .NET 데이터 형식입니다.                                 |
| `DataTypeName`     | 문자열  | 열의 SQLite 데이터 형식입니다.                                       |
| `IsAliased`        | Boolean | 결과 집합에서 열 이름이 별칭으로 지정 되 면 True입니다.                     |
| `IsAutoIncrement`  | Boolean | 원본 열이 AUTOINCREMENT 키워드를 사용 하 여 만들어진 경우 True입니다.     |
| `IsExpression`     | Boolean | 열의 식이 쿼리에서 생성 된 경우 True입니다.            |
| `IsKey`            | Boolean | 원본 열이 기본 키의 일부 이면 True입니다.                     |
| `IsUnique`         | Boolean | 원본 열이 고유한 경우 True입니다.                                      |
| `NumericPrecision` | Int16   | 항상 NULL입니다. 이는 `Microsoft.Data.Sqlite`의 이후 버전에서 변경 될 수 있습니다. |
| `NumericScale`     | Int16   | 항상 NULL입니다. 이는 `Microsoft.Data.Sqlite`의 이후 버전에서 변경 될 수 있습니다. |

다음 예제에서는 `GetSchemaTable`를 사용 하 여 결과에 대 한 메타 데이터를 표시 하는 디버그 문자열을 만드는 방법을 보여 줍니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

예를 들어이 쿼리는 다음 디버그 문자열을 생성 합니다.

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

## <a name="schema-metadata"></a>스키마 메타 데이터

DbConnection에서 GetSchema 메서드를 구현 하지 않습니다. 대신 [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) 테이블 및 PRAGMA 문 (예: [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) 및 [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list))을 사용 하 여 스키마 정보를 직접 쿼리할 수 있습니다.

예를 들어이 쿼리는 데이터베이스의 모든 열에 대 한 메타 데이터를 검색 합니다.

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a>참조

* [SQL Database 스키마의 저장소](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [PRAGMA 문](https://www.sqlite.org/pragma.html)
* [데이터 형식](types.md)
