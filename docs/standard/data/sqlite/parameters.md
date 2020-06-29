---
title: 매개 변수
ms.date: 12/13/2019
description: SQL 매개 변수를 사용하는 방법을 알아봅니다.
ms.openlocfilehash: b24610a5cb65e2b24171452acef9bf55b4995431
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768952"
---
# <a name="parameters"></a>매개 변수

매개 변수는 SQL 삽입 공격으로부터 보호하는 데 사용됩니다. 사용자 입력을 SQL 문과 연결하는 대신 매개 변수를 사용하여 입력이 리터럴 값으로만 처리되고 실행되지 않도록 합니다. SQLite에서 매개 변수는 일반적으로 SQL 문에서 리터럴이 허용되는 모든 곳에서 허용됩니다.

매개 변수는 `:`, `@` 또는 `$`를 접두사로 사용할 수 있습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

.NET 값이 SQLite 값에 매핑되는 방법에 대한 자세한 내용은 [데이터 형식](types.md)을 참조하세요.

## <a name="truncation"></a>잘림

<xref:Microsoft.Data.Sqlite.SqliteParameter.Size> 속성을 사용하여 텍스트 및 BLOB 값을 자릅니다.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Size = 30;
```

## <a name="alternative-types"></a>대체 형식

경우에 따라 대체 SQLite 형식을 사용해야 할 수도 있습니다. <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> 속성을 설정하여 이 작업을 수행합니다.

다음 대체 형식 매핑을 사용할 수 있습니다. 기본 매핑은 [데이터 형식](types.md)을 참조하세요.

| 값          | SqliteType | 설명          |
| -------------- | ---------- | ---------------- |
| Char           | 정수    | UTF-16           |
| DateTime       | Real       | 율리우스 날짜 값 |
| DateTimeOffset | Real       | 율리우스 날짜 값 |
| GUID           | Blob       |                  |
| TimeSpan       | Real       | 일 수          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>출력 매개 변수

SQLite는 출력 매개 변수를 지원하지 않습니다. 대신 쿼리 결과의 값을 반환합니다.

## <a name="see-also"></a>참조

* [데이터 형식](types.md)
