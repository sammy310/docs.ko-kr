---
title: 사용자 정의 함수
ms.date: 12/13/2019
description: 사용자 정의 스칼라 및 집계 함수를 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450413"
---
# <a name="user-defined-functions"></a><span data-ttu-id="033d5-103">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="033d5-103">User-defined functions</span></span>

<span data-ttu-id="033d5-104">대부분의 데이터베이스에는 함수를 정의하는 데 사용할 수 있는 SQL의 절차적 언어가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-104">Most databases have a procedural dialect of SQL that you can use to define your own functions.</span></span> <span data-ttu-id="033d5-105">그러나 SQLite는 앱과 함께 In Process로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-105">SQLite however, runs in-process with your app.</span></span> <span data-ttu-id="033d5-106">SQL의 새로운 언어를 배울 필요 없이 앱의 프로그래밍 언어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-106">Instead of having to learn a new dialect of SQL, you can just use the programming language of your app.</span></span>

## <a name="scalar-functions"></a><span data-ttu-id="033d5-107">스칼라 함수</span><span class="sxs-lookup"><span data-stu-id="033d5-107">Scalar functions</span></span>

<span data-ttu-id="033d5-108">스칼라 함수는 쿼리의 각 행에 대해 단일 스칼라 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-108">Scalar functions return a single, scalar value for each row in a query.</span></span> <span data-ttu-id="033d5-109">새 스칼라 함수를 정의하고 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>을 사용하여 기본 제공 함수를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-109">Define new scalar functions and override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span></span>

<span data-ttu-id="033d5-110">지원되는 매개 변수 목록과 `func` 인수에 대한 반환 형식에 대해서는 [데이터 형식](types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="033d5-110">See [Data types](types.md) for a list of supported parameter and return types for the `func` argument.</span></span>

<span data-ttu-id="033d5-111">`state` 인수를 지정하면 해당 값이 함수의 모든 호출에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-111">Specifying the `state` argument will pass that value into every invocation of the function.</span></span> <span data-ttu-id="033d5-112">이를 사용하여 클로저를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-112">Use this to avoid closures.</span></span>

<span data-ttu-id="033d5-113">쿼리를 컴파일할 때 SQLite에서 추가 최적화를 사용할 수 있도록 함수가 결정적일 경우 `isDeterministic`을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-113">Specify `isDeterministic` if your function is deterministic to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="033d5-114">다음 예제에서는 스칼라 함수를 추가하여 실린더의 반지름을 계산하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-114">The following example shows how to add a scalar function to calculate the radius of a cylinder.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a><span data-ttu-id="033d5-115">연산자</span><span class="sxs-lookup"><span data-stu-id="033d5-115">Operators</span></span>

<span data-ttu-id="033d5-116">다음 SQLite 연산자는 해당 스칼라 함수에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-116">The following SQLite operators are implemented by corresponding scalar functions.</span></span> <span data-ttu-id="033d5-117">앱에서 이러한 스칼라 함수를 정의하면 이러한 연산자의 동작이 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-117">Defining these scalar functions in your app will override the behavior of these operators.</span></span>

| <span data-ttu-id="033d5-118">연산자</span><span class="sxs-lookup"><span data-stu-id="033d5-118">Operator</span></span>          | <span data-ttu-id="033d5-119">기능</span><span class="sxs-lookup"><span data-stu-id="033d5-119">Function</span></span>      |
| ----------------- | ------------- |
| <span data-ttu-id="033d5-120">X GLOB Y</span><span class="sxs-lookup"><span data-stu-id="033d5-120">X GLOB Y</span></span>          | <span data-ttu-id="033d5-121">glob(Y, X)</span><span class="sxs-lookup"><span data-stu-id="033d5-121">glob(Y, X)</span></span>    |
| <span data-ttu-id="033d5-122">X LIKE Y</span><span class="sxs-lookup"><span data-stu-id="033d5-122">X LIKE Y</span></span>          | <span data-ttu-id="033d5-123">like(Y, X)</span><span class="sxs-lookup"><span data-stu-id="033d5-123">like(Y, X)</span></span>    |
| <span data-ttu-id="033d5-124">X LIKE Y ESCAPE Z</span><span class="sxs-lookup"><span data-stu-id="033d5-124">X LIKE Y ESCAPE Z</span></span> | <span data-ttu-id="033d5-125">like(Y, X, Z)</span><span class="sxs-lookup"><span data-stu-id="033d5-125">like(Y, X, Z)</span></span> |
| <span data-ttu-id="033d5-126">X MATCH Y</span><span class="sxs-lookup"><span data-stu-id="033d5-126">X MATCH Y</span></span>         | <span data-ttu-id="033d5-127">match(Y, X)</span><span class="sxs-lookup"><span data-stu-id="033d5-127">match(Y, X)</span></span>   |
| <span data-ttu-id="033d5-128">X REGEXP Y</span><span class="sxs-lookup"><span data-stu-id="033d5-128">X REGEXP Y</span></span>        | <span data-ttu-id="033d5-129">regexp(Y, X)</span><span class="sxs-lookup"><span data-stu-id="033d5-129">regexp(Y, X)</span></span>  |

<span data-ttu-id="033d5-130">다음 예제에서는 해당하는 연산자를 사용하도록 regexp 함수를 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-130">The following example shows how to define the regexp function to enable its corresponding operator.</span></span> <span data-ttu-id="033d5-131">SQLite는 regexp 함수의 기본 구현을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-131">SQLite doesn't include a default implementation of the regexp function.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a><span data-ttu-id="033d5-132">집계 함수</span><span class="sxs-lookup"><span data-stu-id="033d5-132">Aggregate functions</span></span>

<span data-ttu-id="033d5-133">집계 함수는 쿼리의 모든 행에 대해 집계된 단일 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-133">Aggregate functions return a single, aggregated value for all the rows in a query.</span></span> <span data-ttu-id="033d5-134"><xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>를 사용하여 집계 함수를 정의하고 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-134">Define and override aggregate functions using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span></span>

<span data-ttu-id="033d5-135">`seed` 인수는 컨텍스트의 초기 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-135">The `seed` argument specifies the initial state of the context.</span></span> <span data-ttu-id="033d5-136">또한 이를 사용하여 클로저를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-136">Use this to avoid closures also.</span></span>

<span data-ttu-id="033d5-137">`func` 인수는 행당 한 번 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-137">The `func` argument is invoked once per row.</span></span> <span data-ttu-id="033d5-138">컨텍스트를 사용하여 최종 결과를 누적합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-138">Use the context to accumulate a final result.</span></span> <span data-ttu-id="033d5-139">컨텍스트를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-139">Return the context.</span></span> <span data-ttu-id="033d5-140">이 패턴을 사용하면 컨텍스트를 값 형식 또는 변경 불가능으로 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-140">This pattern allows the context to be a value type or immutable.</span></span>

<span data-ttu-id="033d5-141">`resultSelector`를 지정하지 않으면 컨텍스트의 최종 상태가 결과로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-141">If no `resultSelector` is specified, the final state of the context is used as the result.</span></span> <span data-ttu-id="033d5-142">이렇게 하면 각 행의 수를 늘리고 반환하기만 하면 되는 sum 및 count와 같은 함수의 정의를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-142">This can simplify the definition of functions like sum and count that only need to increment a number each row and return it.</span></span>

<span data-ttu-id="033d5-143">모든 행을 반복한 후 컨텍스트의 최종 결과를 계산하려면 `resultSelector`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-143">Specify `resultSelector` to calculate the final result from the context after iterating through all the rows.</span></span>

<span data-ttu-id="033d5-144">`func` 인수에 대한 지원되는 매개 변수 목록과 `resultSelector`에 대한 반환 형식에 대해서는 [데이터 형식](types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="033d5-144">See [Data types](types.md) for a list of supported parameter types for the `func` argument and return types for `resultSelector`.</span></span>

<span data-ttu-id="033d5-145">함수가 결정적인 경우 쿼리를 컴파일할 때 SQLite에서 추가 최적화를 사용할 수 있도록 `isDeterministic`을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-145">If your function is deterministic, specify `isDeterministic` to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="033d5-146">다음 예제에서는 집계 함수를 정의하여 열의 표준 편차를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-146">The following example defines an aggregate function to calculate the standard deviation of a column.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a><span data-ttu-id="033d5-147">오류</span><span class="sxs-lookup"><span data-stu-id="033d5-147">Errors</span></span>

<span data-ttu-id="033d5-148">사용자 정의 함수에서 예외를 throw하는 경우 메시지는 SQLite로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-148">If a user-defined function throws an exception, the message is returned to SQLite.</span></span> <span data-ttu-id="033d5-149">그러면 SQLite에서 오류가 발생시키고 Microsoft.Data.Sqlite에서 SqliteException을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-149">SQLite will then raise an error and Microsoft.Data.Sqlite will throw a SqliteException.</span></span> <span data-ttu-id="033d5-150">자세한 내용은 [데이터베이스 오류](database-errors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="033d5-150">For more information, see [Database errors](database-errors.md).</span></span>

<span data-ttu-id="033d5-151">기본적으로 오류 SQLite 오류 코드는 SQLITE_ERROR(또는 1)입니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-151">By default, the error SQLite error code will be SQLITE_ERROR (or 1).</span></span> <span data-ttu-id="033d5-152">그러나 지정된 <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode>를 사용하여 함수에서 <xref:Microsoft.Data.Sqlite.SqliteException>을 throw하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-152">You can, however, change it by throwing a <xref:Microsoft.Data.Sqlite.SqliteException> in your function with the desired <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> specified.</span></span>

## <a name="debugging"></a><span data-ttu-id="033d5-153">디버깅</span><span class="sxs-lookup"><span data-stu-id="033d5-153">Debugging</span></span>

<span data-ttu-id="033d5-154">SQLite는 구현을 직접 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-154">SQLite calls your implementation directly.</span></span> <span data-ttu-id="033d5-155">이렇게 하면 SQLite가 쿼리를 평가하는 동안 트리거되는 중단점을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-155">This lets you add breakpoints that trigger while SQLite is evaluating queries.</span></span> <span data-ttu-id="033d5-156">사용자 정의 함수를 만드는 데 도움이 되는 전체 .NET 디버깅 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033d5-156">The full .NET debugging experience is available to help you create your user-defined functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="033d5-157">참조</span><span class="sxs-lookup"><span data-stu-id="033d5-157">See also</span></span>

* [<span data-ttu-id="033d5-158">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="033d5-158">Data types</span></span>](types.md)
* [<span data-ttu-id="033d5-159">SQLite 핵심 함수</span><span class="sxs-lookup"><span data-stu-id="033d5-159">SQLite Core functions</span></span>](https://www.sqlite.org/lang_corefunc.html)
* [<span data-ttu-id="033d5-160">SQLite 집계 함수</span><span class="sxs-lookup"><span data-stu-id="033d5-160">SQLite Aggregate Functions</span></span>](https://www.sqlite.org/lang_aggfunc.html)
