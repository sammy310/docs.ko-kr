---
title: 온라인 백업
ms.date: 12/13/2019
description: SQLite의 온라인 백업 기능을 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d857dcb69f2b2d10b034a0abf222b30c2e20bb41
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901277"
---
# <a name="online-backup"></a>온라인 백업

SQLite는 앱이 실행 되는 동안 데이터베이스 파일을 백업할 수 있습니다. 이 기능은 `SqliteConnection`의 <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> 방법으로 서 Microsoft. Sqlite에서 사용할 수 있습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

현재는 `BackupDatabase` 데이터베이스를 가능한 한 빨리 백업 하 고 다른 연결에서 데이터베이스에 쓰는 것을 차단 합니다. 문제 [#13834](https://github.com/dotnet/efcore/issues/13834) 은 백그라운드에서 데이터베이스를 백업 하는 대체 API를 제공 하 고, 다른 연결에서 백업을 중단 하 고 데이터베이스에 쓸 수 있도록 합니다. 관심이 있는 경우 문제에 대 한 피드백을 제공 하세요.
