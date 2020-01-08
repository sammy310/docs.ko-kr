---
title: 연결 문자열
ms.date: 12/13/2019
description: 연결 문자열의 지원 되는 키워드 및 값입니다.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450275"
---
# <a name="connection-strings"></a><span data-ttu-id="9a732-103">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="9a732-103">Connection strings</span></span>

<span data-ttu-id="9a732-104">연결 문자열은 데이터베이스에 연결 하는 방법을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="9a732-105">Microsoft. ADO.NET의 연결 문자열은 표준 [구문을](../../../framework/data/adonet/connection-strings.md) 세미콜론으로 구분 된 키워드 및 값 목록으로 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="9a732-106">키워드</span><span class="sxs-lookup"><span data-stu-id="9a732-106">Keywords</span></span>

<span data-ttu-id="9a732-107">다음 연결 문자열 키워드는 Microsoft. Data. Sqlite와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="9a732-108">데이터 소스</span><span class="sxs-lookup"><span data-stu-id="9a732-108">Data source</span></span>

<span data-ttu-id="9a732-109">데이터베이스 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-109">The path to the database file.</span></span> <span data-ttu-id="9a732-110">*DataSource* (공백 없음) 및 *Filename* 은이 키워드의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="9a732-111">SQLite는 현재 작업 디렉터리를 기준으로 경로를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="9a732-112">절대 경로를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="9a732-113">**비어**있는 경우 SQLite는 연결이 닫힐 때 삭제 되는 임시 디스크에 임시 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="9a732-114">`:memory:`경우 메모리 내 데이터베이스가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="9a732-115">자세한 내용은 [메모리 내 데이터베이스](in-memory-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a732-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="9a732-116">`|DataDirectory|` 대체 문자열로 시작 하는 경로는 상대 경로와 동일 하 게 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="9a732-117">설정 하는 경우 DataDirectory 응용 프로그램 도메인 속성 값을 기준으로 경로가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="9a732-118">이 키워드는 [URI 파일 이름을](https://www.sqlite.org/uri.html)지원 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="9a732-119">모드</span><span class="sxs-lookup"><span data-stu-id="9a732-119">Mode</span></span>

<span data-ttu-id="9a732-120">연결 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-120">The connection mode.</span></span>

| <span data-ttu-id="9a732-121">값</span><span class="sxs-lookup"><span data-stu-id="9a732-121">Value</span></span>           | <span data-ttu-id="9a732-122">설명</span><span class="sxs-lookup"><span data-stu-id="9a732-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="9a732-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="9a732-123">ReadWriteCreate</span></span> | <span data-ttu-id="9a732-124">읽기 및 쓰기를 위해 데이터베이스를 열고 존재 하지 않는 경우 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="9a732-125">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-125">This is the default.</span></span> |
| <span data-ttu-id="9a732-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9a732-126">ReadWrite</span></span>       | <span data-ttu-id="9a732-127">읽기 및 쓰기를 위해 데이터베이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="9a732-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="9a732-128">ReadOnly</span></span>        | <span data-ttu-id="9a732-129">데이터베이스를 읽기 전용 모드로 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="9a732-130">메모리</span><span class="sxs-lookup"><span data-stu-id="9a732-130">Memory</span></span>          | <span data-ttu-id="9a732-131">메모리 내 데이터베이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="9a732-132">캐시</span><span class="sxs-lookup"><span data-stu-id="9a732-132">Cache</span></span>

<span data-ttu-id="9a732-133">연결에 사용 되는 캐싱 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="9a732-134">값</span><span class="sxs-lookup"><span data-stu-id="9a732-134">Value</span></span>   | <span data-ttu-id="9a732-135">설명</span><span class="sxs-lookup"><span data-stu-id="9a732-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="9a732-136">기본</span><span class="sxs-lookup"><span data-stu-id="9a732-136">Default</span></span> | <span data-ttu-id="9a732-137">기본 SQLite 라이브러리의 기본 모드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="9a732-138">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-138">This is the default.</span></span>                   |
| <span data-ttu-id="9a732-139">Private</span><span class="sxs-lookup"><span data-stu-id="9a732-139">Private</span></span> | <span data-ttu-id="9a732-140">각 연결은 개인 캐시를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="9a732-141">공유</span><span class="sxs-lookup"><span data-stu-id="9a732-141">Shared</span></span>  | <span data-ttu-id="9a732-142">연결은 캐시를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-142">Connections share a cache.</span></span> <span data-ttu-id="9a732-143">이 모드는 트랜잭션 및 테이블 잠금의 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="9a732-144">Password</span><span class="sxs-lookup"><span data-stu-id="9a732-144">Password</span></span>

<span data-ttu-id="9a732-145">암호화 키입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-145">The encryption key.</span></span> <span data-ttu-id="9a732-146">지정 된 경우 연결을 연 후 즉시 `PRAGMA key` 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="9a732-147">기본 SQLite 라이브러리에서 암호화를 지원 하지 않는 경우 암호는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="9a732-148">외래 키</span><span class="sxs-lookup"><span data-stu-id="9a732-148">Foreign Keys</span></span>

<span data-ttu-id="9a732-149">Foreign key 제약 조건을 사용할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="9a732-150">값</span><span class="sxs-lookup"><span data-stu-id="9a732-150">Value</span></span>   | <span data-ttu-id="9a732-151">설명</span><span class="sxs-lookup"><span data-stu-id="9a732-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="9a732-152">True</span><span class="sxs-lookup"><span data-stu-id="9a732-152">True</span></span>    | <span data-ttu-id="9a732-153">연결을 연 후 즉시 `PRAGMA foreign_keys = 1`를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="9a732-154">False</span><span class="sxs-lookup"><span data-stu-id="9a732-154">False</span></span>   | <span data-ttu-id="9a732-155">연결을 연 후 즉시 `PRAGMA foreign_keys = 0`를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="9a732-156">(비어 있음)</span><span class="sxs-lookup"><span data-stu-id="9a732-156">(empty)</span></span> | <span data-ttu-id="9a732-157">`PRAGMA foreign_keys`를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="9a732-158">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-158">This is the default.</span></span> |

<span data-ttu-id="9a732-159">E_sqlite3와 같이 네이티브 SQLite 라이브러리를 컴파일하는 데 SQLITE_DEFAULT_FOREIGN_KEYS 사용 되는 경우 외래 키를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="9a732-160">재귀 트리거</span><span class="sxs-lookup"><span data-stu-id="9a732-160">Recursive triggers</span></span>

<span data-ttu-id="9a732-161">재귀 트리거를 사용할 수 있는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="9a732-162">값</span><span class="sxs-lookup"><span data-stu-id="9a732-162">Value</span></span> | <span data-ttu-id="9a732-163">설명</span><span class="sxs-lookup"><span data-stu-id="9a732-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="9a732-164">True</span><span class="sxs-lookup"><span data-stu-id="9a732-164">True</span></span>  | <span data-ttu-id="9a732-165">연결을 연 후 즉시 `PRAGMA recursive_triggers`를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="9a732-166">False</span><span class="sxs-lookup"><span data-stu-id="9a732-166">False</span></span> | <span data-ttu-id="9a732-167">`PRAGMA recursive_triggers`를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="9a732-168">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="9a732-169">연결 문자열 작성기</span><span class="sxs-lookup"><span data-stu-id="9a732-169">Connection string builder</span></span>

<span data-ttu-id="9a732-170"><xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> 사용 하 여 연결 문자열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="9a732-171">연결 문자열 삽입 공격을 방지 하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="9a732-172">예</span><span class="sxs-lookup"><span data-stu-id="9a732-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="9a732-173">Basic</span><span class="sxs-lookup"><span data-stu-id="9a732-173">Basic</span></span>

<span data-ttu-id="9a732-174">동시성 향상을 위해 공유 캐시가 포함 된 기본 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="9a732-175">암호화됨</span><span class="sxs-lookup"><span data-stu-id="9a732-175">Encrypted</span></span>

<span data-ttu-id="9a732-176">암호화 된 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="9a732-177">읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9a732-177">Read-only</span></span>

<span data-ttu-id="9a732-178">앱에서 수정할 수 없는 읽기 전용 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="9a732-179">메모리 내</span><span class="sxs-lookup"><span data-stu-id="9a732-179">In-memory</span></span>

<span data-ttu-id="9a732-180">전용 메모리 내 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="9a732-181">공유 가능한 메모리 내</span><span class="sxs-lookup"><span data-stu-id="9a732-181">Sharable in-memory</span></span>

<span data-ttu-id="9a732-182">*공유*되는 이름으로 식별 되는 공유 가능한 메모리 내 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9a732-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="9a732-183">참조</span><span class="sxs-lookup"><span data-stu-id="9a732-183">See also</span></span>

* [<span data-ttu-id="9a732-184">ADO.NET의 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="9a732-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="9a732-185">메모리 내 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="9a732-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="9a732-186">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="9a732-186">Transactions</span></span>](transactions.md)
