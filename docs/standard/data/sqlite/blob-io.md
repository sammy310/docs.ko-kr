---
title: Blob i/o
ms.date: 12/13/2019
description: SQLite의 BLOB i/o 기능을 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450305"
---
# <a name="blob-io"></a>Blob i/o

데이터베이스에서 데이터를 스트리밍하 고 데이터베이스에서 데이터를 스트리밍하 여 많은 개체를 읽고 쓰는 동안 메모리 사용량을 줄일 수 있습니다. 이는 데이터를 구문 분석 하거나 변환할 때 특히 유용할 수 있습니다.

행을 보통으로 삽입 하 여 시작 합니다. `zeroblob()` SQL 함수를 사용 하 여 데이터베이스에서 많은 개체를 저장할 공간을 할당 합니다. `last_insert_rowid()` 함수는 해당 rowid를 가져오는 편리한 방법을 제공 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

행을 삽입 한 후 스트림을 열어 <xref:Microsoft.Data.Sqlite.SqliteBlob>를 사용 하 여 large 개체를 작성 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

데이터베이스에서 많은 개체를 스트리밍하려면 대량 개체의 열과 함께 여기에 표시 된 대로 rowid 또는 해당 별칭 중 하나를 선택 해야 합니다. Rowid를 선택 하지 않으면 전체 개체가 메모리에 로드 됩니다. `GetStream()`에서 반환 되는 개체는 올바르게 수행 되 면 `SqliteBlob` 됩니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
