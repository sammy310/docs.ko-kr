---
title: Blob I/O
ms.date: 12/13/2019
description: SQLite의 BLOB I/O 기능을 사용하는 방법을 알아봅니다.
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450305"
---
# <a name="blob-io"></a>Blob I/O

데이터베이스에서 데이터를 스트리밍하여 큰 개체를 읽고 쓰는 동안 메모리 사용량을 줄일 수 있습니다. 이는 데이터를 구문 분석하거나 변환할 때 특히 유용할 수 있습니다.

정상적으로 행을 삽입하여 시작합니다. `zeroblob()` SQL 함수를 사용하여 데이터베이스에서 큰 개체를 저장할 공간을 할당합니다. `last_insert_rowid()` 함수는 해당 rowid를 가져오는 편리한 방법을 제공합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

행을 삽입한 후 스트림을 열고 <xref:Microsoft.Data.Sqlite.SqliteBlob>를 사용하여 큰 개체를 작성합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

데이터베이스에서 큰 개체를 스트리밍하려면 여기에 표시된 대로 큰 개체의 열과 함께 rowid 또는 해당 별칭 중 하나를 선택해야 합니다. rowid를 선택하지 않으면 전체 개체가 메모리에 로드됩니다. `GetStream()`이 반환하는 개체는 올바르게 수행되면 `SqliteBlob`입니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
