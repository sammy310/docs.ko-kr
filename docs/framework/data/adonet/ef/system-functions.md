---
title: 시스템 함수
ms.date: 03/30/2017
ms.assetid: b7c71b58-09e6-44ce-a3e5-a0fdb892fb86
ms.openlocfilehash: 9b5455d63dca40834515b14bae2f35d3b54d2aee
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452437"
---
# <a name="system-functions"></a>시스템 함수
.NET Framework Data Provider for SQL Server(SqlClient)에서는 다음 시스템 함수를 제공합니다.  
  
|함수|Description|  
|--------------|-----------------|  
|`CHECKSUM (` `value`, [`value`, [`value`]]`)`|체크섬 값을 반환합니다. `CHECKSUM`은 해시 인덱스를 작성하는 데 사용하기 위한 것입니다.<br /><br /> **인수**<br /><br /> `value`: `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `String`, `Binary`또는 `Guid`입니다. 한 개, 두 개 또는 세 개의 값을 지정할 수 있습니다.<br /><br /> **반환 값**<br /><br /> 지정한 식의 절대 값입니다.<br /><br /> **예제**<br /><br /> `SqlServer.CHECKSUM(10,100,1000.0)`|  
|`CURRENT_TIMESTAMP ()`|SQL Server 2008에서는 전체 자릿수가 7이고 SQL Server 2005에서는 전체 자릿수가 3인 `DateTime` 값의 SQL Server 내부 형식으로 현재 날짜와 시간을 생성합니다.<br /><br /> **반환 값**<br /><br /> `DateTime` 형식의 현재 시스템 날짜 및 시간입니다.<br /><br /> **예제**<br /><br /> `SqlServer.CURRENT_TIMESTAMP()`|  
|`CURRENT_ USER` `()`|현재 사용자의 이름을 반환합니다.<br /><br /> **반환 값**<br /><br /> ASCII `String`입니다.<br /><br /> **예제**<br /><br /> `SqlServer.CURRENT_USER()`|  
|`DATALENGTH` `(` `expression` `)`|식을 표시하는 데 사용된 바이트 수를 반환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`또는 `Guid`입니다.<br /><br /> **반환 값**<br /><br /> 속성의 크기를 나타내는 `Int32`입니다.<br /><br /> **예제**<br /><br /> `SELECT VALUE SqlServer.DATALENGTH(P.Name)FROM`<br /><br /> `AdventureWorksEntities.Product AS P`|  
|`HOST_NAME()`|워크스테이션 이름을 반환합니다.<br /><br /> **반환 값**<br /><br /> 유니코드 `String`입니다.<br /><br /> **예제**<br /><br /> `SqlServer.HOST_NAME()`|  
|`ISDATE(` `expression` `)`|입력 식이 유효한 날짜인지 여부를 확인합니다.<br /><br /> **인수**<br /><br /> `expression`: `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`또는 `Guid`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다. 입력 식이 유효한 날짜이면 1입니다. 그렇지 않으면 0입니다.<br /><br /> **예제**<br /><br /> `SqlServer.ISDATE('1/1/2006')`|  
|`ISNUMERIC(` `expression` `)`|식이 유효한 숫자 유형인지 여부를 지정합니다.<br /><br /> **인수**<br /><br /> `expression`: `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`또는 `Guid`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다. 입력 식이 유효한 날짜이면 1입니다. 그렇지 않으면 0입니다.<br /><br /> **예제**<br /><br /> `SqlServer.ISNUMERIC('21')`|  
|`NEWID()`|GUID 형식의 고유한 값을 만듭니다.<br /><br /> **반환 값**<br /><br /> `Guid`입니다.<br /><br /> **예제**<br /><br /> `SqlServer.NEWID()`|  
|`USER_NAME(` `id` `)`|지정된 ID 번호에서 데이터베이스 사용자 이름을 반환합니다.<br /><br /> **인수**<br /><br /> `expression`: 데이터베이스 사용자와 연결된 `Int32` ID 번호입니다.<br /><br /> **반환 값**<br /><br /> 유니코드 `String`입니다.<br /><br /> **예제**<br /><br /> `SqlServer.USER_NAME(0)`|  
  
 SqlClient에서 지 원하는 `String` 함수에 대 한 자세한 내용은 [문자열 함수 (transact-sql)](/sql/t-sql/functions/string-functions-transact-sql)를 참조 하세요.
  
## <a name="see-also"></a>참고 항목

- [Entity SQL 언어](./language-reference/entity-sql-language.md)
- [Entity Framework용 SqlClient 기능](sqlclient-for-ef-functions.md)
