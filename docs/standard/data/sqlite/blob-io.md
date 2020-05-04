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
# <a name="blob-io"></a><span data-ttu-id="6f056-103">Blob I/O</span><span class="sxs-lookup"><span data-stu-id="6f056-103">Blob I/O</span></span>

<span data-ttu-id="6f056-104">데이터베이스에서 데이터를 스트리밍하여 큰 개체를 읽고 쓰는 동안 메모리 사용량을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f056-104">You can reduce memory usage while reading and writing large objects by streaming the data into and out of the database.</span></span> <span data-ttu-id="6f056-105">이는 데이터를 구문 분석하거나 변환할 때 특히 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f056-105">This can be especially useful when parsing or transforming the data.</span></span>

<span data-ttu-id="6f056-106">정상적으로 행을 삽입하여 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6f056-106">Start by inserting a row as normal.</span></span> <span data-ttu-id="6f056-107">`zeroblob()` SQL 함수를 사용하여 데이터베이스에서 큰 개체를 저장할 공간을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6f056-107">Use the `zeroblob()` SQL function to allocate space in the database to hold the large object.</span></span> <span data-ttu-id="6f056-108">`last_insert_rowid()` 함수는 해당 rowid를 가져오는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f056-108">The `last_insert_rowid()` function provides a convenient way to get its rowid.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

<span data-ttu-id="6f056-109">행을 삽입한 후 스트림을 열고 <xref:Microsoft.Data.Sqlite.SqliteBlob>를 사용하여 큰 개체를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="6f056-109">After inserting the row, open a stream to write the large object using <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

<span data-ttu-id="6f056-110">데이터베이스에서 큰 개체를 스트리밍하려면 여기에 표시된 대로 큰 개체의 열과 함께 rowid 또는 해당 별칭 중 하나를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f056-110">To stream the large object out of the database, you must select the rowid or one of its aliases as show here in addition to the large object's column.</span></span> <span data-ttu-id="6f056-111">rowid를 선택하지 않으면 전체 개체가 메모리에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f056-111">If you don't select the rowid, the entire object will be loaded into memory.</span></span> <span data-ttu-id="6f056-112">`GetStream()`이 반환하는 개체는 올바르게 수행되면 `SqliteBlob`입니다.</span><span class="sxs-lookup"><span data-stu-id="6f056-112">The object returned by `GetStream()` will be a `SqliteBlob` when done correctly.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
