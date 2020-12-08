---
title: F#의 함수형 프로그래밍 소개
description: F#의 함수형 프로그래밍 기본 사항을 알아봅니다.
ms.date: 10/29/2018
ms.openlocfilehash: fc2aebe80de16b92942c3557c0e03c198883dde1
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740330"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="877da-103">F\#의 함수형 프로그래밍 소개</span><span class="sxs-lookup"><span data-stu-id="877da-103">Introduction to Functional Programming in F\#</span></span>

<span data-ttu-id="877da-104">함수형 프로그래밍은 함수 및 변경 불가능 데이터 사용을 강조 하는 프로그래밍 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="877da-105">형식화된 함수형 프로그래밍이란 함수형 프로그래밍이 F# 같은 정적 형식과 결합된 경우를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="877da-106">일반적으로 함수형 프로그래밍에서는 다음 개념을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="877da-107">기본 구문으로 사용하는 함수</span><span class="sxs-lookup"><span data-stu-id="877da-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="877da-108">문 대신 식</span><span class="sxs-lookup"><span data-stu-id="877da-108">Expressions instead of statements</span></span>
* <span data-ttu-id="877da-109">변수 대신 변경 불가능한 값</span><span class="sxs-lookup"><span data-stu-id="877da-109">Immutable values over variables</span></span>
* <span data-ttu-id="877da-110">명령형 프로그래밍 대신 선언적 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="877da-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="877da-111">이 시리즈에서는 F#을 사용하는 함수형 프로그래밍의 개념과 패턴을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="877da-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="877da-112">이 과정에서 F#의 일부 기능에 대해서도 배우게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="877da-113">용어</span><span class="sxs-lookup"><span data-stu-id="877da-113">Terminology</span></span>

<span data-ttu-id="877da-114">다른 프로그래밍 패러다임처럼 함수형 프로그래밍에도 반드시 알아야 하는 용어 모음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="877da-115">다음은 자주 보게 되는 대표적인 일반 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="877da-116">**함수** -함수는 입력을 제공하면 출력을 생성하는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="877da-117">형식적인 면에서 함수는 한 집합의 항목을 다른 집합으로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="877da-118">이러한 형식은 다양한 방식으로 구체화되는 데, 데이터 집합에서 작동하는 함수를 사용할 때는 더욱 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="877da-119">함수는 함수형 프로그래밍의 가장 기본적인(그리고 중요한) 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-119">It is the most basic (and important) concept in functional programming.</span></span>
* <span data-ttu-id="877da-120">**식** - 식은 값을 생성하는 코드의 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="877da-121">F#에서는 이 값은 바인딩하거나 명시적으로 무시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="877da-122">식은 함수 호출로 쉽게 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="877da-123">**순수성** - 순수성은 동일한 인수에서는 반환 값이 항상 동일하며, 계산에 어떠한 의도하지 않은 결과도 발생하지 않음을 의미하는 함수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="877da-124">순수한 함수는 자체 인수에만 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="877da-125">**참조 투명도** - 참조 투명도는 프로그램 동작에 영향을 주지 않고도 출력으로 대체될 수 있는 식 속성을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="877da-126">**불변성** - 불변성은 내부에서 값을 변경할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="877da-127">내부에서 변경할 수 있는 변수와는 반대되는 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="877da-128">예제</span><span class="sxs-lookup"><span data-stu-id="877da-128">Examples</span></span>

<span data-ttu-id="877da-129">다음은 이러한 핵심 개념을 보여주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="877da-130">Functions</span><span class="sxs-lookup"><span data-stu-id="877da-130">Functions</span></span>

<span data-ttu-id="877da-131">함수형 프로그래밍의 가장 일반적이고 기본적인 구문은 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="877da-132">다음은 1을 정수에 더하는 간단한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="877da-133">해당 형식 시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="877da-134">시그니처는 "`addOne`에서 `x`라는 `int`를 수락하여 `int`를 생성한다"는 뜻이라고 생각하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="877da-135">형식적인 면에서 `addOne`은 값을 한쪽 정수 집합에서 다른 정수 집합으로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="877da-136">`->` 토큰은 이 매핑을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="877da-137">F#에서는 대부분의 경우 수행 중인 작업을 함수 시그니처를 통해 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="877da-138">시그니처가 중요한 이유는 무엇일까요?</span><span class="sxs-lookup"><span data-stu-id="877da-138">So, why is the signature important?</span></span> <span data-ttu-id="877da-139">형식화된 함수형 프로그래밍에서 함수 구현은 일반적으로 실제 형식 시그니처보다 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="877da-140">런타임에서는 `addOne`이 값 1을 정수에 추가한다는 사실이 중요하지만, 프로그램을 구성할 때는 이 함수가 `int`를 수락하고 반환한다는 사실을 통해 함수의 실제 사용 방법을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="877da-141">또한 이 함수를 (형식 시그니처에 대해) 올바르게 사용하면 `addOne` 함수 본문 내에서 문제를 진단할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="877da-142">이것은 형식화된 함수형 프로그래밍의 자극제입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="877da-143">식</span><span class="sxs-lookup"><span data-stu-id="877da-143">Expressions</span></span>

<span data-ttu-id="877da-144">식은 값으로 계산되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="877da-145">작업을 수행하는 문과 달리 식은 값을 반환하는 작업이라고 생각하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="877da-146">함수형 프로그래밍에서 거의 언제나 식을 문 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="877da-147">이전 함수인 `addOne`을 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="877da-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="877da-148">`addOne`의 본문은 식입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="877da-149">`addOne` 함수의 결과 형식을 정의하는 이 식의 결과죠.</span><span class="sxs-lookup"><span data-stu-id="877da-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="877da-150">예를 들어 이 함수를 구성하는 식을 `string` 같은 다른 형식으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="877da-151">함수의 시그니처는 이제 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="877da-152">F#의 모든 형식은 `ToString()`을 호출할 수 있으며, 따라서 `x` 형식이 일반이 되며(이를 [자동 일반화](../language-reference/generics/automatic-generalization.md)하고 합니다) 결과 형식은 `string`이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="877da-153">식은 함수의 본문에만 국한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="877da-154">다른 곳에서 사용할 수 있는 값을 생성하는 식을 이용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="877da-155">대표적인 식은 `if`입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-155">A common one is `if`:</span></span>

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result
```

<span data-ttu-id="877da-156">`if` 식은 `result`라는 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="877da-157">`result`를 완전히 누락하면 `if` 식이 `addOneIfOdd` 함수의 본문이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="877da-158">식의 핵심은 값을 생성한다는 사실입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="877da-159">`unit`이라는 특수한 형식도 있는데, 반환할 내용이 없을 때 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="877da-160">예를 들어 다음과 같은 간단한 함수를 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="877da-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn $"String is: {str}"
```

<span data-ttu-id="877da-161">시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="877da-162">`unit` 형식은 반환되는 실제 값이 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="877da-163">결과로 반환되는 값이 없어도 "작동해야 하는" 루틴이 있을 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="877da-164">동일한 `if` 구문이 문이며 대부분의 경우 변경 변수가 값을 생성하는 명령형 프로그래밍과는 완전히 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="877da-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="877da-165">예를 들어 C#에서는 코드를 다음과 같이 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-165">For example, in C#, the code might be written like this:</span></span>

```csharp
bool IsOdd(int x) => x % 2 != 0;

int AddOneIfOdd(int input)
{
    var result = input;

    if (IsOdd(input))
    {
        result = input + 1;
    }

    return result;
}
```

<span data-ttu-id="877da-166">C#과 다른 C 스타일 언어는 식 기반 조건부 프로그래밍을 허용하는 [삼항 식](../../csharp/language-reference/operators/conditional-operator.md)을 지원한다는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="877da-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="877da-167">함수형 프로그래밍에서는 문을 이용해 값을 변경하는 경우가 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="877da-168">일부 함수형 언어는 문과 변경을 지원하지만, 함수형 프로그래밍에서는 두 개념을 잘 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="877da-169">순수 함수</span><span class="sxs-lookup"><span data-stu-id="877da-169">Pure functions</span></span>

<span data-ttu-id="877da-170">앞에서 설명한 것처럼 순수 함수는 다음을 수행하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="877da-171">동일한 입력에 대해서는 항상 동일한 값으로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="877da-172">의도하지 않은 결과를 유발하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-172">Have no side effects.</span></span>

<span data-ttu-id="877da-173">여기서는 수학 함수를 떠올리면 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="877da-174">수학에서 함수는 관련 인수에만 종속되며 의도하지 않은 결과를 유발하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="877da-175">수학 함수 `f(x) = x + 1`에서 `f(x)` 값은 `x` 값에만 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="877da-176">함수형 프로그래밍에서의 순수 함수도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="877da-177">순수 함수를 작성할 때 함수는 관련 인수에만 종속되고 의도하지 않은 결과를 유발하는 작업은 수행하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="877da-178">다음은 전역적이고 변경 가능한 상태에 종속되기 때문에 순수하지 않은 함수의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="877da-179">`addOneToValue` 함수는 순수하지 않은 함수임이 확실합니다. `value`가 언제든 1이 아닌 다른 값으로 변경될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="877da-180">전역 값에 종속되는 이 패턴은 함수형 프로그래밍에서는 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="877da-181">다음은 의도하지 않은 결과를 유발하기 때문에 순수하지 않은 함수의 또 다른 예입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x =
    printfn $"x is %d{x}"
    x + 1
```

<span data-ttu-id="877da-182">이 함수는 전역 값에 종속되지 않지만 `x` 의 값을 프로그램의 출력에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="877da-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="877da-183">함수를 사용하면 안 된다는 것이 아니라 함수가 순수하지 않다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span> <span data-ttu-id="877da-184">프로그램의 다른 부분이 출력 버퍼 같은 프로그램 외부 요소에 종속되는 경우, 이 함수를 호출하면 프로그램의 다른 부분에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-184">If another part of your program depends on something external to the program, such as the output buffer, then calling this function can affect that other part of your program.</span></span>

<span data-ttu-id="877da-185">`printfn` 문을 제거하면 순수 함수가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-185">Removing the `printfn` statement makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="877da-186">이 함수는 `printfn` 문을 사용하는 이전 버전보다 본질적으로 우수하지는 않지만, 함수로 하는 모든 작업이 값을 반환함을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-186">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="877da-187">이 함수를 여러 번 호출해도 매번 값 생성이라는 동일한 결과가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-187">Calling this function any number of times produces the same result: it just produces a value.</span></span> <span data-ttu-id="877da-188">순수성을 바탕으로 제공되는 예측 가능성은 많은 함수형 프로그래머가 원하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-188">The predictability given by purity is something many functional programmers strive for.</span></span>

### <a name="immutability"></a><span data-ttu-id="877da-189">불변성</span><span class="sxs-lookup"><span data-stu-id="877da-189">Immutability</span></span>

<span data-ttu-id="877da-190">마지막으로, 형식화된 함수형 프로그래밍의 가장 기본적인 개념은 불변성입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-190">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="877da-191">F#에서는 기본적으로 어떤 값도 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-191">In F#, all values are immutable by default.</span></span> <span data-ttu-id="877da-192">따라서 사용자가 변경 가능하다고 명시적으로 표시하지 않는 한 내부에서 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-192">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="877da-193">실제로 변경 불가능한 값을 사용한다는 것은 프로그래밍 접근 방식을 "뭔가를 바꿔야 해"에서 "새 값을 생성해야 해"로 변경한다는 뜻입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-193">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="877da-194">예를 들어 1을 값에 추가하면 기존 값이 변경되는 대신 새 값이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-194">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="877da-195">F#에서 다음 코드는 `value` 함수를 변경하지 **않습니다**. 대신 같음 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-195">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="877da-196">변형을 전혀 지원하지 않는 함수형 프로그래밍 언어도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-196">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="877da-197">F#에서는 변형이 지원되지만 값에 대한 기본 동작은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="877da-197">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="877da-198">이 개념은 데이터 구조에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-198">This concept extends even further to data structures.</span></span> <span data-ttu-id="877da-199">함수형 프로그래밍에서 집합(및 수많은 요소) 같은 변경 불가능한 데이터 구조는 최초 예상과는 다른 방식으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-199">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="877da-200">개념적으로 집합에 항목을 추가하면 집합이 변경되는 것이 아니라 추가된 값이 있는 새로운 집합이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-200">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="877da-201">작동 원리를 살펴보면, 대부분의 경우 이 작업은 값을 효과적으로 추적하여 적절한 데이터 표현을 도출하는 다른 데이터 구조를 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="877da-201">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="877da-202">값과 데이터 구조를 사용하는 이러한 방식은 대단히 중요합니다. 항목을 변경하는 모든 작업을 항목의 새 버전을 생성하는 작업처럼 취급해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="877da-202">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="877da-203">이렇게 하면 프로그램에서 같음 및 작음과 비교 같은 요소의 일관성을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-203">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="877da-204">다음 단계</span><span class="sxs-lookup"><span data-stu-id="877da-204">Next steps</span></span>

<span data-ttu-id="877da-205">다음 섹션에서는 함수 관련 심화 학습을 통해 함수형 프로그래밍에서 함수를 사용하는 다양한 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="877da-205">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="877da-206">[첫 번째 클래스 함수](first-class-functions.md)에서는 함수를 심층적으로 탐색하여 다양한 맥락에서 사용하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-206">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="877da-207">추가 참고 자료</span><span class="sxs-lookup"><span data-stu-id="877da-207">Further reading</span></span>

<span data-ttu-id="877da-208">[함수적 사고방식](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) 시리즈에서도 F#을 이용한 함수형 프로그래밍 관련 자료를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="877da-208">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="877da-209">함수형 프로그래밍의 기본 사항을 실용적이고 읽기 쉬운 방식으로 살펴보며, F#을 이용해 개념을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="877da-209">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>
