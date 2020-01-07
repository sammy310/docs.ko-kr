---
title: 사용자 정의 함수
ms.date: 12/13/2019
description: 사용자 정의 스칼라 및 집계 함수를 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450413"
---
# <a name="user-defined-functions"></a><span data-ttu-id="29da3-103">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="29da3-103">User-defined functions</span></span>

<span data-ttu-id="29da3-104">대부분의 데이터베이스에는 함수를 정의 하는 데 사용할 수 있는 SQL의 절차적 언어가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-104">Most databases have a procedural dialect of SQL that you can use to define your own functions.</span></span> <span data-ttu-id="29da3-105">그러나 SQLite는 앱과 함께 in-process로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-105">SQLite however, runs in-process with your app.</span></span> <span data-ttu-id="29da3-106">SQL의 새로운 언어를 배울 필요 없이 앱의 프로그래밍 언어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-106">Instead of having to learn a new dialect of SQL, you can just use the programming language of your app.</span></span>

## <a name="scalar-functions"></a><span data-ttu-id="29da3-107">스칼라 함수</span><span class="sxs-lookup"><span data-stu-id="29da3-107">Scalar functions</span></span>

<span data-ttu-id="29da3-108">스칼라 함수는 쿼리의 각 행에 대해 단일 스칼라 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-108">Scalar functions return a single, scalar value for each row in a query.</span></span> <span data-ttu-id="29da3-109">새 스칼라 함수를 정의 하 고 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>를 사용 하 여 기본 제공 함수를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-109">Define new scalar functions and override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span></span>

<span data-ttu-id="29da3-110">`func` 인수에 대해 지원 되는 매개 변수 및 반환 형식 목록은 [데이터 형식](types.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29da3-110">See [Data types](types.md) for a list of supported parameter and return types for the `func` argument.</span></span>

<span data-ttu-id="29da3-111">`state` 인수를 지정 하면 해당 값이 함수의 모든 호출에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-111">Specifying the `state` argument will pass that value into every invocation of the function.</span></span> <span data-ttu-id="29da3-112">이를 사용 하 여 클로저를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-112">Use this to avoid closures.</span></span>

<span data-ttu-id="29da3-113">쿼리가 쿼리를 컴파일할 때 SQLite에서 추가 최적화를 사용할 수 있도록 함수가 결정적 일 경우 `isDeterministic`를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-113">Specify `isDeterministic` if your function is deterministic to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="29da3-114">다음 예제에서는 스칼라 함수를 추가 하 여 실린더의 반지름을 계산 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-114">The following example shows how to add a scalar function to calculate the radius of a cylinder.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a><span data-ttu-id="29da3-115">연산자</span><span class="sxs-lookup"><span data-stu-id="29da3-115">Operators</span></span>

<span data-ttu-id="29da3-116">다음 SQLite 연산자는 해당 스칼라 함수에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-116">The following SQLite operators are implemented by corresponding scalar functions.</span></span> <span data-ttu-id="29da3-117">앱에서 이러한 스칼라 함수를 정의 하면 이러한 연산자의 동작이 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-117">Defining these scalar functions in your app will override the behavior of these operators.</span></span>

| <span data-ttu-id="29da3-118">연산자</span><span class="sxs-lookup"><span data-stu-id="29da3-118">Operator</span></span>          | <span data-ttu-id="29da3-119">기능</span><span class="sxs-lookup"><span data-stu-id="29da3-119">Function</span></span>      |
| ----------------- | ------------- |
| <span data-ttu-id="29da3-120">X GLOB Y</span><span class="sxs-lookup"><span data-stu-id="29da3-120">X GLOB Y</span></span>          | <span data-ttu-id="29da3-121">glob (Y, X)</span><span class="sxs-lookup"><span data-stu-id="29da3-121">glob(Y, X)</span></span>    |
| <span data-ttu-id="29da3-122">Y와 같은 X</span><span class="sxs-lookup"><span data-stu-id="29da3-122">X LIKE Y</span></span>          | <span data-ttu-id="29da3-123">like (Y, X)</span><span class="sxs-lookup"><span data-stu-id="29da3-123">like(Y, X)</span></span>    |
| <span data-ttu-id="29da3-124">X와 같은 Y 이스케이프 Z</span><span class="sxs-lookup"><span data-stu-id="29da3-124">X LIKE Y ESCAPE Z</span></span> | <span data-ttu-id="29da3-125">like (Y, X, Z)</span><span class="sxs-lookup"><span data-stu-id="29da3-125">like(Y, X, Z)</span></span> |
| <span data-ttu-id="29da3-126">X 일치 Y</span><span class="sxs-lookup"><span data-stu-id="29da3-126">X MATCH Y</span></span>         | <span data-ttu-id="29da3-127">match (Y, X)</span><span class="sxs-lookup"><span data-stu-id="29da3-127">match(Y, X)</span></span>   |
| <span data-ttu-id="29da3-128">X REGEXP Y</span><span class="sxs-lookup"><span data-stu-id="29da3-128">X REGEXP Y</span></span>        | <span data-ttu-id="29da3-129">regexp (Y, X)</span><span class="sxs-lookup"><span data-stu-id="29da3-129">regexp(Y, X)</span></span>  |

<span data-ttu-id="29da3-130">다음 예제에서는 해당 하는 연산자를 사용 하도록 regexp 함수를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-130">The following example shows how to define the regexp function to enable its corresponding operator.</span></span> <span data-ttu-id="29da3-131">SQLite는 regexp 함수의 기본 구현을 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-131">SQLite doesn't include a default implementation of the regexp function.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a><span data-ttu-id="29da3-132">집계 함수</span><span class="sxs-lookup"><span data-stu-id="29da3-132">Aggregate functions</span></span>

<span data-ttu-id="29da3-133">집계 함수는 쿼리의 모든 행에 대해 집계 된 단일 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-133">Aggregate functions return a single, aggregated value for all the rows in a query.</span></span> <span data-ttu-id="29da3-134"><xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>를 사용 하 여 집계 함수를 정의 하 고 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-134">Define and override aggregate functions using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span></span>

<span data-ttu-id="29da3-135">`seed` 인수는 컨텍스트의 초기 상태를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-135">The `seed` argument specifies the initial state of the context.</span></span> <span data-ttu-id="29da3-136">이를 사용 하 여 클로저를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-136">Use this to avoid closures also.</span></span>

<span data-ttu-id="29da3-137">`func` 인수는 행당 한 번 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-137">The `func` argument is invoked once per row.</span></span> <span data-ttu-id="29da3-138">컨텍스트를 사용 하 여 최종 결과를 누적 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-138">Use the context to accumulate a final result.</span></span> <span data-ttu-id="29da3-139">컨텍스트를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-139">Return the context.</span></span> <span data-ttu-id="29da3-140">이 패턴을 사용 하면 컨텍스트를 값 형식 또는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-140">This pattern allows the context to be a value type or immutable.</span></span>

<span data-ttu-id="29da3-141">`resultSelector` 지정 하지 않으면 컨텍스트의 최종 상태가 결과로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-141">If no `resultSelector` is specified, the final state of the context is used as the result.</span></span> <span data-ttu-id="29da3-142">이렇게 하면 각 행의 수를 늘리고 반환 하기만 하면 되는 sum 및 count와 같은 함수의 정의가 간단해 집니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-142">This can simplify the definition of functions like sum and count that only need to increment a number each row and return it.</span></span>

<span data-ttu-id="29da3-143">모든 행을 반복한 후 컨텍스트의 최종 결과를 계산 하려면 `resultSelector`를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-143">Specify `resultSelector` to calculate the final result from the context after iterating through all the rows.</span></span>

<span data-ttu-id="29da3-144">`resultSelector`에 대 한 `func` 인수 및 반환 형식에 대해 지원 되는 매개 변수 형식 목록은 [데이터 형식](types.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29da3-144">See [Data types](types.md) for a list of supported parameter types for the `func` argument and return types for `resultSelector`.</span></span>

<span data-ttu-id="29da3-145">함수가 결정적 이면 쿼리를 컴파일할 때 SQLite에서 추가 최적화를 사용할 수 있도록 `isDeterministic`를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-145">If your function is deterministic, specify `isDeterministic` to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="29da3-146">다음 예에서는 집계 함수를 정의 하 여 열의 표준 편차를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-146">The following example defines an aggregate function to calculate the standard deviation of a column.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a><span data-ttu-id="29da3-147">오류</span><span class="sxs-lookup"><span data-stu-id="29da3-147">Errors</span></span>

<span data-ttu-id="29da3-148">사용자 정의 함수에서 예외를 throw 하는 경우 메시지는 SQLite로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-148">If a user-defined function throws an exception, the message is returned to SQLite.</span></span> <span data-ttu-id="29da3-149">그러면 SQLite에서 오류 및 SqliteException이 발생 합니다. Sqlite에서이를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-149">SQLite will then raise an error and Microsoft.Data.Sqlite will throw a SqliteException.</span></span> <span data-ttu-id="29da3-150">자세한 내용은 [데이터베이스 오류](database-errors.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29da3-150">For more information, see [Database errors](database-errors.md).</span></span>

<span data-ttu-id="29da3-151">기본적으로 SQLite 오류 코드는 SQLITE_ERROR (또는 1)입니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-151">By default, the error SQLite error code will be SQLITE_ERROR (or 1).</span></span> <span data-ttu-id="29da3-152">그러나 지정 된 <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode>를 사용 하 여 함수에서 <xref:Microsoft.Data.Sqlite.SqliteException>를 throw 하 여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-152">You can, however, change it by throwing a <xref:Microsoft.Data.Sqlite.SqliteException> in your function with the desired <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> specified.</span></span>

## <a name="debugging"></a><span data-ttu-id="29da3-153">디버깅</span><span class="sxs-lookup"><span data-stu-id="29da3-153">Debugging</span></span>

<span data-ttu-id="29da3-154">SQLite는 구현을 직접 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-154">SQLite calls your implementation directly.</span></span> <span data-ttu-id="29da3-155">이렇게 하면 SQLite가 쿼리를 평가 하는 동안 트리거되는 중단점을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-155">This lets you add breakpoints that trigger while SQLite is evaluating queries.</span></span> <span data-ttu-id="29da3-156">사용자 정의 함수를 만드는 데 도움이 되는 전체 .NET 디버깅 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29da3-156">The full .NET debugging experience is available to help you create your user-defined functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="29da3-157">참조</span><span class="sxs-lookup"><span data-stu-id="29da3-157">See also</span></span>

* [<span data-ttu-id="29da3-158">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="29da3-158">Data types</span></span>](types.md)
* [<span data-ttu-id="29da3-159">SQLite 핵심 함수</span><span class="sxs-lookup"><span data-stu-id="29da3-159">SQLite Core functions</span></span>](https://www.sqlite.org/lang_corefunc.html)
* [<span data-ttu-id="29da3-160">SQLite 집계 함수</span><span class="sxs-lookup"><span data-stu-id="29da3-160">SQLite Aggregate Functions</span></span>](https://www.sqlite.org/lang_aggfunc.html)
