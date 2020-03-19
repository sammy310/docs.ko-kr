---
title: 매개 변수
ms.date: 12/13/2019
description: SQL 매개 변수를 사용하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401204"
---
# <a name="parameters"></a>매개 변수

매개 변수는 SQL 주입 공격으로부터 보호하는 데 사용됩니다. 사용자 입력을 SQL 문과 연결하는 대신 매개 변수를 사용하여 입력이 리터럴 값으로만 처리되고 실행되지 않도록 합니다. SQLite에서 매개 변수는 일반적으로 SQL 문에서 리터럴이 허용되는 모든 곳에서 허용됩니다.

매개 변수는 에 `:` `@`의한 것 `$`또는 으로 접두사할 수 있습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

.NET 값이 SQLite 값에 매핑되는 방법에 대한 자세한 내용은 [데이터 유형을](types.md) 참조하십시오.

## <a name="truncation"></a>잘림

속성을 <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> 사용하여 TEXT 및 BLOB 값을 자를 합니다.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>대체 형식

경우에 따라 다른 SQLite 형식을 사용할 수 있습니다. <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> 속성을 설정 하 여이 작업을 수행 합니다.

다음 대체 형식 매핑을 사용할 수 있습니다. 기본 매핑에 대 한 데이터 형식을 참조 [합니다.](types.md)

| 값          | SqliteType | 설명          |
| -------------- | ---------- | ---------------- |
| Char           | 정수    | UTF-16           |
| DateTime       | Real       | 줄리안 일 값 |
| DateTimeOffset | Real       | 줄리안 일 값 |
| Guid           | Blob       |                  |
| TimeSpan       | Real       | 며칠 만에          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>출력 매개 변수

SQLite는 출력 매개 변수를 지원하지 않습니다. 대신 쿼리 결과에 값을 반환합니다.

## <a name="see-also"></a>참고 항목

* [데이터 유형](types.md)
