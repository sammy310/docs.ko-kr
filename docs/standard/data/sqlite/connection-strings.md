---
title: 연결 문자열
ms.date: 12/13/2019
description: 지원되는 키워드 및 연결 문자열의 값입니다.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401198"
---
# <a name="connection-strings"></a>연결 문자열

연결 문자열은 데이터베이스에 연결하는 방법을 지정하는 데 사용됩니다. Microsoft.Data.Sqlite의 연결 문자열은 표준 [ADO.NET 구문을](../../../framework/data/adonet/connection-strings.md) 키워드 및 값의 세미콜론으로 구분된 목록으로 따릅니다.

## <a name="keywords"></a>키워드

다음 연결 문자열 키워드는 Microsoft.Data.Sqlite에서 사용할 수 있습니다.

### <a name="data-source"></a>데이터 원본

데이터베이스 파일의 경로입니다. *데이터 원본(공백* 제외)과 *파일 이름은* 이 키워드의 별칭입니다.

SQLite는 현재 작업 디렉터리와 관련된 경로를 처리합니다. 절대 경로를 지정할 수도 있습니다.

**비어**있는 경우 SQLite는 연결이 닫혀 있을 때 삭제되는 임시 온 디스크 데이터베이스를 만듭니다.

을 `:memory:`사용 하는 경우 메모리 내 데이터베이스가 사용 됩니다. 자세한 내용은 [메모리 내 데이터베이스를 참조하십시오.](in-memory-databases.md)

`|DataDirectory|` 대체 문자열로 시작하는 경로는 상대 경로와 동일하게 처리됩니다. 설정된 경우 경로는 DataDirectory 응용 프로그램 도메인 속성 값을 기준으로 만들어집니다.

이 키워드는 [URI 파일 이름도](https://www.sqlite.org/uri.html)지원합니다.

### <a name="mode"></a>Mode

연결 모드입니다.

| 값           | Description                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| 읽기 쓰기 만들기 | 읽기 및 쓰기를 위해 데이터베이스를 열고 존재하지 않는 경우 데이터베이스를 만듭니다. 이것이 기본값입니다. |
| ReadWrite       | 읽기 및 쓰기를 위한 데이터베이스를 엽니다.                                                        |
| ReadOnly        | 읽기 전용 모드에서 데이터베이스를 엽니다.                                                              |
| 메모리          | 메모리 내 데이터베이스를 엽니다.                                                                       |

### <a name="cache"></a>캐시

연결에서 사용하는 캐싱 모드입니다.

| 값   | Description                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| 기본값 | 기본 SQLite 라이브러리의 기본 모드를 사용합니다. 이것이 기본값입니다.                   |
| 프라이빗 | 각 연결은 개인 캐시를 사용합니다.                                                          |
| 공유됨  | 연결은 캐시를 공유합니다. 이 모드는 트랜잭션 및 테이블 잠금 의 동작을 변경할 수 있습니다. |

### <a name="password"></a>암호

암호화 키입니다. 지정하면 `PRAGMA key` 연결을 연 직후에 전송됩니다.

> [!WARNING]
> 기본 SQLite 라이브러리에서 암호화를 지원하지 않는 경우 암호는 영향을 주지 않습니다.

### <a name="foreign-keys"></a>외래 키

외래 키 제약 조건을 사용할지 여부를 나타내는 값입니다.

| 값   | Description
| ------- | --- |
| True    | 연결을 `PRAGMA foreign_keys = 1` 연 직후에 전송됩니다.
| False   | 연결을 `PRAGMA foreign_keys = 0` 연 직후에 전송됩니다.
| (empty) | 을 보내지 `PRAGMA foreign_keys`않습니다. 이것이 기본값입니다. |

e_sqlite3 처럼 네이티브 SQLite 라이브러리를 컴파일하는 데 SQLITE_DEFAULT_FOREIGN_KEYS 사용되는 경우 외래 키를 사용할 필요가 없습니다.

### <a name="recursive-triggers"></a>재귀 트리거

재귀 트리거를 사용할지 여부를 나타내는 값입니다.

| 값 | Description                                                                 |
| ----- | --------------------------------------------------------------------------- |
| True  | 연결을 `PRAGMA recursive_triggers` 연 직후에 전송됩니다. |
| False | 을 보내지 `PRAGMA recursive_triggers`않습니다. 이것이 기본값입니다.              |

## <a name="connection-string-builder"></a>연결 문자열 빌더

연결 문자열을 만드는 강력한 형식의 방법으로 사용할 <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> 수 있습니다. 또한 연결 문자열 주입 공격을 방지하는 데 사용할 수 있습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a>예

### <a name="basic"></a>Basic

향상된 동시성을 위해 공유 캐시가 있는 기본 연결 문자열입니다.

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a>암호화

암호화된 데이터베이스입니다.

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a>읽기 전용

앱에서 수정할 수 없는 읽기 전용 데이터베이스입니다.

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a>메모리 내

전용 인메모리 데이터베이스입니다.

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a>공유 가능한 인메모리

이름 공유 가능으로 식별되는 공유 가능한 메모리 내 *데이터베이스입니다.*

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a>참고 항목

* [ADO.NET의 연결 문자열](../../../framework/data/adonet/connection-strings.md)
* [인메모리 데이터베이스](in-memory-databases.md)
* [트랜잭션을](transactions.md)
