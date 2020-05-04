---
title: 데이터 형식
ms.date: 12/13/2019
description: 지원되는 데이터 형식 및 그와 관련된 몇 가지 제한 사항에 대해 설명합니다.
ms.openlocfilehash: a11ff382f80cd979506d6195c299c8234c3eb8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389046"
---
# <a name="data-types"></a>데이터 형식

SQLite에는 다음 네 가지 기본 데이터 형식만 있습니다. INTEGER, REAL, TEXT 및 BLOB. 데이터베이스 값을 `object`로 반환하는 API는 이 네 가지 형식 중 하나만 반환합니다. 추가 .NET 형식은 Microsoft.Data.Sqlite에서 지원되지만 값은 궁극적으로 다음 형식과 네 가지 기본 형식 중 하나 사이에서 강제 변환됩니다.

| .NET           | SQLite  | 설명                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Boolean        | INTEGER | `0` 또는 `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| DateTime       | TEXT    | yyyy-MM-dd HH:mm:ss.FFFFFFF                                   |
| DateTimeOffset | TEXT    | yyyy-MM-dd HH:mm:ss.FFFFFFFzzz                                |
| Decimal        | TEXT    | `0.0###########################` 형식. REAL은 손실 형식입니다. |
| Double         | real    |                                                               |
| GUID           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Single         | real    |                                                               |
| String         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d.hh:mm:ss.fffffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt32         | INTEGER |                                                               |
| UInt64         | INTEGER | 큰 값 오버플로                                         |

## <a name="alternative-types"></a>대체 형식

일부 .NET 형식은 대체 SQLite 형식에서 읽을 수 있습니다. 또한 이러한 대체 형식을 사용하도록 매개 변수를 구성할 수도 있습니다. 자세한 내용은 [매개 변수](parameters.md#alternative-types)를 참조하세요.

| .NET           | SQLite  | 설명          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| DateTime       | real    | 율리우스 날짜 값 |
| DateTimeOffset | real    | 율리우스 날짜 값 |
| GUID           | BLOB    |                  |
| TimeSpan       | real    | 일 수          |

예를 들어 다음 쿼리는 결과 집합의 REAL 열에서 TimeSpan 값을 읽습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>열 형식

SQLite는 값 형식이 값이 저장된 열이 아니라 값 자체와 연결된 동적 형식 시스템을 사용합니다. 원하는 열 형식 이름을 자유롭게 사용할 수 있습니다. Microsoft.Data.Sqlite는 이러한 이름에 추가 의미 체계를 적용하지 않습니다.

열 형식 이름은 [형식 선호도](https://www.sqlite.org/datatype3.html#type_affinity)에 영향을 줍니다. 한 가지 일반적인 알려진 문제는 열 형식 STRING을 사용하면 값을 INTEGER 또는 REAL로 변환하려고 시도하므로 예기치 않은 결과가 발생할 수 있는 것입니다. 다음 네 가지 기본 SQLite 형식 이름만 사용하는 것이 좋습니다. INTEGER, REAL, TEXT 및 BLOB.

SQLite를 사용하면 길이, 전체 자릿수 및 소수 자릿수와 같은 형식 패싯을 지정할 수 있지만 데이터베이스 엔진은 이를 적용하지 않습니다. 앱이 이를 적용해야 합니다.

## <a name="see-also"></a>참조

- [SQLite의 데이터 형식](https://www.sqlite.org/datatype3.html)
