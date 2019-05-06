---
title: F# 함수형 프로그래밍 소개
description: F# 함수형 프로그래밍의 기본 사항에 대해 알아봅니다.
ms.date: 10/29/2018
ms.openlocfilehash: 84022e58c0f17b9e9875402c653c31e494e940da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772790"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="2ff62-103">F #의 함수형 프로그래밍 소개\#</span><span class="sxs-lookup"><span data-stu-id="2ff62-103">Introduction to Functional Programming in F\#</span></span>

<span data-ttu-id="2ff62-104">함수형 프로그래밍은 함수와 변경할 수 없는 데이터의 사용을 강조하는 프로그래밍 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="2ff62-105">형식화된 함수형 프로그래밍은 함수형 프로그래밍이 F#과 같은 정적 형식과 결합된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="2ff62-106">일반적으로 함수형 프로그래밍에서는 다음과 같은 개념이 강조됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="2ff62-107">사용하는 기본 구문으로서의 함수</span><span class="sxs-lookup"><span data-stu-id="2ff62-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="2ff62-108">명령문 대신 표현식</span><span class="sxs-lookup"><span data-stu-id="2ff62-108">Expressions instead of statements</span></span>
* <span data-ttu-id="2ff62-109">변수보다는 변경할 수 없는 값</span><span class="sxs-lookup"><span data-stu-id="2ff62-109">Immutable values over variables</span></span>
* <span data-ttu-id="2ff62-110">명령형 프로그래밍보다는 선언적 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2ff62-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="2ff62-111">이 시리즈를 통해 F#을 사용한 함수 프로그래밍의 개념과 패턴을 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="2ff62-112">따라서 진행하다 보면 F#도 배우게 됩니다</span><span class="sxs-lookup"><span data-stu-id="2ff62-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="2ff62-113">용어</span><span class="sxs-lookup"><span data-stu-id="2ff62-113">Terminology</span></span>

<span data-ttu-id="2ff62-114">다른 프로그래밍 패러다임과 마찬가지로 함수형 프로그래밍을 배우기 위해 필요한 어휘가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="2ff62-115">다음은 흔히 볼 수 있는 몇 가지 일반적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="2ff62-116">**함수** -함수는 입력이 주어지면 출력을 생성하는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="2ff62-117">어떤 항목을 하나의 집합에서 다른 집합으로 _맵핑_ 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="2ff62-118">이러한 형식은 다양한 방식, 특히 데이터 컬렉션에 대해 작동하는 함수를 사용할때 구체화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="2ff62-119">이는 함수형 프로그래밍에서 가장 기본적이고 중요한 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-119">It is the most basic (and important) concept in functional programming.</span></span> 
* <span data-ttu-id="2ff62-120">**표현식** - 표현식은 값을 생성하는 코드의 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="2ff62-121">F#에서는 이 값을 바인딩하거나 명시적으로 무시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="2ff62-122">표현식은 간단히 함수 호출로 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="2ff62-123">**순도** - 순도는 함수의 속성으로, 동일한 인수에 대해 반환 값이 항상 동일하고 해당 평가에는 부작용이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="2ff62-124">순수 함수는 전적으로 인수에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="2ff62-125">**참조 투명성** - 참조 투명성은 표현식의 속성으로, 프로그램의 동작에 영향을 주지 않고 해당 출력을 사용하여 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="2ff62-126">**불변성** - 불변성은 값을 변경할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="2ff62-127">이는 변경할 수 있는 변수와 대조됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="2ff62-128">예제</span><span class="sxs-lookup"><span data-stu-id="2ff62-128">Examples</span></span>

<span data-ttu-id="2ff62-129">다음 예제에서는 이러한 핵심 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="2ff62-130">함수</span><span class="sxs-lookup"><span data-stu-id="2ff62-130">Functions</span></span>

<span data-ttu-id="2ff62-131">함수형 프로그래밍에서 가장 일반적이고 기본적인 구조는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="2ff62-132">다음은 정수에 1을 추가하는 간단한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="2ff62-133">형식 시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="2ff62-134">이 시그니처는 "`addOne`은 `x`라는 `int`를 받아서 `int`를 생성합니다"라고 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="2ff62-135">`addOne`은 어떤 값을 정수 집합에서 정수 집합으로 _매핑_ 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="2ff62-136">`->` 토큰이 이 매핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="2ff62-137">F#에서는 일반적으로 함수 시그니처를 보고 어떤 작업을 수행하는지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="2ff62-138">그렇다면 시그니처는 왜 중요할까요?</span><span class="sxs-lookup"><span data-stu-id="2ff62-138">So, why is the signature important?</span></span> <span data-ttu-id="2ff62-139">형식화된 함수형 프로그래밍에서 함수의 구현은 종종 실제 형식 시그니처보다 덜 중요합니다!</span><span class="sxs-lookup"><span data-stu-id="2ff62-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="2ff62-140">`addOne`이 런타임에 값 1을 정수에 추가한다는 사실은 흥미롭지만, 프로그램을 만드는 시점에 이 프로그램이 `int`를 받고 반환한다는 사실은 이 함수의 실제 사용법을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="2ff62-141">또한 이 함수를 올바르게 사용하면(형식 시그니처와 관련하여) 모든 문제 진단은 `addOne` 함수의 본문 내에서만 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="2ff62-142">이는 형식화된 함수형 프로그래밍의 원동력입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="2ff62-143">표현식</span><span class="sxs-lookup"><span data-stu-id="2ff62-143">Expressions</span></span>

<span data-ttu-id="2ff62-144">표현식은 값으로 평가되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="2ff62-145">작업을 수행하는 명령문과는 대조적으로 표현식은 값을 반환하는 작업을 수행하는 것으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="2ff62-146">표현식은 함수형 프로그래밍에서 명령문을 위해 거의 항상 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="2ff62-147">이전 함수 `addOne`을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="2ff62-148">다음과 같이 `addOne`의 본문은 표현식입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="2ff62-149">이 표현식의 결과가 `addOne` 함수의 결과 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="2ff62-150">예를 들어, 이 함수를 구성하는 표현식을 `string`과 같은 다른 유형으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="2ff62-151">함수의 시그니처는 이제 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="2ff62-152">모든 형식에 이후 F# 있을 수 있습니다 `ToString()` 호출의 형식 `x` 제네릭 만들어졌습니다 (호출 [자동 일반화](../language-reference/generics/automatic-generalization.md)), 고의 결과 형식이 `string`.</span><span class="sxs-lookup"><span data-stu-id="2ff62-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="2ff62-153">식은 함수의 본문에만 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="2ff62-154">다른 곳에서 사용할 값을 생성 하는 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="2ff62-155">하나는 일반적인 `if`:</span><span class="sxs-lookup"><span data-stu-id="2ff62-155">A common one is `if`:</span></span>

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

<span data-ttu-id="2ff62-156">합니다 `if` 이라고 하는 값을 생성 하는 식 `result`합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="2ff62-157">생략할 수 있습니다 `result` 완전히 수행 합니다 `if` 식 본문의는 `addOneIfOdd` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="2ff62-158">식에 대 한 기억해 야 할 주요 사항은 이러한 값을 생성 하는 경우</span><span class="sxs-lookup"><span data-stu-id="2ff62-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="2ff62-159">특수 형식이 `unit`를 반환 하는 것이 없을 때 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="2ff62-160">예를 들어이 간단한 함수를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="2ff62-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

<span data-ttu-id="2ff62-161">시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="2ff62-162">`unit` 실제 값을 반환 하는 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="2ff62-163">해야 하는 루틴을 해야 하는 경우에 유용 "수행" 작동 불구 하 고 해당 작업의 결과로 반환할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="2ff62-164">이 명령형 프로그래밍에 대조에서 위치에 해당 하는 `if` 구문은 문 및 값을 생성 합니다. 주로 사용 하 여 변수를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="2ff62-165">예를 들어, C#에 다음과 같은 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-165">For example, in C#, the code might be written like this:</span></span>

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

<span data-ttu-id="2ff62-166">주목할 만한 가치가 C# 다른 C 스타일 언어를 지원할 합니다 [삼진 식은](../../csharp/language-reference/operators/conditional-operator.md), 조건부 식 기반 프로그래밍을 수행할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="2ff62-167">함수형 프로그래밍 문 사용 하 여 값을 변경할 드문 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="2ff62-168">일부 함수형 언어 문 및 변형을 지원 하지만 일반적으로 함수형 프로그래밍에서 이러한 개념을 사용 하는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="2ff62-169">순수 함수</span><span class="sxs-lookup"><span data-stu-id="2ff62-169">Pure functions</span></span>

<span data-ttu-id="2ff62-170">앞에서 언급 한 순수 함수는 함수:</span><span class="sxs-lookup"><span data-stu-id="2ff62-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="2ff62-171">항상 동일한 입력에 동일한 값으로 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="2ff62-172">부작용 없음.</span><span class="sxs-lookup"><span data-stu-id="2ff62-172">Have no side effects.</span></span>

<span data-ttu-id="2ff62-173">이 컨텍스트에서 수치 연산 함수 생각 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="2ff62-174">수학에서 함수는 해당 인수에만 의존 하 고 부작용이 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="2ff62-175">수치 연산 함수가 `f(x) = x + 1`, 값 `f(x)` 의 값에만 의존 `x`합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="2ff62-176">함수형 프로그래밍의 순수 함수는 동일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="2ff62-177">순수 함수를 작성할 때 함수 인수에만 의존 하 고 부작용에는 아무 작업도 수행 하지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="2ff62-178">전역, 변경할 수 있는 상태에 종속 되어 있으므로 비 순수 함수의 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="2ff62-179">합니다 `addOneToValue` 명확 하 게 순수 함수가 아닙니다. 때문에 `value` 언제 든 지 다른 값이 1 보다 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="2ff62-180">이 패턴을 전역 값에 따라 함수형 프로그래밍에서 사용 하지 않아야 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="2ff62-181">파생 작업을 수행 하므로 비 순수 함수의 또 다른 예로 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="2ff62-182">값을 씁니다이 함수는 전역 값에 종속 되지 않습니다, 하지만 `x` 프로그램의 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="2ff62-183">근본적으로 이렇게 잘못 된 항목이 없는, 하지만 순수 함수가 아닙니다 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span> <span data-ttu-id="2ff62-184">프로그램의 다른 파트는 출력 버퍼를 비롯 하 여 프로그램에 종속 된 경우이 함수를 호출한 프로그램의 다른 일부는 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-184">If another part of your program depends on something external to the program, such as the output buffer, then calling this function can affect that other part of your program.</span></span>

<span data-ttu-id="2ff62-185">제거 된 `printfn` 문을 순수 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-185">Removing the `printfn` statement makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="2ff62-186">아니지만이 함수 기본적으로 _더 나은_ 사용 하 여 이전 버전 보다는 `printfn` 문에서 반드시이 함수는 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-186">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="2ff62-187">동일한 결과가 생성이 함수를 여러 번 호출 합니다: 값만 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-187">Calling this function any number of times produces the same result: it just produces a value.</span></span> <span data-ttu-id="2ff62-188">순도 제공한 예측 가능성에 대 한 대부분의 함수형 프로그래머 노력입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-188">The predictability given by purity is something many functional programmers strive for.</span></span>

### <a name="immutability"></a><span data-ttu-id="2ff62-189">불변성</span><span class="sxs-lookup"><span data-stu-id="2ff62-189">Immutability</span></span>

<span data-ttu-id="2ff62-190">마지막으로, 불변성은 형식화 된 함수형 프로그래밍의 가장 기본적인 개념 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-190">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="2ff62-191">F#에서 모든 값은 기본적으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-191">In F#, all values are immutable by default.</span></span> <span data-ttu-id="2ff62-192">즉, 변경할 수 있는 것으로 명시적으로 표시 하지 않는 한 내부적으로 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-192">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="2ff62-193">실제로 변경할 수 없는 값으로 작업 하는 "I need 무언가 변경 하려면"에서 프로그래밍 하는 접근 방식을 변경한에 "I need 새 값을 생성 하기 위해"를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-193">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="2ff62-194">예를 들어, 기존 항목을 변경 하지 새 값을 생성 값으로 추가 1을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-194">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="2ff62-195">F#, 다음 코드에서는 **되지** 변경할 합니다 `value` 함수, 같음 검사를 수행 하십시오:</span><span class="sxs-lookup"><span data-stu-id="2ff62-195">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="2ff62-196">일부 함수형 프로그래밍 언어 변형을 전혀 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-196">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="2ff62-197">F#는 지원 되지만 값에 대 한 기본 동작은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-197">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="2ff62-198">이 개념은 데이터 구조까지 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-198">This concept extends even further to data structures.</span></span> <span data-ttu-id="2ff62-199">함수형 프로그래밍을 변경할 수 없는 데이터 구조 집합 (및 더 많은)가 다른 구현을 처음 수 보다 같은 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-199">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="2ff62-200">개념적으로 집합에 항목을 추가 집합은 변경 되지 않으면 같은 생성 된 _새_ 추가 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-200">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="2ff62-201">내부적으로이 하는 경우가 많습니다 적절 한 데이터 표현의 결과적으로 지정할 수 있도록 값을 효율적으로 추적을 허용 하는 다른 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-201">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="2ff62-202">값 및 데이터 구조를 사용 하는이 스타일은 새 버전을 만드는 경우에 따라 항목을 수정 하는 모든 작업을 처리 해야 하는 대로 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-202">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="2ff62-203">따라서 프로그램에서 일관 되도록 같음 및 작음 비교 가능 등.</span><span class="sxs-lookup"><span data-stu-id="2ff62-203">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2ff62-204">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2ff62-204">Next steps</span></span>

<span data-ttu-id="2ff62-205">다음 섹션에서는 함수형 프로그래밍에 사용할 수 있는 다른 방법을 탐색 하는 함수를 철저 하 게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-205">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="2ff62-206">[첫 번째 클래스 함수](first-class-functions.md) 함수 사용 하 여 다양 한 컨텍스트에서 하는 방법을 보여 주는 깊이 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-206">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="2ff62-207">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2ff62-207">Further reading</span></span>

<span data-ttu-id="2ff62-208">합니다 [기능적으로 생각](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) 시리즈를 사용한 함수형 프로그래밍에 대해 자세히 알아보려면 또 다른 유용한 리소스는 F#합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-208">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="2ff62-209">Pragmatic 및 보다 읽기 쉬운 방식으로 함수형 프로그래밍의 기본적인 사항을 다룹니다를 사용 하 여 F# 개념을 설명 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff62-209">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>
