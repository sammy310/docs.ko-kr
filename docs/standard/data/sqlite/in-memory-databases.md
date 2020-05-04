---
title: 메모리 내 데이터베이스
ms.date: 12/13/2019
description: 메모리 내 SQLite 데이터베이스를 사용하는 방법을 알아봅니다.
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391210"
---
# <a name="in-memory-databases"></a><span data-ttu-id="827ab-103">메모리 내 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="827ab-103">In-memory databases</span></span>

<span data-ttu-id="827ab-104">SQLite 메모리 내 데이터베이스는 디스크가 아니라 전적으로 메모리에 저장되는 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="827ab-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="827ab-105">특수한 데이터 원본 파일 이름 `:memory:`를 사용하여 메모리 내 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="827ab-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="827ab-106">연결이 닫히면 데이터베이스가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="827ab-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="827ab-107">`:memory:`를 사용하는 경우 각 연결에서 자체 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="827ab-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="827ab-108">공유 가능한 메모리 내 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="827ab-108">Shareable in-memory databases</span></span>

<span data-ttu-id="827ab-109">연결 문자열에 `Mode=Memory` 및 `Cache=Shared`를 사용하여 여러 연결 간에 메모리 내 데이터베이스를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827ab-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="827ab-110">`Data Source` 키워드는 메모리 내 데이터베이스에 이름을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="827ab-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="827ab-111">동일한 이름을 사용하는 연결 문자열은 동일한 메모리 내 데이터베이스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="827ab-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="827ab-112">하나 이상의 연결이 열린 상태로 유지되는 한 데이터베이스는 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="827ab-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="827ab-113">이를 보여 주는 [샘플](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs)은 GitHub에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="827ab-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
