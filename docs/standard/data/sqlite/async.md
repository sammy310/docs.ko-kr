---
title: 비동기 제한 사항
ms.date: 09/04/2020
description: 비동기 API의 제한 사항과 대신 사용할 수 있는 몇 가지 대안에 대해 설명합니다.
ms.openlocfilehash: 8b14fcfeb12d331d8d43ca6d77332007a12ae5dc
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515997"
---
# <a name="async-limitations"></a><span data-ttu-id="daba0-103">비동기 제한 사항</span><span class="sxs-lookup"><span data-stu-id="daba0-103">Async limitations</span></span>

<span data-ttu-id="daba0-104">SQLite는 비동기 I/O를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daba0-104">SQLite doesn't support asynchronous I/O.</span></span> <span data-ttu-id="daba0-105">비동기 ADO.NET 메서드는 Microsoft.Data.Sqlite에서 동기적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="daba0-105">Async ADO.NET methods will execute synchronously in Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="daba0-106">호출하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="daba0-106">Avoid calling them.</span></span>

<span data-ttu-id="daba0-107">대신 [공유 캐시](connection-strings.md#cache) 및 [미리 쓰기 로깅](https://www.sqlite.org/wal.html)을 사용하여 성능 및 동시성을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="daba0-107">Instead, use a [shared cache](connection-strings.md#cache) and [write-ahead logging](https://www.sqlite.org/wal.html) to improve performance and concurrency.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> <span data-ttu-id="daba0-108">미리 쓰기 로깅은 [Entity Framework Core](/ef/core/)를 사용하여 만든 데이터베이스에서 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="daba0-108">Write-ahead logging is enabled by default on databases created using [Entity Framework Core](/ef/core/).</span></span>
