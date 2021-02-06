---
description: '자세히 알아보기: SQL Server 함수 매핑에 대 한 정식 개념 모델'
title: 개념적 모델 정식 함수와 SQL Server 함수 매핑
ms.date: 03/30/2017
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
ms.openlocfilehash: 25e366a45e91db97693c42b3c8d2febd912320ab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651069"
---
# <a name="conceptual-model-canonical-to-sql-server-functions-mapping"></a>개념적 모델 정식 함수와 SQL Server 함수 매핑

이 항목에서는 개념적 모델 정식 함수가 해당 SQL Server 함수에 매핑되는 방법에 대해 설명합니다.  
  
## <a name="date-and-time-functions"></a>날짜 및 시간 함수  

 다음 표에서는 날짜 및 시간 함수 매핑에 대해 설명합니다.  
  
|정식 함수|SQL Server 함수|  
|-------------------------|--------------------------|  
|[AddDays(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[AddMicroseconds(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[AddMinutes(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[AddNanoseconds(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[AddSeconds(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[AddYears(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[CreateDateTime(year, month, day, hour, minute, second)](./language-reference/date-and-time-canonical-functions.md)|SQL Server 2000 및 SQL Server 2005의 경우 `datetime` 형식이 지정된 값이 서버에 만들어집니다. SQL Server 2008 및 이후 버전의 경우 `datetime2` 값이 서버에 만들어집니다.|  
|[CreateDateTimeOffset(year, month, day, hour, minute, second, tzoffset)](./language-reference/date-and-time-canonical-functions.md)|`datetimeoffset` 형식이 지정된 값이 서버에 만들어집니다.<br /><br /> SQL Server 2000 또는 SQL Server 2005에서는 지원되지 않습니다.|  
|[CreateTime(hour, minute, second)](./language-reference/date-and-time-canonical-functions.md)|`time` 형식이 지정된 값이 서버에 만들어집니다.<br /><br /> SQL Server 2000 또는 SQL Server 2005에서는 지원되지 않습니다.|  
|[CurrentDateTime ()](./language-reference/date-and-time-canonical-functions.md)|SQL Server 2008의 `SysDateTime()`.<br /><br /> SQLServer 2000 및 SQLServer 2005의 `GetDate()`|  
|[CurrentDateTimeOffset()](./language-reference/date-and-time-canonical-functions.md)|SQL Server 2008의 `SysDateTimeOffset()`<br /><br /> SQL Server 2000 또는 SQL Server 2005에서는 지원되지 않습니다.|  
|[CurrentUtcDateTime()](./language-reference/date-and-time-canonical-functions.md)|SQL Server 2008의 `SysUtcDateTime()`. SQL Server 2000 및 SQL Server 2005의 `GetUtcDate()`|  
|[DayOfYear(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[DiffDays(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[DiffHours(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[DiffMicroseconds(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[DiffMilliseconds(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[DiffMinutes(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[DiffNanoseconds(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[DiffSeconds(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[DiffYears(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[GetTotalOffsetMinutes(DateTimeOffset)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[Hour(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Millisecond(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minute(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Month(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Second(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[Truncate(expression)](./language-reference/date-and-time-canonical-functions.md)|SQL Server 2000 및 SQL Server 2005의 경우 잘린 `datetime` 형식의 값이 서버에 만들어집니다. SQL Server 2008 이상 버전의 경우 잘린 `datetime2` `datetimeoffset` 값 이나 값이 서버에 만들어집니다.|  
|[Year(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## <a name="aggregate-functions"></a>집계 함수  

 다음 표에서는 집계 함수 매핑에 대해 설명합니다.  
  
|정식 함수|SQL Server 함수|  
|-------------------------|--------------------------|  
|[Avg(expression)](./language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount(expression)](./language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Count(expression)](./language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min(expression)](./language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max(expression)](./language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev(expression)](./language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP(expression)](./language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[Sum(expression)](./language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var(expression)](./language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP(expression)](./language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## <a name="math-functions"></a>수치 연산 함수  

 다음 표에서는 수치 연산 함수 매핑에 대해 설명합니다.  
  
|정식 함수|SQL Server 함수|  
|-------------------------|--------------------------|  
|[Abs(value)](./language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[Ceiling(value)](./language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor(value)](./language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Power(value)](./language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round(value)](./language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[Truncate](./language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## <a name="string-functions"></a>문자열 함수  

 다음 표에서는 문자열 함수 매핑에 대해 설명합니다.  
  
|정식 함수|SQL Server 함수|  
|-------------------------|--------------------------|  
|[Contains(string, target)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat(string1, string2)](./language-reference/string-canonical-functions.md)|string1 + string2|  
|[EndsWith(string, target)](./language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **참고** `CHARINDEX` 함수는 `false` `string` 이 고정 길이 문자열 열에 저장 되어 있고 `target` 가 상수 이면를 반환 합니다. 이 경우 뒤쪽 채움 공백을 포함하여 전체 문자열이 검색됩니다. `EndsWith` 예제에 나와 있는 대로 `EndsWith(TRIM(string), target)` 함수에 문자열을 전달하기 전에 고정 길이 문자열의 데이터를 잘라내면 문제를 해결할 수 있습니다.|  
|[IndexOf(target, string2)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[Left (string1, length)](./language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[Length (string)](./language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim(string)](./language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[Right (string1, length)](./language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim(string)](./language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[Replace (string1, string2, string3)](./language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[Reverse (문자열)](./language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim(string)](./language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|[StartsWith(string, target)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Substring(string, start, length)](./language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower(string)](./language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper(string)](./language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## <a name="bitwise-functions"></a>비트 함수  

 다음 표에서는 비트 함수 매핑에 대해 설명합니다.  
  
|정식 함수|SQL Server 함수|  
|-------------------------|--------------------------|  
|[BitWiseAnd (value1, value2)](./language-reference/bitwise-canonical-functions.md)|value1 & value2|  
|[BitWiseNot (value)](./language-reference/bitwise-canonical-functions.md)|~value|  
|[BitWiseOr (value1, value2)](./language-reference/bitwise-canonical-functions.md)|value1 &#124; value2|  
|[BitWiseXor (value1, value2)](./language-reference/bitwise-canonical-functions.md)|value1 ^ value2|
