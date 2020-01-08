---
title: 트랜잭션
ms.date: 12/13/2019
description: 트랜잭션을 사용 하는 방법을 알아봅니다.
ms.openlocfilehash: 4b72a1573a560ffd1bfd0f54d46ab3b135280976
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450383"
---
# <a name="transactions"></a>트랜잭션

트랜잭션을 사용 하면 여러 SQL 문을 하나의 원자 단위로 데이터베이스에 커밋한 단일 작업 단위로 그룹화 할 수 있습니다. 트랜잭션의 문이 실패 하면 이전 문에서 변경한 내용을 롤백할 수 있습니다. 트랜잭션이 시작 될 때 데이터베이스의 초기 상태는 유지 됩니다. 트랜잭션을 사용 하면 데이터베이스를 한 번에 여러 번 변경 하는 경우 SQLite의 성능도 향상 됩니다.

## <a name="concurrency"></a>동시성

SQLite에서는 한 번에 하나의 트랜잭션만 데이터베이스에서 보류 중인 변경 내용을 포함할 수 있습니다. 이로 인해 <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A>에 대 한 호출과 <xref:Microsoft.Data.Sqlite.SqliteCommand>의 `Execute` 메서드를 완료 하는 데 시간이 너무 오래 걸리는 경우 시간이 초과 될 수 있습니다.

잠금, 다시 시도 및 제한 시간에 대 한 자세한 내용은 [데이터베이스 오류](database-errors.md)를 참조 하세요.

## <a name="isolation-levels"></a>격리 수준

트랜잭션은 기본적으로 SQLite에서 **serialize** 할 수 있습니다. 이 격리 수준은 트랜잭션 내에서 수행 된 모든 변경 내용이 완전히 격리 되도록 보장 합니다. 트랜잭션 외부에서 실행 된 다른 문은 트랜잭션의 변경 내용에 의해 영향을 받지 않습니다.

SQLite는 공유 캐시를 사용 하는 경우 **커밋되지 않은 읽기** 도 지원 합니다. 이 수준은 더티 읽기, 반복할 읽기 및 phantoms를 허용 합니다.

- *커밋되지 않은 읽기* 는 한 트랜잭션에서 보류 중인 변경 내용이 트랜잭션 외부의 쿼리에서 반환 되었지만 트랜잭션의 변경 내용이 롤백되는 경우에 발생 합니다. 결과에는 실제로 데이터베이스에 커밋되지 않은 데이터가 포함 됩니다.

- *반복할 읽기* 는 트랜잭션이 동일한 행을 두 번 쿼리할 때 발생 하지만 다른 트랜잭션이 두 쿼리 사이에서 변경 되었기 때문에 결과가 다릅니다.

- *Phantoms* 은 트랜잭션 중 쿼리의 where 절을 충족 하기 위해 변경 되거나 추가 되는 행입니다. 허용 되는 경우 동일한 쿼리에서 동일한 쿼리를 두 번 실행 하면 서로 다른 행이 반환 될 수 있습니다.

IsolationLevel에 전달 된 <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A>를 최소 수준으로 처리 합니다. 실제 격리 수준은 커밋되지 않은 읽기 또는 serializable로 승격 됩니다.

다음 코드는 커밋되지 않은 읽기를 시뮬레이션 합니다. 연결 문자열에는 `Cache=Shared`포함 되어야 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]
