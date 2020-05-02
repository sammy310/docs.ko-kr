---
title: ADO.NET 제한 사항
ms.date: 12/13/2019
description: 발생할 수 있는 몇 가지 ADO.NET 제한 사항에 대해 설명합니다.
ms.openlocfilehash: 8664b73071fc859ed30080f549b05e7d6ed020f4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901262"
---
# <a name="adonet-limitations"></a><span data-ttu-id="5b68e-103">ADO.NET 제한 사항</span><span class="sxs-lookup"><span data-stu-id="5b68e-103">ADO.NET limitations</span></span>

<span data-ttu-id="5b68e-104">Microsoft.Data.Sqlite는 많은 ADO.NET 추상화 구현을 제공하지만 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-104">Microsoft.Data.Sqlite provides implementations of many of the ADO.NET abstractions, but there are some limitations.</span></span>

## <a name="database-schema-information"></a><span data-ttu-id="5b68e-105">데이터베이스 스키마 정보</span><span class="sxs-lookup"><span data-stu-id="5b68e-105">Database schema information</span></span>

<span data-ttu-id="5b68e-106"><xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> 메서드를 사용하여 쿼리 결과에 대한 메타데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-106">Metadata about query results is available using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method.</span></span>

<span data-ttu-id="5b68e-107">`DbConnection.GetSchema()`가 구현되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-107">`DbConnection.GetSchema()` isn't implemented.</span></span> <span data-ttu-id="5b68e-108">이 API는 제대로 정의되어 있지 않으므로 [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) 테이블과 [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA와 같은 표준 SQLite API를 사용하여 데이터베이스 메타데이터를 직접 검색하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-108">This API isn't well-defined, so we recommend retrieving database metadata directly using standard SQLite APIs like the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and the [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA.</span></span>

<span data-ttu-id="5b68e-109">자세한 내용은 [메타데이터](metadata.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b68e-109">For more information, see [Metadata](metadata.md).</span></span>

## <a name="systemtransactions"></a><span data-ttu-id="5b68e-110">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="5b68e-110">System.Transactions</span></span>

<span data-ttu-id="5b68e-111">Microsoft.Data.Sqlite는 아직 System.Transactions를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-111">Microsoft.Data.Sqlite doesn't yet support System.Transactions.</span></span> <span data-ttu-id="5b68e-112">대신 ADO.NET 트랜잭션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-112">Use ADO.NET transactions instead.</span></span> <span data-ttu-id="5b68e-113">자세한 내용은 [트랜잭션](transactions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b68e-113">For more information, see [Transactions](transactions.md).</span></span>

<span data-ttu-id="5b68e-114">[#13825](https://github.com/dotnet/efcore/issues/13825) 문제에 대한 System.Transactions 지원 부족에 대한 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-114">Provide feedback about the lack of support for System.Transactions on issue [#13825](https://github.com/dotnet/efcore/issues/13825).</span></span>

## <a name="data-adapters"></a><span data-ttu-id="5b68e-115">데이터 어댑터</span><span class="sxs-lookup"><span data-stu-id="5b68e-115">Data adapters</span></span>

<span data-ttu-id="5b68e-116">`DbDataAdapter`는 아직 Microsoft.Data.Sqlite에 의해 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-116">`DbDataAdapter` isn't yet implemented by Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="5b68e-117">즉, ADO.NET `DataSet` 및 `DataTable`만 사용하여 데이터를 로드하고 업데이트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-117">This means you can only use ADO.NET `DataSet` and `DataTable` to load data and not update it.</span></span>

<span data-ttu-id="5b68e-118">[#13838](https://github.com/dotnet/efcore/issues/13838) 문제를 사용하여 `DbDataAdapter` 구현에 대한 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-118">Use issue [#13838](https://github.com/dotnet/efcore/issues/13838) to provide feedback about implementing `DbDataAdapter`.</span></span>

## <a name="output-parameters"></a><span data-ttu-id="5b68e-119">출력 매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b68e-119">Output parameters</span></span>

<span data-ttu-id="5b68e-120">SQLite는 출력 매개 변수를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-120">SQLite doesn't support output parameters.</span></span>

## <a name="positional-parameters"></a><span data-ttu-id="5b68e-121">위치 매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b68e-121">Positional parameters</span></span>

<span data-ttu-id="5b68e-122">Microsoft.Data.Sqlite는 명명된 [매개 변수](parameters.md)만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-122">Microsoft.Data.Sqlite only supports named [parameters](parameters.md).</span></span> <span data-ttu-id="5b68e-123">위치 매개 변수는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-123">Positional parameters aren't supported.</span></span>

## <a name="stored-procedures"></a><span data-ttu-id="5b68e-124">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="5b68e-124">Stored procedures</span></span>

<span data-ttu-id="5b68e-125">SQLite는 저장 프로시저를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-125">SQLite doesn't support stored procedures.</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="5b68e-126">격리 수준</span><span class="sxs-lookup"><span data-stu-id="5b68e-126">Isolation levels</span></span>

<span data-ttu-id="5b68e-127">SQLite 트랜잭션에서는 `Chaos` 및 `Snapshot` 격리 수준이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b68e-127">The `Chaos` and `Snapshot` isolation levels aren't supported in SQLite transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b68e-128">참조</span><span class="sxs-lookup"><span data-stu-id="5b68e-128">See also</span></span>

* [<span data-ttu-id="5b68e-129">비동기 제한 사항</span><span class="sxs-lookup"><span data-stu-id="5b68e-129">Async limitations</span></span>](async.md)
* [<span data-ttu-id="5b68e-130">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5b68e-130">Data types</span></span>](types.md)
* [<span data-ttu-id="5b68e-131">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="5b68e-131">Transactions</span></span>](transactions.md)
