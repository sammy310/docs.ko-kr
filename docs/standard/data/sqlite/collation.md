---
title: 데이터 정렬
ms.date: 12/13/2019
description: 사용자 지정 정렬 순서를 만드는 방법을 알아봅니다.
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242974"
---
# <a name="collation"></a>데이터 정렬

데이터 정렬 순서는 SQLite에서 TEXT 값을 비교하여 순서 및 같음을 결정하는 데 사용됩니다. SQL 쿼리에서 열을 만들 때 또는 작업 단위로 사용할 데이터 정렬을 지정할 수 있습니다. SQLite에는 기본적으로 세 가지 데이터 정렬 순서가 포함됩니다.

| 데이터 정렬 | 설명                               |
| --------- | ----------------------------------------- |
| RTRIM     | 후행 공백 무시               |
| NOCASE    | ASCII 문자 A-Z의 대/소문자 구분 안 함 |
| BINARY    | 대/소문자 구분. 바이트 직접 비교   |

## <a name="custom-collation"></a>사용자 지정 데이터 정렬

사용자 고유의 데이터 정렬 순서를 정의하거나 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>를 사용하여 기본 제공 순서를 재정의할 수도 있습니다. 다음 예제에서는 유니코드 문자를 지원하도록 NOCASE 데이터 정렬을 재정의하는 방법을 보여 줍니다. [전체 샘플 코드](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs)는 GitHub에서 사용할 수 있습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like 연산자

SQLite의 LIKE 연산자는 데이터 정렬을 인식하지 않습니다. 기본 구현에는 NOCASE 데이터 정렬과 동일한 의미 체계가 있습니다. ASCII 문자 A - Z만 대/소문자를 구분하지 않습니다.

다음과 같은 pragma 문을 사용하여 쉽게 LIKE 연산자가 대/소문자를 구분하도록 만들 수 있습니다.

```sql
PRAGMA case_sensitive_like = 1
```

LIKE 연산자의 구현을 재정의하는 방법에 대한 자세한 내용은 [사용자 정의 함수](user-defined-functions.md)를 참조하세요.

## <a name="see-also"></a>참조

* [사용자 정의 함수](user-defined-functions.md)
* [SQL 구문](https://www.sqlite.org/lang.html)
