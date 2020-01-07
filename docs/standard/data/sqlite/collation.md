---
title: Collation
ms.date: 12/13/2019
description: 사용자 지정 정렬 순서를 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0942ad4523a149ad74321cbe0f63021f53303579
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450287"
---
# <a name="collation"></a>Collation

데이터 정렬 순서는 SQLite에서 텍스트 값을 비교 하 여 순서 및 같음을 결정 하는 데 사용 됩니다. SQL 쿼리에서 열 또는 작업당 작업을 만들 때 사용할 데이터 정렬을 지정할 수 있습니다. SQLite에는 기본적으로 세 가지 데이터 정렬 순서가 포함 됩니다.

| Collation | 설명                               |
| --------- | ----------------------------------------- |
| RTRIM     | 후행 공백을 무시 합니다.               |
| NOCASE    | ASCII 문자 a-z의 대/소문자 구분 안 함 |
| BINARY    | 대/소문자 구분 바이트 직접 비교   |

## <a name="custom-collation"></a>사용자 지정 데이터 정렬

사용자 고유의 데이터 정렬 시퀀스를 정의 하거나 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>를 사용 하 여 기본 제공 되는 시퀀스를 재정의할 수도 있습니다. 다음 예에서는 유니코드 문자를 지원 하도록 NOCASE 데이터 정렬을 재정의 하는 방법을 보여 줍니다. [전체 샘플 코드](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) 는 GitHub에서 사용할 수 있습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like 연산자

SQLite의 LIKE 연산자는 데이터 정렬을 인식 하지 않습니다. 기본 구현에는 NOCASE 데이터 정렬과 동일한 의미 체계가 있습니다. ASCII 문자 A ~ Z에 대 한 대/소문자를 구분 하지 않습니다.

다음과 같은 pragma 문을 사용 하 여 LIKE 연산자를 대/소문자를 구분 하 여 쉽게 만들 수 있습니다.

```sql
PRAGMA case_sensitive_like = 0
```

LIKE 연산자의 구현을 재정의 하는 방법에 대 한 자세한 내용은 [사용자 정의 함수](user-defined-functions.md) 를 참조 하세요.

## <a name="see-also"></a>참조

* [사용자 정의 함수](user-defined-functions.md)
* [SQL 구문](https://www.sqlite.org/lang.html)
