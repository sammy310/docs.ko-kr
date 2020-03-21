---
title: 집계 함수(Entity Framework용 SqlClient)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 1fad25f2229b4fa810cf82a96dcb8c50a9de3070
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150651"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>집계 함수(Entity Framework용 SqlClient)
.NET Framework Data Provider for SQL Server(SqlClient)에서는 집계 함수를 제공합니다. 집계 함수는 입력 값 집합에 대해 계산을 수행하여 하나의 값을 반환합니다. 이 함수는 SqlClient를 사용할 때 사용 가능한 SqlServer 네임스페이스에 있습니다. 공급자의 네임스페이스 속성이 있으면 특정 구문(예: 형식 및 함수)에 대해 이 공급자가 사용하는 접두사를 Entity Framework에서 찾을 수 있습니다.  
  
 다음은 SqlClient 집계 함수입니다.  

## <a name="avgexpression"></a>AVG(식)

컬렉션에 포함된 값의 평균을 반환합니다. Null 값은 무시됩니다.

**인수**

`Int32`, `Int64`, `Double` 및 `Decimal`입니다.

**반환 값**

`expression`의 형식입니다.

**예제**

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a>CHECKSUM_AGG(컬렉션)

 컬렉션에 있는 값의 체크섬을 반환합니다. Null 값은 무시됩니다.

 **인수**

 컬렉션().`Int32`

 **반환 값**

 `Int32`입니다.

 **예제**

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a>COUNT(식)

컬렉션의 항목 수를 `Int32`로 반환합니다.

**인수**

컬렉션\<T는 다음 유형 중 하나인 컬렉션 t>.

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid`(SQL Server 2000에서 반환되지 않음)|

**반환 값**

`Int32`입니다.

**예제**

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a>COUNT_BIG(식)

컬렉션의 항목 수를 `bigint`로 반환합니다.

 **인수**

 T가 다음 유형 중 하나인 컬렉션(T)은 다음과 같은 유형 중 하나입니다.

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid`(SQL Server 2000에서 반환되지 않음)|

**반환 값**

`Int64`입니다.

**예제**

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a>MAX(표현식)

컬렉션의 최대값을 반환합니다.

**인수**

T가 다음 유형 중 하나인 컬렉션(T)은 다음과 같은 유형 중 하나입니다.

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**반환 값**

`expression`의 형식입니다.

**예제**

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a>MIN(표현식)

컬렉션의 최소값을 반환합니다.

**인수**

T가 다음 유형 중 하나인 컬렉션(T)은 다음과 같은 유형 중 하나입니다.

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**반환 값**

`expression`의 형식입니다.

**예제**

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a>STDEV(표현식)

지정한 식의 모든 값에 대한 통계적 표준 편차를 반환합니다.

**인수**

컬렉션().`Double`

**반환 값**

`Double`입니다.

**예제**

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a>STDEVP(표현식)

지정한 식에 있는 모든 값의 모집단에 대한 통계적 표준 편차를 반환합니다.

**인수**

컬렉션().`Double`

**반환 값**

`Double`입니다.

**예제**

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a>SUM(표현식)

컬렉션에 있는 모든 값의 합계를 반환합니다.

**인수**

T가 다음 유형 중 하나인 컬렉션(T) `Int64` `Double`: `Decimal` `Int32`.

**반환 값**

`expression`의 형식입니다.

**예제**

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a>VAR(표현식)

지정한 식에 있는 모든 값의 통계적 분산을 반환합니다.

**인수**

컬렉션().`Double`

**반환 값**

`Double`입니다.

**예제**

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a>VARP(표현식)

지정한 식에 있는 모든 값의 모집단에 대한 통계적 분산을 반환합니다.

**인수**

컬렉션().`Double`

**반환 값**

`Double`입니다.

**예제**

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a>참고 항목

- [집계 함수(Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [Entity SQL 언어](./language-reference/entity-sql-language.md)
- [집계 정식 함수](./language-reference/aggregate-canonical-functions.md)
