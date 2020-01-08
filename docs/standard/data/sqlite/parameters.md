---
title: 매개 변수
ms.date: 12/13/2019
description: SQL 매개 변수를 사용 하는 방법을 알아봅니다.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450425"
---
# <a name="parameters"></a>매개 변수

매개 변수는 SQL 삽입 공격 으로부터 보호 하는 데 사용 됩니다. 사용자 입력을 SQL 문과 연결 하는 대신 매개 변수를 사용 하 여 입력이 리터럴 값 으로만 처리 되 고 실행 되지 않도록 합니다. SQLite에서 매개 변수는 일반적으로 SQL 문에서 리터럴이 허용 되는 모든 위치에서 허용 됩니다.

매개 변수에는 `:`, `@`또는 `$`접두사가 추가 될 수 있습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

.NET 값이 SQLite 값에 매핑되는 방법에 대 한 자세한 내용은 [데이터 형식](types.md) 을 참조 하세요.

## <a name="truncation"></a>잘림

<xref:Microsoft.Data.Sqlite.SqliteParameter.Size> 속성을 사용 하 여 텍스트 및 BLOB 값을 자릅니다.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>대체 형식

경우에 따라 대체 SQLite 유형을 사용 해야 할 수도 있습니다. <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> 속성을 설정 하 여이 작업을 수행 합니다.

다음 대체 형식 매핑을 사용할 수 있습니다. 기본 매핑에 대해서는 [데이터 형식](types.md)을 참조 하세요.

| 값          | SqliteType | 주의          |
| -------------- | ---------- | ---------------- |
| Char           | 정수    | UTF-16           |
| DateTime       | Real       | 율리우스 날짜 값 |
| DateTimeOffset | Real       | 율리우스 날짜 값 |
| GUID           | Blob       |                  |
| TimeSpan       | Real       | 일 단위          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>출력 매개 변수

SQLite는 출력 매개 변수를 지원 하지 않습니다. 대신 쿼리 결과의 값을 반환 합니다.

## <a name="see-also"></a>참조

* [데이터 형식](types.md)
