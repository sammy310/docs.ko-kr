---
title: 의
ms.date: 12/13/2019
description: 트랜잭션을 사용하는 방법을 알아봅니다.
ms.openlocfilehash: 4b72a1573a560ffd1bfd0f54d46ab3b135280976
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450383"
---
# <a name="transactions"></a><span data-ttu-id="e308c-103">의</span><span class="sxs-lookup"><span data-stu-id="e308c-103">Transactions</span></span>

<span data-ttu-id="e308c-104">트랜잭션을 사용하면 여러 SQL 문을 하나의 원자 단위로 데이터베이스에 커밋된 단일 작업 단위로 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-104">Transactions let you group multiple SQL statements into a single unit of work that is committed to the database as one atomic unit.</span></span> <span data-ttu-id="e308c-105">트랜잭션의 명령문이 실패하면 이전 명령문에서 변경한 내용을 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-105">If any statement in the transaction fails, changes made by the previous statements can be rolled back.</span></span> <span data-ttu-id="e308c-106">트랜잭션이 시작될 때 데이터베이스의 초기 상태는 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-106">The initial state of the database when the transaction was started is preserved.</span></span> <span data-ttu-id="e308c-107">트랜잭션을 사용하면 데이터베이스를 동시에 여러 번 변경할 때 SQLite의 성능을 개선할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-107">Using a transaction can also improve performance on SQLite when making numerous changes to the database at once.</span></span>

## <a name="concurrency"></a><span data-ttu-id="e308c-108">동시성</span><span class="sxs-lookup"><span data-stu-id="e308c-108">Concurrency</span></span>

<span data-ttu-id="e308c-109">SQLite에서는 한 번에 하나의 트랜잭션만 데이터베이스에 보류 중인 변경 내용을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-109">In SQLite, only one transaction is allowed to have changes pending in the database at a time.</span></span> <span data-ttu-id="e308c-110">이로 인해 다른 트랜잭션을 완료하는 데 시간이 너무 오래 걸리면 <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> 및 <xref:Microsoft.Data.Sqlite.SqliteCommand>의 `Execute` 메서드에 대한 호출이 시간 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-110">Because of this, calls to <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> and the `Execute` methods on <xref:Microsoft.Data.Sqlite.SqliteCommand> may time out if another transaction takes too long to complete.</span></span>

<span data-ttu-id="e308c-111">잠금, 다시 시도 및 시간 제한에 대한 자세한 내용은 [데이터 베이스 오류](database-errors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e308c-111">For more information about locking, retries, and timeouts, see [Database errors](database-errors.md).</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="e308c-112">격리 수준</span><span class="sxs-lookup"><span data-stu-id="e308c-112">Isolation levels</span></span>

<span data-ttu-id="e308c-113">트랜잭션은 기본적으로 SQLite에서 **직렬화 가능**입니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-113">Transactions are **serializable** by default in SQLite.</span></span> <span data-ttu-id="e308c-114">이 격리 수준은 트랜잭션 내에서 수행된 모든 변경 내용이 완전히 격리되도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-114">This isolation level guarantees that any changes made within a transaction are completely isolated.</span></span> <span data-ttu-id="e308c-115">트랜잭션 외부에서 실행된 다른 명령문은 트랜잭션의 변경 내용에 의해 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-115">Other statements executed outside of the transaction aren't affected by the transaction's changes.</span></span>

<span data-ttu-id="e308c-116">SQLite는 공유 캐시를 사용할 때 **커밋되지 않은 읽기**도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-116">SQLite also supports **read uncommitted** when using a shared cache.</span></span> <span data-ttu-id="e308c-117">이 수준은 커밋되지 않은 데이터 읽기, 반복되지 않는 읽기 및 팬텀을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-117">This level allows dirty reads, nonrepeatable reads, and phantoms:</span></span>

- <span data-ttu-id="e308c-118">한 트랜잭션에서 보류 중인 변경 내용이 트랜잭션 외부의 쿼리에 의해 반환될 때 *커밋되지 않은 데이터 읽기*가 발생하지만 트랜잭션의 변경 내용은 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-118">A *dirty read* occurs when changes pending in one transaction are returned by a query outside of the transaction, but the changes in the transaction are rolled back.</span></span> <span data-ttu-id="e308c-119">결과에는 실제로 데이터베이스에 커밋되지 않은 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-119">The results contain data that was never actually committed to the database.</span></span>

- <span data-ttu-id="e308c-120">*반복되지 않는 읽기*는 트랜잭션이 동일한 행을 두 번 쿼리할 때 발생하지만 다른 트랜잭션에 의해 두 쿼리 간에 변경되었기 때문에 결과가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-120">A *nonrepeatable read* occurs when a transaction queries same row twice, but the results are different because it was changed between the two queries by another transaction.</span></span>

- <span data-ttu-id="e308c-121">*팬텀*은 트랜잭션 중에 쿼리의 where 절을 충족하기 위해 변경되거나 추가되는 행입니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-121">*Phantoms* are rows that get changed or added to meet the where clause of a query during a transaction.</span></span> <span data-ttu-id="e308c-122">허용되는 경우 동일한 트랜잭션에서 두 번 실행될 때 동일한 쿼리가 다른 행을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-122">If allowed, the same query could return different rows when executed twice in the same transaction.</span></span>

<span data-ttu-id="e308c-123">Microsoft.Data.Sqlite는 <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A>에 전달된 IsolationLevel을 최소 수준으로 취급합니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-123">Microsoft.Data.Sqlite treats the IsolationLevel passed to <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> as a minimum level.</span></span> <span data-ttu-id="e308c-124">실제 격리 수준은 커밋되지 않은 읽기 또는 직렬화 가능 수준으로 승격됩니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-124">The actual isolation level will be promoted to either read uncommitted or serializable.</span></span>

<span data-ttu-id="e308c-125">다음 코드는 커밋되지 않은 데이터 읽기를 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-125">The following code simulates a dirty read.</span></span> <span data-ttu-id="e308c-126">참고: 연결 문자열에는 `Cache=Shared`가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e308c-126">Note, the connection string must include `Cache=Shared`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]
