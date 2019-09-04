---
title: 집계 함수(Entity Framework용 SqlClient)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: cf476192cf049f230c1956e390d215ad4abaa821
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251700"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>집계 함수(Entity Framework용 SqlClient)
.NET Framework Data Provider for SQL Server(SqlClient)에서는 집계 함수를 제공합니다. 집계 함수는 입력 값 집합에 대해 계산을 수행하여 하나의 값을 반환합니다. 이 함수는 SqlClient를 사용할 때 사용 가능한 SqlServer 네임스페이스에 있습니다. 공급자의 네임스페이스 속성이 있으면 특정 구문(예: 형식 및 함수)에 대해 이 공급자가 사용하는 접두사를 Entity Framework에서 찾을 수 있습니다.  
  
 다음은 SqlClient 집계 함수입니다.  

## <a name="avgexpression"></a>AVG (expression)

컬렉션에 포함된 값의 평균을 반환합니다. Null 값은 무시됩니다.

**인수**

`Int32`, `Int64`, `Double` 및 `Decimal`입니다.

**반환 값**

`expression`의 형식입니다.

**예제**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a>CHECKSUM_AGG (collection)
 
 컬렉션에 있는 값의 체크섬을 반환합니다. Null 값은 무시됩니다.
 
 **인수**
 
 컬렉션 (`Int32`)입니다.
 
 **반환 값**
 
 `Int32`입니다.
 
 **예제**
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a>COUNT (식)

컬렉션의 항목 수를 `Int32`로 반환합니다.

**인수**

컬렉션\<t >입니다. 여기서 t는 다음 형식 중 하나입니다.

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid`(SQL Server 2000에서 반환 되지 않음)|

**반환 값**

`Int32`입니다.

**예제**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)
 
## <a name="count_bigexpression"></a>COUNT_BIG (식)
 
 컬렉션의 항목 수를 `bigint`로 반환합니다.
 
 **인수**
 
 컬렉션 (T) 이며, 여기서 T는 다음 형식 중 하나입니다.
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid`(SQL Server 2000에서 반환 되지 않음)|

**반환 값**

`Int64`입니다.

**예제**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a>MAX (expression)

컬렉션의 최대값을 반환합니다.

**인수**

컬렉션 (T) 이며, 여기서 T는 다음 형식 중 하나입니다. 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**반환 값**

`expression`의 형식입니다.

**예제**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a>MIN (expression)

컬렉션의 최소값을 반환합니다.

**인수**

컬렉션 (T) 이며, 여기서 T는 다음 형식 중 하나입니다. 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**반환 값**

`expression`의 형식입니다.

**예제**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a>STDEV (식)

지정한 식의 모든 값에 대한 통계적 표준 편차를 반환합니다.

**인수**

컬렉션 (`Double`)입니다.

**반환 값**

`Double`

**예제**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a>STDEVP (식)

지정한 식에 있는 모든 값의 모집단에 대한 통계적 표준 편차를 반환합니다.

**인수**

컬렉션 (`Double`)입니다.

**반환 값**

`Double`

**예제**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a>합계 (식)

컬렉션에 있는 모든 값의 합계를 반환합니다.

**인수**

컬렉션 (T) 이며, `Int32`여기서 t는, `Int64`, `Double`, `Decimal`형식 중 하나입니다.

**반환 값**

`expression`의 형식입니다.

**예제**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a>VAR (expression)

지정한 식에 있는 모든 값의 통계적 분산을 반환합니다.

**인수**

컬렉션 (`Double`)입니다.

**반환 값**

`Double`

**예제**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a>VARP (식)

지정한 식에 있는 모든 값의 모집단에 대한 통계적 분산을 반환합니다.

**인수**

컬렉션 (`Double`)입니다.

**반환 값**

`Double`

**예제**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a>참고자료

SqlClient에서 지원하는 집계 함수에 대한 자세한 내용은 SqlClient 공급자 매니페스트에 지정한 SQL Server 버전의 설명서를 참조하세요.

- **SQL Server 2005:** [집계 함수 (Transact-sql)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))
- **SQL Server 2008 이상:** [집계 함수 (Transact-sql)](/sql/t-sql/functions/aggregate-functions-transact-sql)

- [Entity SQL 언어](./language-reference/entity-sql-language.md)
- [집계 정식 함수](./language-reference/aggregate-canonical-functions.md)
