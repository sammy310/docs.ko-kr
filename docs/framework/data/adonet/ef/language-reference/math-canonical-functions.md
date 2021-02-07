---
description: '자세한 정보: 수학 정식 함수'
title: 수학 정식 함수
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 55072099f5766d48ea3067a2e9eaa187a8b3f111
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739367"
---
# <a name="math-canonical-functions"></a>수학 정식 함수

Entity SQL는 다음과 같은 수학 정식 함수를 포함 합니다.
  
## <a name="absvalue"></a>Abs(value)

`value`의 절대값을 반환합니다.

**인수**

,,,,, `Int16` `Int32` `Int64` `Byte` `Single` `Double` 및 `Decimal` 입니다.

**Return Value**

`value`의 형식입니다.

**예제**

`Abs(-2)`

## <a name="ceilingvalue"></a>Ceiling(value)

`value`보다 작지 않은 가장 작은 정수를 반환합니다.

**인수**

`Single`, `Double` 및 `Decimal` 입니다.

**Return Value**

`value`의 형식입니다.

**예제**

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a>Floor(value)

`value`보다 크지 않은 가장 큰 정수를 반환합니다.

**인수**

`Single`, `Double` 및 `Decimal` 입니다.

**Return Value**

`value`의 형식입니다.

**예제**

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a>Power(value, exponent)

지정된 `value`에 대해 지정된 `exponent`의 결과를 반환합니다.

**인수**

|  |  |
|--|--|
|`value` | `Int32, Int64, Double` 또는 `Decimal`입니다. |
|`exponent` | `Int64`, `Double` 또는 `Decimal` 입니다. |

**Return Value**

`value`의 형식입니다.

**예제**

`Power(748.58,2)`

## <a name="roundvalue"></a>Round(value)

`value`의 정수 부분을 가장 가까운 정수로 반올림하여 반환합니다.

**인수**

`Single`, `Double` 및 `Decimal` 입니다.

**Return Value**

`value`의 형식입니다.

**예제**

`Round(748.58)`

## <a name="roundvalue-digits"></a>Round(value, digits)

`value`를 지정된 `digits` 중 가장 가까운 숫자로 반올림하여 반환합니다.

**인수**

|  |  |
|--|--|
|`value`|`Double` 또는 `Decimal`|
|`digits`|`Int16` 또는 `Int32`|

**Return Value**

`value`의 형식입니다.

**예제**

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a>Truncate(value, digits)

`value`를 지정된 `digits` 중 가장 가까운 숫자로 잘라 반환합니다.

**인수**

|  |  |
|--|--|
|`value`|`Double` 또는 `Decimal`|
|`digits`|`Int16` 또는 `Int32`|

**Return Value**

`value`의 형식입니다.

**예제**

`Truncate(748.58,1)`  
  
 이러한 함수는 `null`이 입력되면 `null`을 반환합니다.  
  
 동일한 기능을 Microsoft SQL 클라이언트 관리 공급자에서 사용할 수 있습니다. 자세한 내용은 [Entity Framework 함수에 대 한 SqlClient](../sqlclient-for-ef-functions.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [정식 함수](canonical-functions.md)
