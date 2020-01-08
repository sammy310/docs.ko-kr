---
title: 데이터베이스 오류
ms.date: 12/13/2019
description: 라이브러리에서 데이터베이스 오류 및 받아볼를 처리 하는 방법을 설명 합니다.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450491"
---
# <a name="database-errors"></a><span data-ttu-id="90569-103">데이터베이스 오류</span><span class="sxs-lookup"><span data-stu-id="90569-103">Database errors</span></span>

<span data-ttu-id="90569-104">SQLite 오류가 발생 하면 <xref:Microsoft.Data.Sqlite.SqliteException>이 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90569-104"><xref:Microsoft.Data.Sqlite.SqliteException> is thrown when a SQLite error is encountered.</span></span> <span data-ttu-id="90569-105">메시지는 SQLite에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90569-105">The message is provided by SQLite.</span></span> <span data-ttu-id="90569-106">`SqliteErrorCode` 및 `SqliteExtendedErrorCode` 속성은 오류에 대 한 SQLite [결과 코드](https://www.sqlite.org/rescode.html) 를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="90569-106">The `SqliteErrorCode` and `SqliteExtendedErrorCode` properties contain the SQLite [result code](https://www.sqlite.org/rescode.html) of the error.</span></span>

<span data-ttu-id="90569-107">오류가 발생 하는 경우에는 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90569-107">Errors may be encountered any time the Microsoft.Data.Sqlite interacts with the native SQLite library.</span></span> <span data-ttu-id="90569-108">다음 목록에서는 오류가 발생할 수 있는 일반적인 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90569-108">The following list shows the common scenarios where errors can occur:</span></span>

* <span data-ttu-id="90569-109">연결을 여는 경우</span><span class="sxs-lookup"><span data-stu-id="90569-109">Opening a connection.</span></span>
* <span data-ttu-id="90569-110">트랜잭션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="90569-110">Beginning a transaction.</span></span>
* <span data-ttu-id="90569-111">명령 실행</span><span class="sxs-lookup"><span data-stu-id="90569-111">Executing a command.</span></span>
* <span data-ttu-id="90569-112"><xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>를 호출할 경우</span><span class="sxs-lookup"><span data-stu-id="90569-112">Calling <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span></span>

<span data-ttu-id="90569-113">앱에서 이러한 오류를 처리 하는 방법을 신중 하 게 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="90569-113">Consider carefully how your app will handle these errors.</span></span>

## <a name="locking-retries-and-timeouts"></a><span data-ttu-id="90569-114">잠금, 다시 시도 및 시간 제한</span><span class="sxs-lookup"><span data-stu-id="90569-114">Locking, retries, and timeouts</span></span>

<span data-ttu-id="90569-115">SQLite는 테이블 및 데이터베이스 파일을 잠그는 경우 적극적입니다.</span><span class="sxs-lookup"><span data-stu-id="90569-115">SQLite is aggressive when it comes to locking tables and database files.</span></span> <span data-ttu-id="90569-116">앱에서 동시 데이터베이스 액세스를 사용할 수 있는 경우 사용 중 및 잠긴 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90569-116">If your app enables any concurrent database access, you'll likely encounter busy and locked errors.</span></span> <span data-ttu-id="90569-117">[공유 캐시](connection-strings.md#cache) 및 [미리 쓰기 로깅을](async.md)사용 하 여 많은 오류를 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90569-117">You can mitigate many errors by using a [shared cache](connection-strings.md#cache) and [write-ahead logging](async.md).</span></span>

<span data-ttu-id="90569-118">Microsoft. Data. Sqlite에서 사용 중이거나 잠금 오류가 발생할 때마다 성공할 때까지 자동으로 다시 시도 하거나 명령 시간 제한에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="90569-118">Whenever Microsoft.Data.Sqlite encounters a busy or locked error, it will automatically retry until it succeeds or the command timeout is reached.</span></span>

<span data-ttu-id="90569-119"><xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>를 설정 하 여 명령 제한 시간을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90569-119">You can increase the timeout of command by setting <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>.</span></span> <span data-ttu-id="90569-120">기본 제한 시간은 30 초입니다.</span><span class="sxs-lookup"><span data-stu-id="90569-120">The default timeout is 30 seconds.</span></span> <span data-ttu-id="90569-121">`0` 값은 시간 제한이 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="90569-121">A value of `0` means no timeout.</span></span>

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

<span data-ttu-id="90569-122">Microsoft의 경우에 따라 암시적 명령 개체를 만들어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90569-122">Microsoft.Data.Sqlite sometimes needs to create an implicit command object.</span></span> <span data-ttu-id="90569-123">예를 들면 BeginTransaction 중입니다.</span><span class="sxs-lookup"><span data-stu-id="90569-123">For example, during BeginTransaction.</span></span> <span data-ttu-id="90569-124">이러한 명령에 대 한 제한 시간을 설정 하려면 <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="90569-124">To set the timeout for these commands, use <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.</span></span>

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a><span data-ttu-id="90569-125">참조</span><span class="sxs-lookup"><span data-stu-id="90569-125">See also</span></span>

* [<span data-ttu-id="90569-126">SQLite 오류 코드</span><span class="sxs-lookup"><span data-stu-id="90569-126">SQLite Error Codes</span></span>](https://www.sqlite.org/rescode.html)
* [<span data-ttu-id="90569-127">SQLite의 파일 잠금</span><span class="sxs-lookup"><span data-stu-id="90569-127">File Locking In SQLite</span></span>](https://www.sqlite.org/lockingv3.html)
* [<span data-ttu-id="90569-128">공유 캐시 모드</span><span class="sxs-lookup"><span data-stu-id="90569-128">Shared-Cache Mode</span></span>](https://www.sqlite.org/sharedcache.html)
* [<span data-ttu-id="90569-129">미리 쓰기 로깅</span><span class="sxs-lookup"><span data-stu-id="90569-129">Write-Ahead Logging</span></span>](https://www.sqlite.org/wal.html)
