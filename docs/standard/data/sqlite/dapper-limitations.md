---
title: Dapper 제한 사항
ms.date: 12/13/2019
description: Dapper를 사용할 때 발생하는 몇 가지 제한 사항에 대해 설명합니다.
ms.openlocfilehash: 396507f25f591a9ab5c3bb07c0af6fd8d175e4ea
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901206"
---
# <a name="dapper-limitations"></a><span data-ttu-id="9c998-103">Dapper 제한 사항</span><span class="sxs-lookup"><span data-stu-id="9c998-103">Dapper limitations</span></span>

<span data-ttu-id="9c998-104">Microsoft.Data.Sqlite를 [Dapper](https://stackexchange.github.io/Dapper/)와 함께 사용할 때 알아야 할 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c998-104">There are a few limitations you should be aware of when using Microsoft.Data.Sqlite with [Dapper](https://stackexchange.github.io/Dapper/).</span></span>

## <a name="parameters"></a><span data-ttu-id="9c998-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c998-105">Parameters</span></span>

<span data-ttu-id="9c998-106">SQLite 매개 변수 이름은 대소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="9c998-106">SQLite parameter names are case-sensitive.</span></span> <span data-ttu-id="9c998-107">SQL에서 사용되는 매개 변수 이름이 익명 개체의 속성과 대/소문자가 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c998-107">Ensure that the parameter names used in SQL match the case of the anonymous object's properties.</span></span> <span data-ttu-id="9c998-108">문제 [#18861](https://github.com/dotnet/efcore/issues/18861)이 이 환경을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c998-108">Issue [#18861](https://github.com/dotnet/efcore/issues/18861) would improve this experience.</span></span>

<span data-ttu-id="9c998-109">또한 Dapper는 매개 변수가 `@` 접두사를 사용하도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="9c998-109">Dapper also expects parameters to use the `@` prefix.</span></span> <span data-ttu-id="9c998-110">다른 접두사는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c998-110">Other prefixes won't work.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a><span data-ttu-id="9c998-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9c998-111">Data types</span></span>

<span data-ttu-id="9c998-112">Dapper는 SqliteDataReader 인덱서를 사용하여 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9c998-112">Dapper reads values using the SqliteDataReader indexer.</span></span> <span data-ttu-id="9c998-113">이 인덱서의 반환 형식은 개체입니다. 즉, long, double, string 또는 byte[] 값만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9c998-113">The return type of this indexer is object, which means it will only ever return long, double, string, or byte[] values.</span></span> <span data-ttu-id="9c998-114">자세한 내용은 [데이터 형식](types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c998-114">For more information, see [Data types](types.md).</span></span> <span data-ttu-id="9c998-115">Dapper는 이러한 기본 형식과 다른 기본 형식 간의 변환을 대부분 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9c998-115">Dapper handles most conversions between these and other primitive types.</span></span> <span data-ttu-id="9c998-116">아쉽지만 `DateTimeOffset`, `Guid` 또는 `TimeSpan`은 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c998-116">Unfortunately, it doesn't handle `DateTimeOffset`, `Guid`, or `TimeSpan`.</span></span> <span data-ttu-id="9c998-117">결과에 이러한 형식을 사용하려면 형식 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c998-117">Create type handlers if you want to use these types in your results.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

<span data-ttu-id="9c998-118">형식 처리기는 쿼리 전에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c998-118">Don't forget to add the type handlers before querying.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a><span data-ttu-id="9c998-119">참조</span><span class="sxs-lookup"><span data-stu-id="9c998-119">See also</span></span>

* [<span data-ttu-id="9c998-120">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9c998-120">Data types</span></span>](types.md)
* [<span data-ttu-id="9c998-121">비동기 제한 사항</span><span class="sxs-lookup"><span data-stu-id="9c998-121">Async limitations</span></span>](async.md)
