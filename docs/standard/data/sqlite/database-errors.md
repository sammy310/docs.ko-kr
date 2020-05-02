---
title: 데이터베이스 오류
ms.date: 12/13/2019
description: 라이브러리에서 데이터베이스 오류 및 중지를 처리하는 방법을 설명합니다.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450491"
---
# <a name="database-errors"></a><span data-ttu-id="d870f-103">데이터베이스 오류</span><span class="sxs-lookup"><span data-stu-id="d870f-103">Database errors</span></span>

<span data-ttu-id="d870f-104">SQLite 오류가 발생하면 <xref:Microsoft.Data.Sqlite.SqliteException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-104"><xref:Microsoft.Data.Sqlite.SqliteException> is thrown when a SQLite error is encountered.</span></span> <span data-ttu-id="d870f-105">이 메시지는 SQLite에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-105">The message is provided by SQLite.</span></span> <span data-ttu-id="d870f-106">`SqliteErrorCode` 및 `SqliteExtendedErrorCode` 속성에는 오류의 SQLite [결과 코드](https://www.sqlite.org/rescode.html)가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-106">The `SqliteErrorCode` and `SqliteExtendedErrorCode` properties contain the SQLite [result code](https://www.sqlite.org/rescode.html) of the error.</span></span>

<span data-ttu-id="d870f-107">Microsoft.Data.Sqlite가 네이티브 SQLite 라이브러리와 상호 작용할 때마다 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-107">Errors may be encountered any time the Microsoft.Data.Sqlite interacts with the native SQLite library.</span></span> <span data-ttu-id="d870f-108">다음 목록에서는 오류가 발생할 수 있는 일반적인 시나리오를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-108">The following list shows the common scenarios where errors can occur:</span></span>

* <span data-ttu-id="d870f-109">연결을 여는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-109">Opening a connection.</span></span>
* <span data-ttu-id="d870f-110">트랜잭션을 시작하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-110">Beginning a transaction.</span></span>
* <span data-ttu-id="d870f-111">명령 실행</span><span class="sxs-lookup"><span data-stu-id="d870f-111">Executing a command.</span></span>
* <span data-ttu-id="d870f-112"><xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>을 호출하여.</span><span class="sxs-lookup"><span data-stu-id="d870f-112">Calling <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span></span>

<span data-ttu-id="d870f-113">앱에서 이러한 오류를 처리하는 방법을 신중하게 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-113">Consider carefully how your app will handle these errors.</span></span>

## <a name="locking-retries-and-timeouts"></a><span data-ttu-id="d870f-114">잠금, 다시 시도 및 시간 제한</span><span class="sxs-lookup"><span data-stu-id="d870f-114">Locking, retries, and timeouts</span></span>

<span data-ttu-id="d870f-115">SQLite는 테이블 및 데이터베이스 파일을 잠글 때 적극적입니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-115">SQLite is aggressive when it comes to locking tables and database files.</span></span> <span data-ttu-id="d870f-116">앱에서 동시 데이터베이스 액세스를 활성화하면 사용 중이거나 잠금 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-116">If your app enables any concurrent database access, you'll likely encounter busy and locked errors.</span></span> <span data-ttu-id="d870f-117">[공유 캐시](connection-strings.md#cache) 및 [미리 쓰기 로깅](async.md)을 사용하여 많은 오류를 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-117">You can mitigate many errors by using a [shared cache](connection-strings.md#cache) and [write-ahead logging](async.md).</span></span>

<span data-ttu-id="d870f-118">Microsoft.Data.Sqlite에서 사용 중이거나 잠금 오류가 발생할 때마다 성공하거나 명령 시간 제한에 도달할 때까지 자동으로 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-118">Whenever Microsoft.Data.Sqlite encounters a busy or locked error, it will automatically retry until it succeeds or the command timeout is reached.</span></span>

<span data-ttu-id="d870f-119"><xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>을 설정하여 명령 제한 시간을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-119">You can increase the timeout of command by setting <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>.</span></span> <span data-ttu-id="d870f-120">기본 제한 시간은 30초입니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-120">The default timeout is 30 seconds.</span></span> <span data-ttu-id="d870f-121">`0` 값은 시간 제한이 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-121">A value of `0` means no timeout.</span></span>

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

<span data-ttu-id="d870f-122">Microsoft.Data.Sqlite는 경우에 따라 암시적 명령 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-122">Microsoft.Data.Sqlite sometimes needs to create an implicit command object.</span></span> <span data-ttu-id="d870f-123">예를 들면 BeginTransaction 중에 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-123">For example, during BeginTransaction.</span></span> <span data-ttu-id="d870f-124">이러한 명령에 대한 시간 제한을 설정하려면 <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d870f-124">To set the timeout for these commands, use <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.</span></span>

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a><span data-ttu-id="d870f-125">참조</span><span class="sxs-lookup"><span data-stu-id="d870f-125">See also</span></span>

* [<span data-ttu-id="d870f-126">SQLite 오류 코드</span><span class="sxs-lookup"><span data-stu-id="d870f-126">SQLite Error Codes</span></span>](https://www.sqlite.org/rescode.html)
* [<span data-ttu-id="d870f-127">SQLite의 파일 잠금</span><span class="sxs-lookup"><span data-stu-id="d870f-127">File Locking In SQLite</span></span>](https://www.sqlite.org/lockingv3.html)
* [<span data-ttu-id="d870f-128">공유 캐시 모드</span><span class="sxs-lookup"><span data-stu-id="d870f-128">Shared-Cache Mode</span></span>](https://www.sqlite.org/sharedcache.html)
* [<span data-ttu-id="d870f-129">미리 쓰기 로깅</span><span class="sxs-lookup"><span data-stu-id="d870f-129">Write-Ahead Logging</span></span>](https://www.sqlite.org/wal.html)
