---
title: 데이터 형식
ms.date: 12/13/2019
description: 지원 되는 데이터 형식 및 그와 관련 된 몇 가지 제한 사항에 대해 설명 합니다.
ms.openlocfilehash: ae70cb91a5a6d9cfed45a5a47dda25a70362871e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450419"
---
# <a name="data-types"></a>데이터 형식

SQLite에는 정수, 실제, 텍스트 및 BLOB의 네 가지 기본 데이터 유형만 있습니다. 데이터베이스 값을 `object` 반환 하는 Api는 다음 네 가지 형식 중 하나만 반환 합니다. 추가 .NET 형식은 Microsoft. Sqlite에서 지원 되지만 값은 궁극적으로 이러한 형식과 네 가지 기본 형식 중 하나 사이에서 강제 변환 됩니다.

| .NET           | SQLite  | 주의                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Boolean        | INTEGER | `0` 또는 `1`                                                    |
| 바이트           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| DateTime       | TEXT    | yyyy-MM-dd HH: MM: ss. FFFFFFF                                   |
| DateTimeOffset | TEXT    | yyyy-MM-dd HH: MM: ss. Ss'.'fffffffzzz                                |
| Decimal        | TEXT    | `0.0###########################` 형식입니다. 실수는 손실이 될 것입니다. |
| Double         | REAL    |                                                               |
| GUID           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Single         | REAL    |                                                               |
| 문자열         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d. hh: mm: ss. fffffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt64         | INTEGER | 대량 값 오버플로                                         |

## <a name="alternative-types"></a>대체 형식

일부 .NET 형식은 다른 SQLite 형식에서 읽을 수 있습니다. 이러한 대체 유형을 사용 하도록 매개 변수를 구성할 수도 있습니다. 자세한 내용은 [매개 변수](parameters.md#alternative-types)를 참조하세요.

| .NET           | SQLite  | 주의          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| DateTime       | REAL    | 율리우스 날짜 값 |
| DateTimeOffset | REAL    | 율리우스 날짜 값 |
| GUID           | BLOB    |                  |
| TimeSpan       | REAL    | 일 단위          |

예를 들어 다음 쿼리는 결과 집합의 실제 열에서 TimeSpan 값을 읽습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>열 형식

SQLite는 값 유형이 저장 된 열이 아니라 값 자체와 연결 된 동적 유형 시스템을 사용 합니다. 원하는 열 유형 이름을 자유롭게 사용할 수 있습니다. 이러한 이름에는 추가 의미 체계를 적용 하지 않습니다.

열 형식 이름이 [형식 선호도](https://www.sqlite.org/datatype3.html#type_affinity)에 영향을 줍니다. 한 가지 일반적인 알려진 문제 열 형식을 사용 하면 값을 정수 또는 실수로 변환 하려고 시도 하므로 예기치 않은 결과가 발생할 수 있습니다. 네 가지 기본 SQLite 형식 이름 (정수, 실제, 텍스트 및 BLOB)만 사용 하는 것이 좋습니다.

SQLite를 사용 하면 길이, 전체 자릿수 및 소수 자릿수와 같은 유형 패싯을 지정할 수 있지만 데이터베이스 엔진에 의해 적용 되지 않습니다. 앱은이를 적용 해야 합니다.

## <a name="see-also"></a>참조

- [SQLite의 데이터 형식](https://www.sqlite.org/datatype3.html)
