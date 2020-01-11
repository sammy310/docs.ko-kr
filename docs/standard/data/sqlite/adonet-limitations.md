---
title: ADO.NET 제한 사항
ms.date: 12/13/2019
description: 발생할 수 있는 몇 가지 ADO.NET 제한 사항에 대해 설명 합니다.
ms.openlocfilehash: 8664b73071fc859ed30080f549b05e7d6ed020f4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901262"
---
# <a name="adonet-limitations"></a><span data-ttu-id="3e396-103">ADO.NET 제한 사항</span><span class="sxs-lookup"><span data-stu-id="3e396-103">ADO.NET limitations</span></span>

<span data-ttu-id="3e396-104">ADO.NET는 많은 수의 추상화 구현을 제공 하지만 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-104">Microsoft.Data.Sqlite provides implementations of many of the ADO.NET abstractions, but there are some limitations.</span></span>

## <a name="database-schema-information"></a><span data-ttu-id="3e396-105">데이터베이스 스키마 정보</span><span class="sxs-lookup"><span data-stu-id="3e396-105">Database schema information</span></span>

<span data-ttu-id="3e396-106"><xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> 메서드를 사용 하 여 쿼리 결과에 대 한 메타 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-106">Metadata about query results is available using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method.</span></span>

<span data-ttu-id="3e396-107">`DbConnection.GetSchema()` 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-107">`DbConnection.GetSchema()` isn't implemented.</span></span> <span data-ttu-id="3e396-108">이 API는 잘 정의 되어 있지 않으므로 [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) 테이블 및 [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA와 같은 표준 SQLite api를 사용 하 여 데이터베이스 메타 데이터를 직접 검색 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-108">This API isn't well-defined, so we recommend retrieving database metadata directly using standard SQLite APIs like the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and the [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA.</span></span>

<span data-ttu-id="3e396-109">자세한 내용은 [메타 데이터](metadata.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e396-109">For more information, see [Metadata](metadata.md).</span></span>

## <a name="systemtransactions"></a><span data-ttu-id="3e396-110">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="3e396-110">System.Transactions</span></span>

<span data-ttu-id="3e396-111">Microsoft. Sqlite는 아직 시스템 트랜잭션을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-111">Microsoft.Data.Sqlite doesn't yet support System.Transactions.</span></span> <span data-ttu-id="3e396-112">대신 ADO.NET 트랜잭션을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e396-112">Use ADO.NET transactions instead.</span></span> <span data-ttu-id="3e396-113">자세한 내용은 [트랜잭션](transactions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e396-113">For more information, see [Transactions](transactions.md).</span></span>

<span data-ttu-id="3e396-114">문제 [#13825](https://github.com/dotnet/efcore/issues/13825)에서 시스템이 트랜잭션을 지원 하지 않는다는 의견을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-114">Provide feedback about the lack of support for System.Transactions on issue [#13825](https://github.com/dotnet/efcore/issues/13825).</span></span>

## <a name="data-adapters"></a><span data-ttu-id="3e396-115">데이터 어댑터</span><span class="sxs-lookup"><span data-stu-id="3e396-115">Data adapters</span></span>

<span data-ttu-id="3e396-116">`DbDataAdapter`은 (는) Microsoft에서 아직 구현 되지 않았습니다. Sqlite.</span><span class="sxs-lookup"><span data-stu-id="3e396-116">`DbDataAdapter` isn't yet implemented by Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="3e396-117">즉, ADO.NET `DataSet`와 `DataTable`만 사용 하 여 데이터를 로드 하 고 업데이트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-117">This means you can only use ADO.NET `DataSet` and `DataTable` to load data and not update it.</span></span>

<span data-ttu-id="3e396-118">`DbDataAdapter`구현에 대 한 피드백을 제공 하려면 문제 [#13838](https://github.com/dotnet/efcore/issues/13838) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-118">Use issue [#13838](https://github.com/dotnet/efcore/issues/13838) to provide feedback about implementing `DbDataAdapter`.</span></span>

## <a name="output-parameters"></a><span data-ttu-id="3e396-119">출력 매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e396-119">Output parameters</span></span>

<span data-ttu-id="3e396-120">SQLite는 출력 매개 변수를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-120">SQLite doesn't support output parameters.</span></span>

## <a name="positional-parameters"></a><span data-ttu-id="3e396-121">위치 매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e396-121">Positional parameters</span></span>

<span data-ttu-id="3e396-122">Microsoft. Data. Sqlite는 명명 된 [매개 변수만](parameters.md)지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-122">Microsoft.Data.Sqlite only supports named [parameters](parameters.md).</span></span> <span data-ttu-id="3e396-123">위치 매개 변수는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-123">Positional parameters aren't supported.</span></span>

## <a name="stored-procedures"></a><span data-ttu-id="3e396-124">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="3e396-124">Stored procedures</span></span>

<span data-ttu-id="3e396-125">SQLite는 저장 프로시저를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-125">SQLite doesn't support stored procedures.</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="3e396-126">격리 수준</span><span class="sxs-lookup"><span data-stu-id="3e396-126">Isolation levels</span></span>

<span data-ttu-id="3e396-127">SQLite 트랜잭션에서는 `Chaos` 및 `Snapshot` 격리 수준이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e396-127">The `Chaos` and `Snapshot` isolation levels aren't supported in SQLite transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e396-128">참조</span><span class="sxs-lookup"><span data-stu-id="3e396-128">See also</span></span>

* [<span data-ttu-id="3e396-129">비동기 제한 사항</span><span class="sxs-lookup"><span data-stu-id="3e396-129">Async limitations</span></span>](async.md)
* [<span data-ttu-id="3e396-130">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3e396-130">Data types</span></span>](types.md)
* [<span data-ttu-id="3e396-131">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="3e396-131">Transactions</span></span>](transactions.md)
