---
title: 날짜 및 시간 함수
ms.date: 03/30/2017
ms.assetid: 971762d0-663b-4b64-8c61-352a8e6d3949
ms.openlocfilehash: aa024ad748db26cb75111984abdb61fdbd538ef9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198458"
---
# <a name="date-and-time-functions"></a>날짜 및 시간 함수

.NET Framework Data Provider for SQL Server(SqlClient)에서는 `System.DateTime` 입력 값에 대해 연산을 수행하고 `string`, 숫자 또는 `System.DateTime` 값 결과를 반환하는 날짜 및 시간 함수를 제공합니다. 이 함수는 SqlClient를 사용할 때 사용 가능한 SqlServer 네임스페이스에 있습니다. 공급자의 네임스페이스 속성이 있으면 특정 구문(예: 형식 및 함수)에 대해 이 공급자가 사용하는 접두사를 Entity Framework에서 찾을 수 있습니다. 다음 표에서는 SqlClient 날짜 및 시간 함수를 보여 줍니다.  
  
|함수|설명|  
|--------------|-----------------|  
|`DATEADD(datepart, number, date)`|지정한 날짜에 일정 간격을 더한 값을 더해서 새 `DateTime` 값을 반환합니다.<br /><br /> **인수**<br /><br /> `datepart`: 새 값을 반환할 날짜 부분을 나타내는 `String`입니다.<br /><br /> `number`: `Int32`에 더해지는 `Int64`, `Decimal`, `Double` 또는 `datepart` 값입니다.<br /><br /> `date:` 전체 자릿수가 [0-7]인 `DateTime`, `DateTimeOffset`, `Time` 또는 날짜 형식의 문자열을 반환하는 식입니다.<br /><br /> **반환 값**<br /><br /> 전체 자릿수가 [0-7]인 새 `DateTime`, `DateTimeOffset` 또는  `Time` 값입니다.<br /><br /> **예제**<br /><br /> `SqlServer.DATEADD('day', 22, cast('6/9/2006' as DateTime))`|  
|`DATEDIFF(datepart,startdate,enddate)`|지정한 두 날짜 간에 교차되는 날짜와 시간 경계값을 반환합니다.<br /><br /> **인수**<br /><br /> `datepart`: 차이를 계산할 날짜 부분을 나타내는 `String`입니다.<br /><br /> `startdate`: 계산의 시작 날짜는 전체 자릿수가 [0-7]인 `DateTime`, `DateTimeOffset`, `Time` 값 또는 날짜 형식의 문자열을 반환하는 식입니다.<br /><br /> `enddate:` 계산의 끝 날짜는 전체 자릿수가 [0-7]인 `DateTime`, `DateTimeOffset`, `Time` 값 또는 날짜 형식의 문자열을 반환하는 식입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다.<br /><br /> **예제**<br /><br /> `SqlServer.DATEDIFF('day', cast('6/9/2006' as DateTime),`<br /><br /> `cast('6/20/2006' as DateTime))`|  
|`DATENAME(datepart, date)`|지정된 날짜의 특정 부분을 나타내는 문자열을 반환합니다.<br /><br /> **인수**<br /><br /> `datepart`: 새 값을 반환할 날짜 부분을 나타내는 `String`입니다.<br /><br /> `date`: 전체 자릿수가 [0-7]인 `DateTime,`, `DateTimeOffset`, `Time` 값 또는 날짜 형식의 문자열을 반환하는 식입니다.<br /><br /> **반환 값**<br /><br /> 지정한 날짜의 지정한 부분을 나타내는 문자열입니다.<br /><br /> **예제**<br /><br /> `SqlServer.DATENAME('year', cast('6/9/2006' as DateTime))`|  
|`DATEPART(datepart, date)`|지정한 날짜의 지정된 datepart를 나타내는 정수를 반환합니다.<br /><br /> **인수**<br /><br /> `datepart`: 새 값을 반환할 날짜 부분을 나타내는 `String`입니다.<br /><br /> `date`: 전체 자릿수가 [0-7]인 `DateTime,`, `DateTimeOffset,`, `Time` 값 또는 날짜 형식의 문자열을 반환하는 식입니다.<br /><br /> **반환 값**<br /><br /> 지정한 날짜의 지정한 부분을 나타내는 `Int32`입니다.<br /><br /> **예제**<br /><br /> `SqlServer.DATEPART('year', cast('6/9/2006' as DateTime))`|  
|`DAY(date)`|지정 된 날짜의 일을 정수로 반환 합니다.<br /><br /> **인수**<br /><br /> `date`: `DateTime` `DateTimeOffset` 전체 자릿수가 0-7 인 또는 형식의 식입니다.<br /><br /> **반환 값**<br /><br /> 지정한 날짜의 일을 나타내는 `Int32`입니다.<br /><br /> **예제**<br /><br /> `SqlServer.DAY(cast('6/9/2006' as DateTime))`|  
|`GETDATE()`|현재 날짜와 시간을 datetime 값에 대한 SQL Server 내부 형식으로 생성합니다.<br /><br /> **반환 값**<br /><br /> `DateTime` 형식이며 전체 자릿수가 3인 현재 시스템 날짜 및 시간입니다.<br /><br /> **예제**<br /><br /> `SqlServer.GETDATE()`|  
|`GETUTCDATE()`|datetime 값을 UTC(Coordinated Universal Time 또는 그리니치 표준시) 형식으로 생성합니다.<br /><br /> **반환 값**<br /><br /> 전체 자릿수가 3인 UTC 형식의 `DateTime` 값입니다.<br /><br /> **예제**<br /><br /> `SqlServer.GETUTCDATE()`|  
|`MONTH(date)`|지정한 날짜의 월을 정수로 반환합니다.<br /><br /> **인수**<br /><br /> `date`: `DateTime` `DateTimeOffset` 전체 자릿수가 0-7 인 또는 형식의 식입니다.<br /><br /> **반환 값**<br /><br /> 지정한 날짜의 월을 나타내는 `Int32`입니다.<br /><br /> **예제**<br /><br /> `SqlServer.MONTH(cast('6/9/2006' as DateTime))`|  
|`YEAR(date)`|지정한 날짜의 연도를 정수로 반환합니다.<br /><br /> **인수**<br /><br /> `date`: `DateTime` `DateTimeOffset` 전체 자릿수가 0-7 인 또는 형식의 식입니다.<br /><br /> **반환 값**<br /><br /> 지정한 날짜의 연도를 나타내는 `Int32`입니다.<br /><br /> **예제**<br /><br /> `SqlServer.YEAR(cast('6/9/2006' as DateTime))`|  
|`SYSDATETIME()`|전체 자릿수가 7인 `DateTime` 값을 반환합니다.<br /><br /> **반환 값**<br /><br /> 전체 자릿수가 7인 `DateTime` 값입니다.<br /><br /> **예제**<br /><br /> `SqlServer.SYSDATETIME()`|  
|`SYSUTCDATE()`|datetime 값을 UTC(Coordinated Universal Time 또는 그리니치 표준시) 형식으로 생성합니다.<br /><br /> **반환 값**<br /><br /> 전체 자릿수가 7인 UTC 형식의 `DateTime` 값입니다.<br /><br /> **예제**<br /><br /> `SqlServer.SYSUTCDATE()`|  
|`SYSDATETIMEOFFSET()`|전체 자릿수가 7인 `DateTimeOffset`을 반환합니다.<br /><br /> **반환 값**<br /><br /> 전체 자릿수가 7인 UTC 형식의 `DateTimeOffset` 값입니다.<br /><br /> **예제**<br /><br /> `SqlServer.SYSDATETIMEOFFSET()`|  
  
 SqlClient에서 지 원하는 날짜 및 시간 함수에 대 한 자세한 내용은 [날짜 및 시간 데이터 형식 및 함수 (transact-sql)](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)를 참조 하세요.
  
## <a name="see-also"></a>참고 항목

- [Entity Framework용 SqlClient 기능](sqlclient-for-ef-functions.md)
