---
title: 연결 문자열
ms.date: 12/13/2019
description: 지원되는 키워드 및 연결 문자열의 값입니다.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401198"
---
# <a name="connection-strings"></a><span data-ttu-id="ad667-103">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="ad667-103">Connection strings</span></span>

<span data-ttu-id="ad667-104">연결 문자열은 데이터베이스에 연결하는 방법을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="ad667-105">Microsoft.Data.Sqlite의 연결 문자열은 표준 [ADO.NET 구문을](../../../framework/data/adonet/connection-strings.md) 키워드 및 값의 세미콜론으로 구분된 목록으로 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="ad667-106">키워드</span><span class="sxs-lookup"><span data-stu-id="ad667-106">Keywords</span></span>

<span data-ttu-id="ad667-107">다음 연결 문자열 키워드는 Microsoft.Data.Sqlite에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="ad667-108">데이터 원본</span><span class="sxs-lookup"><span data-stu-id="ad667-108">Data source</span></span>

<span data-ttu-id="ad667-109">데이터베이스 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-109">The path to the database file.</span></span> <span data-ttu-id="ad667-110">*데이터 원본(공백* 제외)과 *파일 이름은* 이 키워드의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="ad667-111">SQLite는 현재 작업 디렉터리와 관련된 경로를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="ad667-112">절대 경로를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="ad667-113">**비어**있는 경우 SQLite는 연결이 닫혀 있을 때 삭제되는 임시 온 디스크 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="ad667-114">을 `:memory:`사용 하는 경우 메모리 내 데이터베이스가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="ad667-115">자세한 내용은 [메모리 내 데이터베이스를 참조하십시오.](in-memory-databases.md)</span><span class="sxs-lookup"><span data-stu-id="ad667-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="ad667-116">`|DataDirectory|` 대체 문자열로 시작하는 경로는 상대 경로와 동일하게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="ad667-117">설정된 경우 경로는 DataDirectory 응용 프로그램 도메인 속성 값을 기준으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="ad667-118">이 키워드는 [URI 파일 이름도](https://www.sqlite.org/uri.html)지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="ad667-119">Mode</span><span class="sxs-lookup"><span data-stu-id="ad667-119">Mode</span></span>

<span data-ttu-id="ad667-120">연결 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-120">The connection mode.</span></span>

| <span data-ttu-id="ad667-121">값</span><span class="sxs-lookup"><span data-stu-id="ad667-121">Value</span></span>           | <span data-ttu-id="ad667-122">Description</span><span class="sxs-lookup"><span data-stu-id="ad667-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ad667-123">읽기 쓰기 만들기</span><span class="sxs-lookup"><span data-stu-id="ad667-123">ReadWriteCreate</span></span> | <span data-ttu-id="ad667-124">읽기 및 쓰기를 위해 데이터베이스를 열고 존재하지 않는 경우 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="ad667-125">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-125">This is the default.</span></span> |
| <span data-ttu-id="ad667-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ad667-126">ReadWrite</span></span>       | <span data-ttu-id="ad667-127">읽기 및 쓰기를 위한 데이터베이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="ad667-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="ad667-128">ReadOnly</span></span>        | <span data-ttu-id="ad667-129">읽기 전용 모드에서 데이터베이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="ad667-130">메모리</span><span class="sxs-lookup"><span data-stu-id="ad667-130">Memory</span></span>          | <span data-ttu-id="ad667-131">메모리 내 데이터베이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="ad667-132">캐시</span><span class="sxs-lookup"><span data-stu-id="ad667-132">Cache</span></span>

<span data-ttu-id="ad667-133">연결에서 사용하는 캐싱 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="ad667-134">값</span><span class="sxs-lookup"><span data-stu-id="ad667-134">Value</span></span>   | <span data-ttu-id="ad667-135">Description</span><span class="sxs-lookup"><span data-stu-id="ad667-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ad667-136">기본값</span><span class="sxs-lookup"><span data-stu-id="ad667-136">Default</span></span> | <span data-ttu-id="ad667-137">기본 SQLite 라이브러리의 기본 모드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="ad667-138">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-138">This is the default.</span></span>                   |
| <span data-ttu-id="ad667-139">프라이빗</span><span class="sxs-lookup"><span data-stu-id="ad667-139">Private</span></span> | <span data-ttu-id="ad667-140">각 연결은 개인 캐시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="ad667-141">공유됨</span><span class="sxs-lookup"><span data-stu-id="ad667-141">Shared</span></span>  | <span data-ttu-id="ad667-142">연결은 캐시를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-142">Connections share a cache.</span></span> <span data-ttu-id="ad667-143">이 모드는 트랜잭션 및 테이블 잠금 의 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="ad667-144">암호</span><span class="sxs-lookup"><span data-stu-id="ad667-144">Password</span></span>

<span data-ttu-id="ad667-145">암호화 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-145">The encryption key.</span></span> <span data-ttu-id="ad667-146">지정하면 `PRAGMA key` 연결을 연 직후에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="ad667-147">기본 SQLite 라이브러리에서 암호화를 지원하지 않는 경우 암호는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="ad667-148">외래 키</span><span class="sxs-lookup"><span data-stu-id="ad667-148">Foreign Keys</span></span>

<span data-ttu-id="ad667-149">외래 키 제약 조건을 사용할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="ad667-150">값</span><span class="sxs-lookup"><span data-stu-id="ad667-150">Value</span></span>   | <span data-ttu-id="ad667-151">Description</span><span class="sxs-lookup"><span data-stu-id="ad667-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="ad667-152">True</span><span class="sxs-lookup"><span data-stu-id="ad667-152">True</span></span>    | <span data-ttu-id="ad667-153">연결을 `PRAGMA foreign_keys = 1` 연 직후에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="ad667-154">False</span><span class="sxs-lookup"><span data-stu-id="ad667-154">False</span></span>   | <span data-ttu-id="ad667-155">연결을 `PRAGMA foreign_keys = 0` 연 직후에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="ad667-156">(empty)</span><span class="sxs-lookup"><span data-stu-id="ad667-156">(empty)</span></span> | <span data-ttu-id="ad667-157">을 보내지 `PRAGMA foreign_keys`않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="ad667-158">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-158">This is the default.</span></span> |

<span data-ttu-id="ad667-159">e_sqlite3 처럼 네이티브 SQLite 라이브러리를 컴파일하는 데 SQLITE_DEFAULT_FOREIGN_KEYS 사용되는 경우 외래 키를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="ad667-160">재귀 트리거</span><span class="sxs-lookup"><span data-stu-id="ad667-160">Recursive triggers</span></span>

<span data-ttu-id="ad667-161">재귀 트리거를 사용할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="ad667-162">값</span><span class="sxs-lookup"><span data-stu-id="ad667-162">Value</span></span> | <span data-ttu-id="ad667-163">Description</span><span class="sxs-lookup"><span data-stu-id="ad667-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="ad667-164">True</span><span class="sxs-lookup"><span data-stu-id="ad667-164">True</span></span>  | <span data-ttu-id="ad667-165">연결을 `PRAGMA recursive_triggers` 연 직후에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="ad667-166">False</span><span class="sxs-lookup"><span data-stu-id="ad667-166">False</span></span> | <span data-ttu-id="ad667-167">을 보내지 `PRAGMA recursive_triggers`않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="ad667-168">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="ad667-169">연결 문자열 빌더</span><span class="sxs-lookup"><span data-stu-id="ad667-169">Connection string builder</span></span>

<span data-ttu-id="ad667-170">연결 문자열을 만드는 강력한 형식의 방법으로 사용할 <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="ad667-171">또한 연결 문자열 주입 공격을 방지하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="ad667-172">예</span><span class="sxs-lookup"><span data-stu-id="ad667-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="ad667-173">Basic</span><span class="sxs-lookup"><span data-stu-id="ad667-173">Basic</span></span>

<span data-ttu-id="ad667-174">향상된 동시성을 위해 공유 캐시가 있는 기본 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="ad667-175">암호화</span><span class="sxs-lookup"><span data-stu-id="ad667-175">Encrypted</span></span>

<span data-ttu-id="ad667-176">암호화된 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="ad667-177">읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ad667-177">Read-only</span></span>

<span data-ttu-id="ad667-178">앱에서 수정할 수 없는 읽기 전용 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="ad667-179">메모리 내</span><span class="sxs-lookup"><span data-stu-id="ad667-179">In-memory</span></span>

<span data-ttu-id="ad667-180">전용 인메모리 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ad667-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="ad667-181">공유 가능한 인메모리</span><span class="sxs-lookup"><span data-stu-id="ad667-181">Sharable in-memory</span></span>

<span data-ttu-id="ad667-182">이름 공유 가능으로 식별되는 공유 가능한 메모리 내 *데이터베이스입니다.*</span><span class="sxs-lookup"><span data-stu-id="ad667-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="ad667-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad667-183">See also</span></span>

* [<span data-ttu-id="ad667-184">ADO.NET의 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="ad667-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="ad667-185">인메모리 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="ad667-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="ad667-186">트랜잭션을</span><span class="sxs-lookup"><span data-stu-id="ad667-186">Transactions</span></span>](transactions.md)
