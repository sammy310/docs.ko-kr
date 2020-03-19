---
title: 매개 변수
ms.date: 12/13/2019
description: SQL 매개 변수를 사용하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401204"
---
# <a name="parameters"></a><span data-ttu-id="fb3dc-103">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb3dc-103">Parameters</span></span>

<span data-ttu-id="fb3dc-104">매개 변수는 SQL 주입 공격으로부터 보호하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="fb3dc-105">사용자 입력을 SQL 문과 연결하는 대신 매개 변수를 사용하여 입력이 리터럴 값으로만 처리되고 실행되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="fb3dc-106">SQLite에서 매개 변수는 일반적으로 SQL 문에서 리터럴이 허용되는 모든 곳에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="fb3dc-107">매개 변수는 에 `:` `@`의한 것 `$`또는 으로 접두사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="fb3dc-108">.NET 값이 SQLite 값에 매핑되는 방법에 대한 자세한 내용은 [데이터 유형을](types.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="fb3dc-109">잘림</span><span class="sxs-lookup"><span data-stu-id="fb3dc-109">Truncation</span></span>

<span data-ttu-id="fb3dc-110">속성을 <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> 사용하여 TEXT 및 BLOB 값을 자를 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="fb3dc-111">대체 형식</span><span class="sxs-lookup"><span data-stu-id="fb3dc-111">Alternative types</span></span>

<span data-ttu-id="fb3dc-112">경우에 따라 다른 SQLite 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="fb3dc-113"><xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> 속성을 설정 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="fb3dc-114">다음 대체 형식 매핑을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="fb3dc-115">기본 매핑에 대 한 데이터 형식을 참조 [합니다.](types.md)</span><span class="sxs-lookup"><span data-stu-id="fb3dc-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="fb3dc-116">값</span><span class="sxs-lookup"><span data-stu-id="fb3dc-116">Value</span></span>          | <span data-ttu-id="fb3dc-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="fb3dc-117">SqliteType</span></span> | <span data-ttu-id="fb3dc-118">설명</span><span class="sxs-lookup"><span data-stu-id="fb3dc-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="fb3dc-119">Char</span><span class="sxs-lookup"><span data-stu-id="fb3dc-119">Char</span></span>           | <span data-ttu-id="fb3dc-120">정수</span><span class="sxs-lookup"><span data-stu-id="fb3dc-120">Integer</span></span>    | <span data-ttu-id="fb3dc-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="fb3dc-121">UTF-16</span></span>           |
| <span data-ttu-id="fb3dc-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="fb3dc-122">DateTime</span></span>       | <span data-ttu-id="fb3dc-123">Real</span><span class="sxs-lookup"><span data-stu-id="fb3dc-123">Real</span></span>       | <span data-ttu-id="fb3dc-124">줄리안 일 값</span><span class="sxs-lookup"><span data-stu-id="fb3dc-124">Julian day value</span></span> |
| <span data-ttu-id="fb3dc-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fb3dc-125">DateTimeOffset</span></span> | <span data-ttu-id="fb3dc-126">Real</span><span class="sxs-lookup"><span data-stu-id="fb3dc-126">Real</span></span>       | <span data-ttu-id="fb3dc-127">줄리안 일 값</span><span class="sxs-lookup"><span data-stu-id="fb3dc-127">Julian day value</span></span> |
| <span data-ttu-id="fb3dc-128">Guid</span><span class="sxs-lookup"><span data-stu-id="fb3dc-128">Guid</span></span>           | <span data-ttu-id="fb3dc-129">Blob</span><span class="sxs-lookup"><span data-stu-id="fb3dc-129">Blob</span></span>       |                  |
| <span data-ttu-id="fb3dc-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="fb3dc-130">TimeSpan</span></span>       | <span data-ttu-id="fb3dc-131">Real</span><span class="sxs-lookup"><span data-stu-id="fb3dc-131">Real</span></span>       | <span data-ttu-id="fb3dc-132">며칠 만에</span><span class="sxs-lookup"><span data-stu-id="fb3dc-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="fb3dc-133">출력 매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb3dc-133">Output parameters</span></span>

<span data-ttu-id="fb3dc-134">SQLite는 출력 매개 변수를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="fb3dc-135">대신 쿼리 결과에 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3dc-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb3dc-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb3dc-136">See also</span></span>

* [<span data-ttu-id="fb3dc-137">데이터 유형</span><span class="sxs-lookup"><span data-stu-id="fb3dc-137">Data types</span></span>](types.md)
