---
title: 비동기 제한 사항
ms.date: 12/13/2019
description: 비동기 Api의 제한 사항 및 대신 사용할 수 있는 몇 가지 대안에 대해 설명 합니다.
ms.openlocfilehash: 350237dc5c03023f60e9680e8b9c94aabb62606f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450335"
---
# <a name="async-limitations"></a><span data-ttu-id="b80b0-103">비동기 제한 사항</span><span class="sxs-lookup"><span data-stu-id="b80b0-103">Async limitations</span></span>

<span data-ttu-id="b80b0-104">SQLite는 비동기 i/o를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b80b0-104">SQLite doesn't support asynchronous I/O.</span></span> <span data-ttu-id="b80b0-105">Async ADO.NET 메서드는 Microsoft. Data. Sqlite에서 동기적으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b80b0-105">Async ADO.NET methods will execute synchronously in Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="b80b0-106">호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b80b0-106">Avoid calling them.</span></span>

<span data-ttu-id="b80b0-107">대신 [미리 쓰기 로깅을](https://www.sqlite.org/wal.html) 사용 하 여 성능 및 동시성을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b80b0-107">Instead, use [write-ahead logging](https://www.sqlite.org/wal.html) to improve performance and concurrency.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> <span data-ttu-id="b80b0-108">미리 쓰기 로깅은 [Entity Framework Core](/ef/core/)를 사용 하 여 만든 데이터베이스에서 기본적으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b80b0-108">Write-ahead logging is enabled by default on databases created using [Entity Framework Core](/ef/core/).</span></span>
