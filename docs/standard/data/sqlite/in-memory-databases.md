---
title: 메모리 내 데이터베이스
ms.date: 12/13/2019
description: 메모리 내 SQLite 데이터베이스를 사용하는 방법을 알아봅니다.
ms.openlocfilehash: fbda5787d95a9ce462752b985f847af0b0551fa6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555369"
---
# <a name="in-memory-databases"></a><span data-ttu-id="fee9c-103">메모리 내 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="fee9c-103">In-memory databases</span></span>

<span data-ttu-id="fee9c-104">SQLite 메모리 내 데이터베이스는 디스크가 아니라 전적으로 메모리에 저장되는 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="fee9c-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="fee9c-105">특수한 데이터 원본 파일 이름 `:memory:`를 사용하여 메모리 내 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fee9c-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="fee9c-106">연결이 닫히면 데이터베이스가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee9c-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="fee9c-107">`:memory:`를 사용하는 경우 각 연결에서 자체 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fee9c-107">When using `:memory:`, each connection creates its own database.</span></span>

```connectionstring
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="fee9c-108">공유 가능한 메모리 내 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="fee9c-108">Shareable in-memory databases</span></span>

<span data-ttu-id="fee9c-109">연결 문자열에 `Mode=Memory` 및 `Cache=Shared`를 사용하여 여러 연결 간에 메모리 내 데이터베이스를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee9c-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="fee9c-110">`Data Source` 키워드는 메모리 내 데이터베이스에 이름을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee9c-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="fee9c-111">동일한 이름을 사용하는 연결 문자열은 동일한 메모리 내 데이터베이스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="fee9c-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="fee9c-112">하나 이상의 연결이 열린 상태로 유지되는 한 데이터베이스는 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee9c-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="fee9c-113">이를 보여 주는 [샘플](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs)은 GitHub에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee9c-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```connectionstring
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
