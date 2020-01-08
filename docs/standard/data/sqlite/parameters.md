---
title: 매개 변수
ms.date: 12/13/2019
description: SQL 매개 변수를 사용 하는 방법을 알아봅니다.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450425"
---
# <a name="parameters"></a><span data-ttu-id="6ab59-103">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ab59-103">Parameters</span></span>

<span data-ttu-id="6ab59-104">매개 변수는 SQL 삽입 공격 으로부터 보호 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab59-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="6ab59-105">사용자 입력을 SQL 문과 연결 하는 대신 매개 변수를 사용 하 여 입력이 리터럴 값 으로만 처리 되 고 실행 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab59-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="6ab59-106">SQLite에서 매개 변수는 일반적으로 SQL 문에서 리터럴이 허용 되는 모든 위치에서 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab59-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="6ab59-107">매개 변수에는 `:`, `@`또는 `$`접두사가 추가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab59-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="6ab59-108">.NET 값이 SQLite 값에 매핑되는 방법에 대 한 자세한 내용은 [데이터 형식](types.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ab59-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="6ab59-109">잘림</span><span class="sxs-lookup"><span data-stu-id="6ab59-109">Truncation</span></span>

<span data-ttu-id="6ab59-110"><xref:Microsoft.Data.Sqlite.SqliteParameter.Size> 속성을 사용 하 여 텍스트 및 BLOB 값을 자릅니다.</span><span class="sxs-lookup"><span data-stu-id="6ab59-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="6ab59-111">대체 형식</span><span class="sxs-lookup"><span data-stu-id="6ab59-111">Alternative types</span></span>

<span data-ttu-id="6ab59-112">경우에 따라 대체 SQLite 유형을 사용 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab59-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="6ab59-113"><xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> 속성을 설정 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab59-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="6ab59-114">다음 대체 형식 매핑을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab59-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="6ab59-115">기본 매핑에 대해서는 [데이터 형식](types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ab59-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="6ab59-116">값</span><span class="sxs-lookup"><span data-stu-id="6ab59-116">Value</span></span>          | <span data-ttu-id="6ab59-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="6ab59-117">SqliteType</span></span> | <span data-ttu-id="6ab59-118">주의</span><span class="sxs-lookup"><span data-stu-id="6ab59-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="6ab59-119">Char</span><span class="sxs-lookup"><span data-stu-id="6ab59-119">Char</span></span>           | <span data-ttu-id="6ab59-120">정수</span><span class="sxs-lookup"><span data-stu-id="6ab59-120">Integer</span></span>    | <span data-ttu-id="6ab59-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="6ab59-121">UTF-16</span></span>           |
| <span data-ttu-id="6ab59-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="6ab59-122">DateTime</span></span>       | <span data-ttu-id="6ab59-123">Real</span><span class="sxs-lookup"><span data-stu-id="6ab59-123">Real</span></span>       | <span data-ttu-id="6ab59-124">율리우스 날짜 값</span><span class="sxs-lookup"><span data-stu-id="6ab59-124">Julian day value</span></span> |
| <span data-ttu-id="6ab59-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6ab59-125">DateTimeOffset</span></span> | <span data-ttu-id="6ab59-126">Real</span><span class="sxs-lookup"><span data-stu-id="6ab59-126">Real</span></span>       | <span data-ttu-id="6ab59-127">율리우스 날짜 값</span><span class="sxs-lookup"><span data-stu-id="6ab59-127">Julian day value</span></span> |
| <span data-ttu-id="6ab59-128">GUID</span><span class="sxs-lookup"><span data-stu-id="6ab59-128">Guid</span></span>           | <span data-ttu-id="6ab59-129">Blob</span><span class="sxs-lookup"><span data-stu-id="6ab59-129">Blob</span></span>       |                  |
| <span data-ttu-id="6ab59-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="6ab59-130">TimeSpan</span></span>       | <span data-ttu-id="6ab59-131">Real</span><span class="sxs-lookup"><span data-stu-id="6ab59-131">Real</span></span>       | <span data-ttu-id="6ab59-132">일 단위</span><span class="sxs-lookup"><span data-stu-id="6ab59-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="6ab59-133">출력 매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ab59-133">Output parameters</span></span>

<span data-ttu-id="6ab59-134">SQLite는 출력 매개 변수를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab59-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="6ab59-135">대신 쿼리 결과의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab59-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ab59-136">참조</span><span class="sxs-lookup"><span data-stu-id="6ab59-136">See also</span></span>

* [<span data-ttu-id="6ab59-137">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6ab59-137">Data types</span></span>](types.md)
