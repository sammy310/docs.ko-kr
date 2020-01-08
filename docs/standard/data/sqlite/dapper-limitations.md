---
title: Dapper 제한 사항
ms.date: 12/13/2019
description: Dapper를 사용할 때 발생 하는 몇 가지 제한 사항에 대해 설명 합니다.
ms.openlocfilehash: 90c7fb24f068d663081390bdba9b1b222b4be56e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450497"
---
# <a name="dapper-limitations"></a><span data-ttu-id="29169-103">Dapper 제한 사항</span><span class="sxs-lookup"><span data-stu-id="29169-103">Dapper limitations</span></span>

<span data-ttu-id="29169-104">[Dapper](https://stackexchange.github.io/Dapper/)와 함께 Microsoft. Sqlite를 사용할 때 알아야 할 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29169-104">There are a few limitations you should be aware of when using Microsoft.Data.Sqlite with [Dapper](https://stackexchange.github.io/Dapper/).</span></span>

## <a name="parameters"></a><span data-ttu-id="29169-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29169-105">Parameters</span></span>

<span data-ttu-id="29169-106">SQLite 매개 변수 이름은 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="29169-106">SQLite parameter names are case-sensitive.</span></span> <span data-ttu-id="29169-107">SQL에서 사용 되는 매개 변수 이름이 익명 개체의 속성에 대 한 대/소문자와 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="29169-107">Ensure that the parameter names used in SQL match the case of the anonymous object's properties.</span></span> <span data-ttu-id="29169-108">[#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861) 문제는이 환경을 개선 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29169-108">Issue [#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861) would improve this experience.</span></span>

<span data-ttu-id="29169-109">또한 Dapper는 `@` 접두사를 사용 하는 매개 변수를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="29169-109">Dapper also expects parameters to use the `@` prefix.</span></span> <span data-ttu-id="29169-110">다른 접두사는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29169-110">Other prefixes won't work.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a><span data-ttu-id="29169-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="29169-111">Data types</span></span>

<span data-ttu-id="29169-112">Dapper는 SqliteDataReader 인덱서를 사용 하 여 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="29169-112">Dapper reads values using the SqliteDataReader indexer.</span></span> <span data-ttu-id="29169-113">이 인덱서의 반환 형식은 object 이며 long, double, string 또는 byte [] 값만 반환 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="29169-113">The return type of this indexer is object, which means it will only ever return long, double, string, or byte[] values.</span></span> <span data-ttu-id="29169-114">자세한 내용은 [데이터 형식](types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29169-114">For more information, see [Data types](types.md).</span></span> <span data-ttu-id="29169-115">Dapper는 이러한 기본 형식 및 다른 기본 형식 간의 변환을 대부분 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="29169-115">Dapper handles most conversions between these and other primitive types.</span></span> <span data-ttu-id="29169-116">아쉽게도 `DateTimeOffset`, `Guid`또는 `TimeSpan`를 처리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29169-116">Unfortunately, it doesn't handle `DateTimeOffset`, `Guid`, or `TimeSpan`.</span></span> <span data-ttu-id="29169-117">결과에 이러한 형식을 사용 하려면 형식 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="29169-117">Create type handlers if you want to use these types in your results.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

<span data-ttu-id="29169-118">쿼리 하기 전에 형식 처리기를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29169-118">Don't forget to add the type handlers before querying.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a><span data-ttu-id="29169-119">참조</span><span class="sxs-lookup"><span data-stu-id="29169-119">See also</span></span>

* [<span data-ttu-id="29169-120">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="29169-120">Data types</span></span>](types.md)
* [<span data-ttu-id="29169-121">비동기 제한 사항</span><span class="sxs-lookup"><span data-stu-id="29169-121">Async limitations</span></span>](async.md)
