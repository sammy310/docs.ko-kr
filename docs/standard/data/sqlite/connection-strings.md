---
title: 연결 문자열
ms.date: 12/13/2019
description: 연결 문자열의 지원되는 키워드 및 값입니다.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401198"
---
# <a name="connection-strings"></a>연결 문자열

연결 문자열은 데이터베이스에 연결하는 방법을 지정하는 데 사용됩니다. Microsoft.Data.Sqlite의 연결 문자열은 세미콜론으로 구분된 키워드 및 값 목록으로 표준 [ADO.NET 구문](../../../framework/data/adonet/connection-strings.md)을 따릅니다.

## <a name="keywords"></a>키워드가

다음 연결 문자열 키워드는 Microsoft.Data.Sqlite에서 사용할 수 있습니다.

### <a name="data-source"></a>데이터 원본

데이터베이스 파일의 경로입니다. *DataSource*(공백 없음) 및 *Filename*은 이 키워드의 별칭입니다.

SQLite는 경로를 현재 작업 디렉터리에 대한 상대 경로로 처리합니다. 절대 경로를 지정할 수도 있습니다.

**비어 있는** 경우 SQLite는 연결이 닫힐 때 삭제되는 임시 디스크 데이터베이스를 만듭니다.

`:memory:`인 경우 메모리 내 데이터베이스가 사용됩니다. 자세한 내용은 [메모리 내 데이터베이스](in-memory-databases.md)를 참조하세요.

`|DataDirectory|` 대체 문자열로 시작하는 경로는 상대 경로와 동일하게 처리됩니다. 설정하는 경우 DataDirectory 애플리케이션 도메인 속성 값을 기준으로 상대 경로가 만들어집니다.

이 키워드는 [URI 파일 이름](https://www.sqlite.org/uri.html)도 지원합니다.

### <a name="mode"></a>모드

연결 모드입니다.

| 값           | 설명                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| ReadWriteCreate | 읽기 및 쓰기를 위해 데이터베이스를 열고 존재하지 않는 경우 데이터베이스를 만듭니다. 기본값입니다. |
| ReadWrite       | 읽기 및 쓰기를 위해 데이터베이스를 엽니다.                                                        |
| ReadOnly        | 데이터베이스를 읽기 전용 모드로 엽니다.                                                              |
| 메모리          | 메모리 내 데이터베이스를 엽니다.                                                                       |

### <a name="cache"></a>캐시

연결에 사용되는 캐싱 모드입니다.

| 값   | 설명                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| 기본값 | 기본 SQLite 라이브러리의 기본 모드를 사용합니다. 기본값입니다.                   |
| Private | 각 연결이 전용 캐시를 사용합니다.                                                          |
| Shared  | 연결이 캐시를 공유합니다. 이 모드는 트랜잭션 및 테이블 잠금의 동작을 변경할 수 있습니다. |

### <a name="password"></a>암호

암호화 키입니다. 지정된 경우 연결을 연 후 즉시 `PRAGMA key`를 보냅니다.

> [!WARNING]
> 네이티브 SQLite 라이브러리에서 암호화를 지원하지 않는 경우 암호는 적용되지 않습니다.

### <a name="foreign-keys"></a>외래 키

외래 키 제약 조건을 사용할지 여부를 나타내는 값입니다.

| 값   | 설명
| ------- | --- |
| True    | 연결을 연 후 즉시 `PRAGMA foreign_keys = 1`을 보냅니다.
| False   | 연결을 연 후 즉시 `PRAGMA foreign_keys = 0`을 보냅니다.
| (비어 있음) | `PRAGMA foreign_keys`를 보내지 않습니다. 기본값입니다. |

e_sqlite3에서와 같이 네이티브 SQLite 라이브러리를 컴파일하는 데 SQLITE_DEFAULT_FOREIGN_KEYS가 사용된 경우 외래 키를 사용할 필요가 없습니다.

### <a name="recursive-triggers"></a>재귀 트리거

재귀 트리거를 사용할지 여부를 나타내는 값입니다.

| 값 | 설명                                                                 |
| ----- | --------------------------------------------------------------------------- |
| True  | 연결을 연 후 즉시 `PRAGMA recursive_triggers`를 보냅니다. |
| False | `PRAGMA recursive_triggers`를 보내지 않습니다. 기본값입니다.              |

## <a name="connection-string-builder"></a>연결 문자열 작성기

<xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>를 강력한 형식으로 연결 문자열을 만드는 방법으로 사용할 수 있습니다. 연결 문자열 삽입 공격을 방지하는 데도 사용할 수 있습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a>예

### <a name="basic"></a>Basic

동시성 향상을 위해 공유 캐시를 사용하는 기본 연결 문자열입니다.

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a>암호화

암호화된 데이터베이스입니다.

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a>읽기 전용

앱이 수정할 수 없는 읽기 전용 데이터베이스입니다.

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a>메모리 내

전용 메모리 내 데이터베이스입니다.

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a>공유 가능한 메모리 내

이름 *Sharable*로 식별되는 공유 가능한 메모리 내 데이터베이스입니다.

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a>참조

* [ADO.NET의 연결 문자열](../../../framework/data/adonet/connection-strings.md)
* [메모리 내 데이터베이스](in-memory-databases.md)
* [트랜잭션](transactions.md)
