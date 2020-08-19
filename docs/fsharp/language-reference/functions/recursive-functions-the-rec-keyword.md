---
title: '재귀 함수: rec 키워드'
description: "' Let ' 키워드와 함께 F # ' rec ' 키워드를 사용 하 여 재귀 함수를 정의 하는 방법을 알아봅니다."
ms.date: 08/12/2020
ms.openlocfilehash: 389357bd13cef39b1d07972c1a3167320b61612b
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558714"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="43adb-103">재귀 함수: rec 키워드</span><span class="sxs-lookup"><span data-stu-id="43adb-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="43adb-104">`rec`키워드는 키워드와 함께 사용 되어 `let` 재귀 함수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="43adb-105">구문</span><span class="sxs-lookup"><span data-stu-id="43adb-105">Syntax</span></span>

```fsharp
// Recursive function:
let rec function-nameparameter-list =
    function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
    function1-body

and function2-nameparameter-list =
    function2-body
...
```

## <a name="remarks"></a><span data-ttu-id="43adb-106">설명</span><span class="sxs-lookup"><span data-stu-id="43adb-106">Remarks</span></span>

<span data-ttu-id="43adb-107">재귀 함수-자신을 호출 하는 함수는 F # 언어에서 키워드를 사용 하 여 명시적으로 식별 됩니다 `rec` .</span><span class="sxs-lookup"><span data-stu-id="43adb-107">Recursive functions - functions that call themselves - are identified explicitly in the F# language with the `rec` keyword.</span></span> <span data-ttu-id="43adb-108">`rec`키워드는 `let` 해당 본문에서 바인딩 이름을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-108">The `rec` keyword makes the name of the `let` binding available in its body.</span></span>

<span data-ttu-id="43adb-109">다음 예에서는 수학적 정의를 사용 하 여 *n*<sup>번째</sup> 피보나치 수를 계산 하는 재귀 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-109">The following example shows a recursive function that computes the *n*<sup>th</sup> Fibonacci number using the mathematical definition.</span></span>

```fsharp
let fib n =
    match n with
    | 0 | 1 -> 1
    | n -> fib (n-1) + fib (n-2)
```

> [!NOTE]
> <span data-ttu-id="43adb-110">실제로 이전 샘플과 같은 코드는 이미 계산 된 대해 값을 unecessarily 하기 때문에 이상적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-110">In practice, code like the previous sample is not ideal because it unecessarily recomputes values that have already been computed.</span></span> <span data-ttu-id="43adb-111">이는이 문서의 뒷부분에서 설명 하는 tail recursive가 아니기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-111">This is because it is not tail recursive, which is explained further in this article.</span></span>

<span data-ttu-id="43adb-112">메서드는 정의 된 형식 내에서 암시적으로 재귀적으로 수행 됩니다. 즉, 키워드를 추가할 필요가 없습니다 `rec` .</span><span class="sxs-lookup"><span data-stu-id="43adb-112">Methods are implicitly recursive within the type they are defined in, meaning there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="43adb-113">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-113">For example:</span></span>

```fsharp
type MyClass() =
    member this.Fib(n) =
        match n with
        | 0 | 1 -> 1
        | n -> this.Fib(n-1) + this.Fib(n-2)
```

<span data-ttu-id="43adb-114">그러나 클래스 내의 바인딩이 암시적으로 재귀적이 지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-114">Let bindings within classes are not implicitly recursive, though.</span></span> <span data-ttu-id="43adb-115">모든 `let` 바인딩된 함수에는 `rec` 키워드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-115">All `let`-bound functions require the `rec` keyword.</span></span>

## <a name="tail-recursion"></a><span data-ttu-id="43adb-116">비상 재귀</span><span class="sxs-lookup"><span data-stu-id="43adb-116">Tail recursion</span></span>

<span data-ttu-id="43adb-117">일부 재귀 함수의 경우에는 더 많은 "순수" 정의를 [tail 재귀](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion)인 하나에 리팩터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-117">For some recursive functions, it is necessary to refactor a more "pure" definition to one that is [tail recursive](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion).</span></span> <span data-ttu-id="43adb-118">이렇게 하면 불필요 한 계산이 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-118">This prevents unnecessary recomputations.</span></span> <span data-ttu-id="43adb-119">예를 들어 이전 피보나치 수 생성기는 다음과 같이 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-119">For example, the previous fibonacci number generator can be rewritten like this:</span></span>

```fsharp
let fib n =
    let rec loop acc1 acc2 n =
        match n with
        | 0 -> acc1
        | 1 -> acc2
        | _ ->
            loop acc2 (acc1 + acc2) (n - 1)
    loop 0 1 n
```

<span data-ttu-id="43adb-120">이는 보다 복잡 한 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-120">This is a more complicated implementation.</span></span> <span data-ttu-id="43adb-121">피보나치 수를 생성 하는 것은 수학적으로는 좋지만 실제로 비효율적인 "naive" 알고리즘의 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-121">Generating a fibonacci number is a great example of a "naive" algorithm that's mathematically pure but inefficient in practice.</span></span> <span data-ttu-id="43adb-122">여러 가지 측면에서 F #의 효율성을 향상 하는 동시에 반복 해 서 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-122">Several aspects make it efficient in F# while still remaining recursively defined:</span></span>

* <span data-ttu-id="43adb-123">`loop`자연 스러운 F # 패턴 인 이라는 재귀적 내부 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-123">A recursive inner function named `loop`, which is an idiomatic F# pattern.</span></span>
* <span data-ttu-id="43adb-124">재귀 호출에 누적 값을 전달 하는 두 개의 누적기 매개 변수</span><span class="sxs-lookup"><span data-stu-id="43adb-124">Two accumulator parameters, which pass accumulate values to recursive calls.</span></span>
* <span data-ttu-id="43adb-125">의 값을 검사 하 여 `n` 특정 누적을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-125">A check on the value of `n` to return a specific accumulate.</span></span>

<span data-ttu-id="43adb-126">루프를 사용 하 여이 예제가 반복적으로 작성 된 경우 코드는 특정 조건이 충족 될 때까지 숫자를 누적 하는 두 개의 다른 값과 유사 하 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-126">If this example were written iteratively with a loop, the code would look similar with two different values accumulating numbers until a particular condition was met.</span></span>

<span data-ttu-id="43adb-127">이는 tail. 재귀를 수행 하는 이유는 재귀 호출이 호출 스택에 값을 저장할 필요가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-127">The reason why this is tail-recursive is because the recursive call does not need to save any values on the call stack.</span></span> <span data-ttu-id="43adb-128">계산 되는 모든 중간 값은 내부 함수에 대 한 입력을 통해 누적 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-128">All intermediate values being calculated are accumulated via inputs to the inner function.</span></span> <span data-ttu-id="43adb-129">이렇게 하면 F # 컴파일러가 루프와 같은 항목을 작성 한 것 처럼 코드를 최적화 하는 데에도 사용할 수 있습니다 `while` .</span><span class="sxs-lookup"><span data-stu-id="43adb-129">This also allows the F# compiler to optimize the code to be just as fast as if you had written something like a `while` loop.</span></span>

<span data-ttu-id="43adb-130">이전 예제에서 보여 주는 것 처럼 내부 및 외부 함수를 사용 하 여 항목을 재귀적으로 처리 하는 F # 코드를 작성 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-130">It's common to write F# code that recursively processes something with an inner and outer function, as the previous example shows.</span></span> <span data-ttu-id="43adb-131">내부 함수는 tail 재귀를 사용 하는 반면 외부 함수는 호출자에 게 더 나은 인터페이스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-131">The inner function uses tail recursion, while the outer function has a better interface for callers.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="43adb-132">상호 재귀 함수</span><span class="sxs-lookup"><span data-stu-id="43adb-132">Mutually Recursive Functions</span></span>

<span data-ttu-id="43adb-133">경우에 따라 함수는 서로 *재귀적*으로 사용 됩니다. 즉, 한 함수가 다른 함수를 호출 하는 원을 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-133">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="43adb-134">`let`키워드를 사용 하 여 함께 연결 하려면 하나의 바인딩에서 이러한 함수를 함께 정의 해야 합니다 `and` .</span><span class="sxs-lookup"><span data-stu-id="43adb-134">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="43adb-135">다음 예에서는 두 개의 상호 재귀 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-135">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="recursive-values"></a><span data-ttu-id="43adb-136">재귀 값</span><span class="sxs-lookup"><span data-stu-id="43adb-136">Recursive values</span></span>

<span data-ttu-id="43adb-137">또한 재귀적으로 바인딩되는 값을 정의할 수 있습니다 `let` .</span><span class="sxs-lookup"><span data-stu-id="43adb-137">You can also define a `let`-bound value to be recursive.</span></span> <span data-ttu-id="43adb-138">이는 로깅에 대해 수행 되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-138">This is sometimes done for logging.</span></span> <span data-ttu-id="43adb-139">F # 5와 함수를 사용 하 여 `nameof` 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43adb-139">With F# 5 and the `nameof` function, you can do this:</span></span>

```fsharp
let rec nameDoubles = nameof nameDoubles + nameof nameDoubles
```

## <a name="see-also"></a><span data-ttu-id="43adb-140">참조</span><span class="sxs-lookup"><span data-stu-id="43adb-140">See also</span></span>

- [<span data-ttu-id="43adb-141">함수</span><span class="sxs-lookup"><span data-stu-id="43adb-141">Functions</span></span>](index.md)
