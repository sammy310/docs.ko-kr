---
title: 데이터 정렬
ms.date: 12/13/2019
description: 사용자 지정 정렬 시퀀스를 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242974"
---
# <a name="collation"></a>데이터 정렬

정렬 시퀀스는 텍스트 값을 비교하여 순서와 같음을 결정할 때 SQLite에서 사용됩니다. SQL 쿼리에서 열을 만들거나 작업당 작업을 수행할 때 사용할 데이터 정렬을 지정할 수 있습니다. SQLite는 기본적으로 세 개의 정렬 시퀀스를 포함합니다.

| 데이터 정렬 | Description                               |
| --------- | ----------------------------------------- |
| RTRIM     | 후행 공백 무시               |
| 없음 없음    | ASCII 문자 A-Z에 대한 대/소문자 구분되지 않음 |
| BINARY    | 대/소문자를 구분할 수 있습니다. 바이트를 직접 비교합니다.   |

## <a name="custom-collation"></a>사용자 지정 데이터 정렬

고유한 정렬 시퀀스를 정의하거나 을 사용하여 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>기본 제공 시퀀스를 재정의할 수도 있습니다. 다음 예제에서는 유니코드 문자를 지원 하기 위해 NOCASE 데이터 정렬 재정의 를 보여 주다. [전체 샘플 코드는](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) GitHub에서 사용할 수 있습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like 연산자

SQLite의 LIKE 연산자는 데이터 정렬을 존중하지 않습니다. 기본 구현에는 NOCASE 데이터 정렬과 동일한 의미 체계가 있습니다. ASCII 문자 A부터 Z까지의 대/소문자에 대해서만 민감하지 않습니다.

다음 pragma 문을 사용하여 LIKE 연산자 대/소문자를 쉽게 만들 수 있습니다.

```sql
PRAGMA case_sensitive_like = 1
```

LIKE 연산자의 구현 재정의에 대한 자세한 내용은 [사용자 정의 함수를](user-defined-functions.md) 참조하십시오.

## <a name="see-also"></a>참고 항목

* [사용자 정의 함수](user-defined-functions.md)
* [SQL 구문](https://www.sqlite.org/lang.html)
