---
title: 상호 운용성
ms.date: 12/13/2019
description: 다른 SQLite 라이브러리와 상호 운용하는 방법을 알아봅니다.
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450461"
---
# <a name="interoperability"></a>상호 운용성

Microsoft.Data.Sqlite는 SQLitePCLRaw를 사용하여 네이티브 SQLite 라이브러리와 상호 작용합니다. SQLitePCLRaw는 네이티브 SQLite API를 통해 씬 .NET API를 제공합니다. SqliteConnection 및 SqliteDataReader는 이러한 API를 직접 호출할 수 있는 기본 SQLitePCLRaw 개체에 대한 액세스를 제공합니다.

다음 예제에서는 `sqlite3_trace`를 호출하여 실행된 SQL 문을 콘솔에 쓰는 방법을 보여줍니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

그리고 다음 예제에서는 `sqlite3_stmt_status`를 호출하여 SQL 문이 컴파일되는 SQLite 가상 머신 단계 수를 보여줍니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

SQLitePCLRaw 개체는 P/Invoke 추가 네이티브 SQLite API를 사용할 수 있도록 네이티브 개체에 포인터를 노출하기도 합니다.
