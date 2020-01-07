---
title: 데이터베이스 오류
ms.date: 12/13/2019
description: 라이브러리에서 데이터베이스 오류 및 받아볼를 처리 하는 방법을 설명 합니다.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450491"
---
# <a name="database-errors"></a>데이터베이스 오류

SQLite 오류가 발생 하면 <xref:Microsoft.Data.Sqlite.SqliteException>이 throw 됩니다. 메시지는 SQLite에서 제공 됩니다. `SqliteErrorCode` 및 `SqliteExtendedErrorCode` 속성은 오류에 대 한 SQLite [결과 코드](https://www.sqlite.org/rescode.html) 를 포함 합니다.

오류가 발생 하는 경우에는 문제가 발생할 수 있습니다. 다음 목록에서는 오류가 발생할 수 있는 일반적인 시나리오를 보여 줍니다.

* 연결을 여는 경우
* 트랜잭션을 시작 합니다.
* 명령 실행
* <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>를 호출할 경우

앱에서 이러한 오류를 처리 하는 방법을 신중 하 게 고려 합니다.

## <a name="locking-retries-and-timeouts"></a>잠금, 다시 시도 및 시간 제한

SQLite는 테이블 및 데이터베이스 파일을 잠그는 경우 적극적입니다. 앱에서 동시 데이터베이스 액세스를 사용할 수 있는 경우 사용 중 및 잠긴 오류가 발생할 수 있습니다. [공유 캐시](connection-strings.md#cache) 및 [미리 쓰기 로깅을](async.md)사용 하 여 많은 오류를 완화할 수 있습니다.

Microsoft. Data. Sqlite에서 사용 중이거나 잠금 오류가 발생할 때마다 성공할 때까지 자동으로 다시 시도 하거나 명령 시간 제한에 도달 합니다.

<xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>를 설정 하 여 명령 제한 시간을 늘릴 수 있습니다. 기본 제한 시간은 30 초입니다. `0` 값은 시간 제한이 없음을 의미 합니다.

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

Microsoft의 경우에 따라 암시적 명령 개체를 만들어야 할 수도 있습니다. 예를 들면 BeginTransaction 중입니다. 이러한 명령에 대 한 제한 시간을 설정 하려면 <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>을 사용 합니다.

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a>참조

* [SQLite 오류 코드](https://www.sqlite.org/rescode.html)
* [SQLite의 파일 잠금](https://www.sqlite.org/lockingv3.html)
* [공유 캐시 모드](https://www.sqlite.org/sharedcache.html)
* [미리 쓰기 로깅](https://www.sqlite.org/wal.html)
