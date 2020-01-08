---
title: 대량 삽입
ms.date: 12/13/2019
description: 데이터베이스에 대 한 여러 변경 작업을 수행할 때 사용할 수 있는 성능 팁입니다.
ms.openlocfilehash: 9d87d5c8d70f8e70479f9aa02b7802f73b88de9e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450299"
---
# <a name="bulk-insert"></a><span data-ttu-id="64cd3-103">대량 삽입</span><span class="sxs-lookup"><span data-stu-id="64cd3-103">Bulk insert</span></span>

<span data-ttu-id="64cd3-104">SQLite에는 데이터를 대량 삽입 하는 특별 한 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64cd3-104">SQLite doesn't have any special way to bulk insert data.</span></span> <span data-ttu-id="64cd3-105">데이터를 삽입 하거나 업데이트할 때 최적의 성능을 얻으려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64cd3-105">To get optimal performance when inserting or updating data, ensure that you do the following:</span></span>

- <span data-ttu-id="64cd3-106">트랜잭션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="64cd3-106">Use a transaction.</span></span>
- <span data-ttu-id="64cd3-107">동일한 매개 변수가 있는 명령을 다시 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="64cd3-107">Reuse the same parameterized command.</span></span> <span data-ttu-id="64cd3-108">이후 실행은 첫 번째 실행에 대 한 컴파일을 다시 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="64cd3-108">Subsequent executions will reuse the compilation of the first one.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
