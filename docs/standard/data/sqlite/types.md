---
title: 데이터 형식
ms.date: 12/13/2019
description: 지원되는 데이터 형식과 지원되는 데이터 형식에 대한 몇 가지 제한 사항에 대해 설명합니다.
ms.openlocfilehash: a11ff382f80cd979506d6195c299c8234c3eb8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389046"
---
# <a name="data-types"></a>데이터 형식

SQLite에는 정수, REAL, 텍스트 및 BLOB의 네 가지 기본 데이터 유형만 있습니다. 데이터베이스 값을 반환하는 `object` API는 이러한 네 가지 유형 중 하나만 반환합니다. Microsoft.Data.Sqlite에서 추가 .NET 형식을 지원하지만 궁극적으로 이러한 형식과 네 가지 기본 형식 중 하나 간에 값이 강제 변환됩니다.

| .NET           | SQLite  | 설명                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| 부울        | INTEGER | `0` 또는 `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| DateTime       | TEXT    | yyy-MM-dd HH:mm:ss. 프프프 (것)fffffff                                   |
| DateTimeOffset | TEXT    | yyy-MM-dd HH:mm:ss. FFFFFzzz                                |
| Decimal        | TEXT    | `0.0###########################`형식. 레알은 손해가 될 것입니다. |
| Double         | real    |                                                               |
| Guid           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Single         | real    |                                                               |
| String         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d.hh:mm:ss.fffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt32         | INTEGER |                                                               |
| UInt64         | INTEGER | 큰 값 오버플로                                         |

## <a name="alternative-types"></a>대체 형식

일부 .NET 형식은 대체 SQLite 형식에서 읽을 수 있습니다. 이러한 대체 형식을 사용하도록 매개 변수를 구성할 수도 있습니다. 자세한 내용은 [매개 변수](parameters.md#alternative-types)를 참조하세요.

| .NET           | SQLite  | 설명          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| DateTime       | real    | 줄리안 일 값 |
| DateTimeOffset | real    | 줄리안 일 값 |
| Guid           | BLOB    |                  |
| TimeSpan       | real    | 며칠 만에          |

예를 들어 다음 쿼리는 결과 집합의 REAL 열에서 TimeSpan 값을 읽습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>열 형식

SQLite는 값의 형식이 저장된 열이 아니라 값 자체와 연관된 동적 형식 시스템을 사용합니다. 원하는 열 유형 이름을 자유롭게 사용할 수 있습니다. Microsoft.Data.Sqlite는 이러한 이름에 추가 의미 체계를 적용하지 않습니다.

열 형식 이름은 [형식 선호도에](https://www.sqlite.org/datatype3.html#type_affinity)영향을 미칩니다. 한 가지 일반적인 gotcha는 STRING의 열 형식을 사용하면 값을 정수 또는 REAL으로 변환하여 예기치 않은 결과를 초래할 수 있다는 것입니다. 정수, REAL, TEXT 및 BLOB의 네 가지 기본 SQLite 형식 이름만 사용하는 것이 좋습니다.

SQLite를 사용하면 길이, 정밀도 및 배율과 같은 유형 면을 지정할 수 있지만 데이터베이스 엔진에 의해 적용되지는 않습니다. 앱은 이러한 적용을 담당합니다.

## <a name="see-also"></a>참고 항목

- [SQLite의 데이터 유형](https://www.sqlite.org/datatype3.html)
