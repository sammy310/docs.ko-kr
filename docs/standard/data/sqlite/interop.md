---
title: 상호 운용성
ms.date: 12/13/2019
description: 다른 SQLite 라이브러리와 상호 운용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450461"
---
# <a name="interoperability"></a>상호 운용성

SQLitePCLRaw를 사용 하 여 네이티브 SQLite 라이브러리와 상호 작용 합니다. SQLitePCLRaw는 네이티브 SQLite API에 대 한 씬 .NET API를 제공 합니다. SqliteConnection 및 SqliteDataReader는 이러한 Api를 직접 호출할 수 있는 기본 SQLitePCLRaw 개체에 대 한 액세스를 제공 합니다.

다음 예에서는 `sqlite3_trace`를 호출 하 여 실행 된 SQL 문을 콘솔에 쓰는 방법을 보여 줍니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

다음 예에서는를 호출 하 여 SQL 문이 컴파일되는 SQLite 가상 컴퓨터 단계 수를 확인 하는 `sqlite3_stmt_status`를 보여 줍니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

SQLitePCLRaw 개체는 네이티브 개체에 대 한 포인터를 노출 하 여 추가 네이티브 SQLite Api를 호출할 수도 있습니다.
