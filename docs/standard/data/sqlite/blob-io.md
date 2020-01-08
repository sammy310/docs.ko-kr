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
# <a name="blob-io"></a><span data-ttu-id="cfea5-103">Blob i/o</span><span class="sxs-lookup"><span data-stu-id="cfea5-103">Blob I/O</span></span>

<span data-ttu-id="cfea5-104">데이터베이스에서 데이터를 스트리밍하 고 데이터베이스에서 데이터를 스트리밍하 여 많은 개체를 읽고 쓰는 동안 메모리 사용량을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfea5-104">You can reduce memory usage while reading and writing large objects by streaming the data into and out of the database.</span></span> <span data-ttu-id="cfea5-105">이는 데이터를 구문 분석 하거나 변환할 때 특히 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfea5-105">This can be especially useful when parsing or transforming the data.</span></span>

<span data-ttu-id="cfea5-106">행을 보통으로 삽입 하 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfea5-106">Start by inserting a row as normal.</span></span> <span data-ttu-id="cfea5-107">`zeroblob()` SQL 함수를 사용 하 여 데이터베이스에서 많은 개체를 저장할 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfea5-107">Use the `zeroblob()` SQL function to allocate space in the database to hold the large object.</span></span> <span data-ttu-id="cfea5-108">`last_insert_rowid()` 함수는 해당 rowid를 가져오는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfea5-108">The `last_insert_rowid()` function provides a convenient way to get its rowid.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

<span data-ttu-id="cfea5-109">행을 삽입 한 후 스트림을 열어 <xref:Microsoft.Data.Sqlite.SqliteBlob>를 사용 하 여 large 개체를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfea5-109">After inserting the row, open a stream to write the large object using <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

<span data-ttu-id="cfea5-110">데이터베이스에서 많은 개체를 스트리밍하려면 대량 개체의 열과 함께 여기에 표시 된 대로 rowid 또는 해당 별칭 중 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfea5-110">To stream the large object out of the database, you must select the rowid or one of its aliases as show here in addition to the large object's column.</span></span> <span data-ttu-id="cfea5-111">Rowid를 선택 하지 않으면 전체 개체가 메모리에 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfea5-111">If you don't select the rowid, the entire object will be loaded into memory.</span></span> <span data-ttu-id="cfea5-112">`GetStream()`에서 반환 되는 개체는 올바르게 수행 되 면 `SqliteBlob` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfea5-112">The object returned by `GetStream()` will be a `SqliteBlob` when done correctly.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
