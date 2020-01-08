---
title: 메모리 내 데이터베이스
ms.date: 12/13/2019
description: 메모리 내 SQLite 데이터베이스를 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: b125ff5aa4128bd4c3ff558c5573b7d11802090a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450467"
---
# <a name="in-memory-databases"></a><span data-ttu-id="a64f0-103">메모리 내 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="a64f0-103">In-memory databases</span></span>

<span data-ttu-id="a64f0-104">SQLite 메모리 내 데이터베이스는 디스크에 저장 되는 것이 아니라 메모리에 완전히 저장 된 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a64f0-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="a64f0-105">특수 한 데이터 원본 파일 이름 `:memory:`를 사용 하 여 메모리 내 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a64f0-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="a64f0-106">연결이 닫히면 데이터베이스가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a64f0-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="a64f0-107">`:memory:`사용 하는 경우 각 연결에서 자체 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a64f0-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="a64f0-108">공유 가능한 메모리 내 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="a64f0-108">Shareable in-memory databases</span></span>

<span data-ttu-id="a64f0-109">`Mode=Memory`를 사용 하 고 연결 문자열에 `Cache=Shared`를 사용 하 여 여러 연결 간에 메모리 내 데이터베이스를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a64f0-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="a64f0-110">`Data Source` 키워드는 메모리 내 데이터베이스에 이름을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a64f0-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="a64f0-111">동일한 이름을 사용 하는 연결 문자열은 동일한 메모리 내 데이터베이스에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="a64f0-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="a64f0-112">하나 이상의 연결이 열린 상태로 유지 되는 한 데이터베이스는 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a64f0-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="a64f0-113">이를 보여 주는 [샘플](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) 은 GitHub에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a64f0-113">A [sample](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
