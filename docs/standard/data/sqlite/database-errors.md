---
title: 데이터베이스 오류
ms.date: 12/13/2019
description: 라이브러리에서 데이터베이스 오류 및 중지를 처리하는 방법을 설명합니다.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450491"
---
# <a name="database-errors"></a>데이터베이스 오류

SQLite 오류가 발생하면 <xref:Microsoft.Data.Sqlite.SqliteException>이 throw됩니다. 이 메시지는 SQLite에서 제공합니다. `SqliteErrorCode` 및 `SqliteExtendedErrorCode` 속성에는 오류의 SQLite [결과 코드](https://www.sqlite.org/rescode.html)가 포함되어 있습니다.

Microsoft.Data.Sqlite가 네이티브 SQLite 라이브러리와 상호 작용할 때마다 오류가 발생할 수 있습니다. 다음 목록에서는 오류가 발생할 수 있는 일반적인 시나리오를 보여줍니다.

* 연결을 여는 중입니다.
* 트랜잭션을 시작하는 중입니다.
* 명령 실행
* <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>을 호출하여.

앱에서 이러한 오류를 처리하는 방법을 신중하게 고려합니다.

## <a name="locking-retries-and-timeouts"></a>잠금, 다시 시도 및 시간 제한

SQLite는 테이블 및 데이터베이스 파일을 잠글 때 적극적입니다. 앱에서 동시 데이터베이스 액세스를 활성화하면 사용 중이거나 잠금 오류가 발생할 수 있습니다. [공유 캐시](connection-strings.md#cache) 및 [미리 쓰기 로깅](async.md)을 사용하여 많은 오류를 완화할 수 있습니다.

Microsoft.Data.Sqlite에서 사용 중이거나 잠금 오류가 발생할 때마다 성공하거나 명령 시간 제한에 도달할 때까지 자동으로 다시 시도합니다.

<xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>을 설정하여 명령 제한 시간을 늘릴 수 있습니다. 기본 제한 시간은 30초입니다. `0` 값은 시간 제한이 없음을 의미합니다.

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

Microsoft.Data.Sqlite는 경우에 따라 암시적 명령 개체를 만들어야 합니다. 예를 들면 BeginTransaction 중에 만들어야 합니다. 이러한 명령에 대한 시간 제한을 설정하려면 <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>을 사용합니다.

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a>참조

* [SQLite 오류 코드](https://www.sqlite.org/rescode.html)
* [SQLite의 파일 잠금](https://www.sqlite.org/lockingv3.html)
* [공유 캐시 모드](https://www.sqlite.org/sharedcache.html)
* [미리 쓰기 로깅](https://www.sqlite.org/wal.html)
