---
title: 식 일치
description: F# 일치 식이 패턴 집합을 사용 하 여 식의 비교를 기반으로 하는 분기 제어를 제공 하는 방법에 대해 알아봅니다.
ms.date: 04/19/2018
ms.openlocfilehash: 222cb0604300039d86ed0c80293651631d212eb6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627613"
---
# <a name="match-expressions"></a><span data-ttu-id="b068a-103">식 일치</span><span class="sxs-lookup"><span data-stu-id="b068a-103">Match expressions</span></span>

<span data-ttu-id="b068a-104">`match` 식은 패턴 집합과 식의 비교를 기반으로 하는 분기 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="b068a-105">구문</span><span class="sxs-lookup"><span data-stu-id="b068a-105">Syntax</span></span>

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a><span data-ttu-id="b068a-106">설명</span><span class="sxs-lookup"><span data-stu-id="b068a-106">Remarks</span></span>

<span data-ttu-id="b068a-107">패턴 일치 식을 사용 하면 패턴 집합과 테스트 식의 비교를 기반으로 복잡 한 분기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="b068a-108">식에서 *테스트 식은* 각 패턴과 비교 되며, 일치 하는 항목이 발견 되 면 해당 *결과 식이* 계산 되 고 결과 값이 match 식의 값으로 반환 됩니다. `match`</span><span class="sxs-lookup"><span data-stu-id="b068a-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="b068a-109">이전 구문에 표시 된 패턴 일치 함수는 인수에서 패턴 일치가 즉시 수행 되는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="b068a-110">이전 구문에 표시 된 패턴 일치 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="b068a-111">람다 식에 대 한 자세한 내용은 람다 [식을 참조 하세요. `fun` 키워드](./functions/lambda-expressions-the-fun-keyword.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="b068a-112">전체 패턴 집합은 입력 변수의 가능한 모든 일치 항목을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="b068a-113">와일드 카드 패턴 (`_`)을 마지막 패턴으로 사용 하 여 이전에 일치 하지 않는 입력 값과 일치 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="b068a-114">다음 코드에서는 `match` 식을 사용 하는 몇 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="b068a-115">사용할 수 있는 가능한 모든 패턴의 참조 및 예제는 [패턴 일치](pattern-matching.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b068a-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="b068a-116">패턴에 대 한 가드</span><span class="sxs-lookup"><span data-stu-id="b068a-116">Guards on patterns</span></span>

<span data-ttu-id="b068a-117">절을 `when` 사용 하 여 변수에서 패턴과 일치 하기 위해 충족 해야 하는 추가 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="b068a-118">이러한 절을 *가드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="b068a-119">해당 가드와 연결 `when` 된 패턴과 일치 하는 항목이 없는 경우 키워드 다음에 나오는 식은 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="b068a-120">다음 예에서는 가드를 사용 하 여 변수 패턴의 숫자 범위를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="b068a-121">부울 연산자를 사용 하 여 여러 조건을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="b068a-122">리터럴 이외의 값은 패턴에서 사용할 수 없으므로 입력의 일부를 값과 비교 해야 하 `when` 는 경우 절을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="b068a-123">이 작업은 다음 코드에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="b068a-124">가드가 union 패턴을 적용 하는 경우 가드는 마지막 패턴 뿐만 아니라 **모든** 패턴에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="b068a-125">예를 들어 다음 코드에서 가드 `when a > 12` 는 및 `B a`에 모두 `A a` 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b068a-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a><span data-ttu-id="b068a-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="b068a-126">See also</span></span>

- [<span data-ttu-id="b068a-127">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="b068a-127">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b068a-128">활성 패턴</span><span class="sxs-lookup"><span data-stu-id="b068a-128">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="b068a-129">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="b068a-129">Pattern Matching</span></span>](pattern-matching.md)
