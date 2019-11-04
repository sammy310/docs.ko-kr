---
title: F#의 함수형 프로그래밍 소개
description: 에서 F#함수형 프로그래밍에 대 한 기본 사항을 알아봅니다.
ms.date: 10/29/2018
ms.openlocfilehash: e1a0edc61dbe13012c48e166d490e22ebc70d6a0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424704"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="b5e3f-103">F\#의 함수형 프로그래밍 소개</span><span class="sxs-lookup"><span data-stu-id="b5e3f-103">Introduction to Functional Programming in F\#</span></span>

<span data-ttu-id="b5e3f-104">함수형 프로그래밍은 함수 및 변경할 수 없는 데이터의 사용을 강조 하는 프로그래밍의 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="b5e3f-105">형식화 된 함수형 프로그래밍은 함수형 프로그래밍이와 F#같은 정적 형식과 결합 된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="b5e3f-106">일반적으로 함수형 프로그래밍에서는 다음 개념을 강조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="b5e3f-107">사용 하는 기본 구문으로 함수 사용</span><span class="sxs-lookup"><span data-stu-id="b5e3f-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="b5e3f-108">문 대신 식</span><span class="sxs-lookup"><span data-stu-id="b5e3f-108">Expressions instead of statements</span></span>
* <span data-ttu-id="b5e3f-109">변수에 대 한 변경할 수 없는 값</span><span class="sxs-lookup"><span data-stu-id="b5e3f-109">Immutable values over variables</span></span>
* <span data-ttu-id="b5e3f-110">명령적 프로그래밍에 대 한 선언적 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b5e3f-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="b5e3f-111">이 시리즈 전체에서를 사용 하 여 F#함수형 프로그래밍의 개념과 패턴을 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="b5e3f-112">이 과정에서 몇 가지 F# 방법을 배우게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="b5e3f-113">용어</span><span class="sxs-lookup"><span data-stu-id="b5e3f-113">Terminology</span></span>

<span data-ttu-id="b5e3f-114">다른 프로그래밍 패러다임과 마찬가지로 함수형 프로그래밍에는 결국 학습 해야 하는 어휘가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="b5e3f-115">다음은 전체 시간을 볼 수 있는 몇 가지 일반적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="b5e3f-116">**함수** -함수는 입력이 제공 될 때 출력을 생성 하는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="b5e3f-117">공식적으로는 한 집합에서 다른 집합으로 항목을 _매핑합니다_ .</span><span class="sxs-lookup"><span data-stu-id="b5e3f-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="b5e3f-118">특히 데이터 컬렉션에 대해 작동 하는 함수를 사용 하는 경우이 정해진는 구체적으로 구체적으로 리프트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="b5e3f-119">함수형 프로그래밍의 가장 기본적인 (및 중요 한) 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-119">It is the most basic (and important) concept in functional programming.</span></span>
* <span data-ttu-id="b5e3f-120">**식** -식은 값을 생성 하는 코드의 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="b5e3f-121">에서 F#이 값은 바인딩되어야 하거나 명시적으로 무시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="b5e3f-122">식은 함수 호출로 일반적으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="b5e3f-123">**순도** -순도는 동일한 인수에 대해 해당 반환 값이 항상 동일 하 고 해당 계산에 부작용이 없도록 하는 함수의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="b5e3f-124">순수 함수는 해당 인수에 전적으로 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="b5e3f-125">**참조 투명성** -참조 투명성은 프로그램의 동작에 영향을 주지 않고 출력으로 바꿀 수 있도록 식의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="b5e3f-126">**불변성** -불변성은 내부에서 값을 변경할 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="b5e3f-127">이는 현재 위치가 변경 될 수 있는 변수와 대조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="b5e3f-128">예제</span><span class="sxs-lookup"><span data-stu-id="b5e3f-128">Examples</span></span>

<span data-ttu-id="b5e3f-129">다음 예에서는 이러한 핵심 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="b5e3f-130">함수</span><span class="sxs-lookup"><span data-stu-id="b5e3f-130">Functions</span></span>

<span data-ttu-id="b5e3f-131">함수형 프로그래밍에서 가장 일반적이 고 기본적인 구문은 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="b5e3f-132">1을 정수에 더하는 간단한 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="b5e3f-133">해당 형식 시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="b5e3f-134">시그니처는 "`addOne` `x` `int`를 수락 하 고 `int`를 생성 하는"으로 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="b5e3f-135">보다 공식적으로 `addOne` 정수 집합의 값을 정수 집합에 _매핑합니다_ .</span><span class="sxs-lookup"><span data-stu-id="b5e3f-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="b5e3f-136">`->` 토큰은이 매핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="b5e3f-137">F#에서는 일반적으로 함수 시그니처를 확인 하 여 수행 되는 작업에 대 한 의미를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="b5e3f-138">그렇다면 서명이 중요 한 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="b5e3f-138">So, why is the signature important?</span></span> <span data-ttu-id="b5e3f-139">형식화 된 함수형 프로그래밍에서 함수 구현은 실제 형식 서명 보다 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="b5e3f-140">값 1을 정수에 추가 `addOne`는 것은 런타임에 유용 하지만 프로그램을 생성 하는 경우에는이 함수를 사용 하는 방법에 `int` 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="b5e3f-141">또한이 함수를 올바르게 사용 하는 경우 (형식 시그니처를 기준으로) 문제를 진단 하는 작업은 `addOne` 함수 본문 내 에서만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="b5e3f-142">형식화 된 함수형 프로그래밍의 자극 제입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="b5e3f-143">표현식</span><span class="sxs-lookup"><span data-stu-id="b5e3f-143">Expressions</span></span>

<span data-ttu-id="b5e3f-144">식은 값으로 계산 되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="b5e3f-145">작업을 수행 하는 문과 달리 식은 값을 다시 제공 하는 작업을 수행 하는 것으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="b5e3f-146">식은 함수형 프로그래밍의 문을 위해 거의 항상 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="b5e3f-147">`addOne`이전 함수를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="b5e3f-148">`addOne`의 본문은 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="b5e3f-149">`addOne` 함수의 결과 유형을 정의 하는이 식의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="b5e3f-150">예를 들어이 함수를 구성 하는 식은 `string`같은 다른 형식으로 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="b5e3f-151">함수 시그니처는 이제 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="b5e3f-152">의 F# 모든 형식이 `ToString()` 호출 될 수 있으므로 `x`의 형식은 제네릭 ( [자동 일반화](../language-reference/generics/automatic-generalization.md)라고 함)로 설정 되 고 결과 형식은 `string`입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="b5e3f-153">식은 단순히 함수의 본문이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="b5e3f-154">다른 곳에서 사용 하는 값을 생성 하는 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="b5e3f-155">일반적인 항목은 `if`입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-155">A common one is `if`:</span></span>

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

<span data-ttu-id="b5e3f-156">`if` 식은 `result`라는 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="b5e3f-157">`result`를 완전히 생략 하 여 `if` 식을 `addOneIfOdd` 함수의 본문으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="b5e3f-158">식에 대해 기억해 야 할 중요 한 점은 값을 생성 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="b5e3f-159">반환할 항목이 없을 때 사용 되는 특별 한 형식 `unit`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="b5e3f-160">예를 들어 다음과 같은 간단한 함수를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

<span data-ttu-id="b5e3f-161">시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="b5e3f-162">`unit` 형식은 반환 되는 실제 값이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="b5e3f-163">이는 해당 작업의 결과로 반환할 값이 없는 경우에도 "작업 수행" 해야 하는 루틴이 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="b5e3f-164">이는 동일한 `if` 구문이 문이 고 값을 생성 하는 것이 일반적으로 변경 변수를 사용 하 여 수행 되는 명령형 프로그래밍과 매우 대조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="b5e3f-165">예를 들어에서 C#코드는 다음과 같이 작성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-165">For example, in C#, the code might be written like this:</span></span>

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

<span data-ttu-id="b5e3f-166">및 기타 C 스타일 언어 C# 는 식 기반 조건부 프로그래밍을 허용 하는 [삼항 식을](../../csharp/language-reference/operators/conditional-operator.md)지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="b5e3f-167">함수형 프로그래밍에서는 문을 사용 하 여 값을 변경할 경우는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="b5e3f-168">일부 기능 언어는 문과 변형을 지원 하지만 함수형 프로그래밍에서 이러한 개념을 사용 하는 것은 일반적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="b5e3f-169">순수 함수</span><span class="sxs-lookup"><span data-stu-id="b5e3f-169">Pure functions</span></span>

<span data-ttu-id="b5e3f-170">앞에서 설명한 것 처럼 순수 함수는 다음을 수행 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="b5e3f-171">항상 동일한 입력에 대해 동일한 값으로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="b5e3f-172">부작용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-172">Have no side effects.</span></span>

<span data-ttu-id="b5e3f-173">이 컨텍스트에서 수학 함수를 생각해 보면 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="b5e3f-174">수학에서 함수는 해당 인수에만 종속 되며 의도 하지 않은 결과가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="b5e3f-175">수치 연산 함수 `f(x) = x + 1``f(x)` 값은 `x`값에만 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="b5e3f-176">함수형 프로그래밍의 순수 함수는 동일한 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="b5e3f-177">순수 함수를 작성 하는 경우 함수는 해당 인수에만 종속 되어야 하며 부작용이 발생 하는 작업을 수행 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="b5e3f-178">다음은 전역적이 고 변경 가능한 상태에 종속 되기 때문에 비 순수 함수의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="b5e3f-179">`addOneToValue` 함수는 한 번에 1과 다른 값을 갖도록 변경 될 수 `value` 있으므로 명확 하 게 비 순수형.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="b5e3f-180">전역 값에 따라이 패턴은 함수형 프로그래밍에서 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="b5e3f-181">다음은 파생 작업을 수행 하기 때문에 비 순수 함수의 또 다른 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x =
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="b5e3f-182">이 함수는 전역 값에 의존 하지 않지만 `x`의 값을 프로그램의 출력에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="b5e3f-183">이 작업을 수행 하는 경우 기본적으로 잘못 된 것은 아니지만 함수는 순수 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span> <span data-ttu-id="b5e3f-184">프로그램의 다른 부분이 출력 버퍼와 같은 프로그램 외부에 종속 된 경우이 함수를 호출 하면 프로그램의 다른 부분에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-184">If another part of your program depends on something external to the program, such as the output buffer, then calling this function can affect that other part of your program.</span></span>

<span data-ttu-id="b5e3f-185">`printfn` 문을 제거 하면 함수를 순수 하 게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-185">Removing the `printfn` statement makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="b5e3f-186">이 함수는 기본적으로 `printfn` 문을 사용 하는 이전 버전 보다 _더 나은_ 것은 아니지만이 함수는 모든 함수에서 값을 반환 하는 것을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-186">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="b5e3f-187">이 함수를 여러 번 호출 하면 동일한 결과가 생성 됩니다. 값만 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-187">Calling this function any number of times produces the same result: it just produces a value.</span></span> <span data-ttu-id="b5e3f-188">순도로 제공 되는 예측 가능성은 프로그래머가 많은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-188">The predictability given by purity is something many functional programmers strive for.</span></span>

### <a name="immutability"></a><span data-ttu-id="b5e3f-189">불변성</span><span class="sxs-lookup"><span data-stu-id="b5e3f-189">Immutability</span></span>

<span data-ttu-id="b5e3f-190">마지막으로 형식화 된 함수형 프로그래밍의 가장 기본적인 개념 중 하나는 불변성입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-190">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="b5e3f-191">에서 F#모든 값은 기본적으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-191">In F#, all values are immutable by default.</span></span> <span data-ttu-id="b5e3f-192">즉, 변경 가능한 것으로 명시적으로 표시 하지 않는 한 내부에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-192">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="b5e3f-193">실제로 변경할 수 없는 값을 사용 하 여 작업 하는 방법은 "항목을 변경 해야 합니다."를 "새 값을 생성 해야 합니다."에서 프로그래밍 방식으로 변경 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-193">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="b5e3f-194">예를 들어 값에 1을 추가 하면 기존 값을 변경 하는 것이 아니라 새 값이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-194">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="b5e3f-195">에서 F#다음 코드는 `value` 함수를 변경할 **수** 없습니다. 대신, 같음 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-195">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="b5e3f-196">일부 함수형 프로그래밍 언어에서는 변형을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-196">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="b5e3f-197">F#에서는 지원 되지만 값에 대 한 기본 동작은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-197">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="b5e3f-198">이 개념은 데이터 구조를 더욱 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-198">This concept extends even further to data structures.</span></span> <span data-ttu-id="b5e3f-199">함수형 프로그래밍에서 집합 (및 기타)과 같은 변경할 수 없는 데이터 구조에는 처음에는 것과 다른 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-199">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="b5e3f-200">개념적으로 집합에 항목을 추가 하는 것과 같은 항목은 집합을 변경 하지 않으며 추가 된 값을 사용 하 여 _새_ 집합을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-200">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="b5e3f-201">내부적으로는 데이터의 적절 한 표현을 결과로 제공할 수 있도록 값을 효율적으로 추적할 수 있도록 하는 다른 데이터 구조를 통해이 작업을 수행 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-201">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="b5e3f-202">이러한 스타일의 값과 데이터 구조를 사용 하는 것이 중요 합니다 .이는 해당 항목의 새 버전을 만드는 것 처럼이를 수정 하는 작업을 강제로 처리 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-202">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="b5e3f-203">따라서 프로그램에서 같음 및 작음 비교 가능 같은 작업을 일관 되 게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-203">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b5e3f-204">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b5e3f-204">Next steps</span></span>

<span data-ttu-id="b5e3f-205">다음 섹션에서는 함수 프로그래밍에 사용할 수 있는 다양 한 방법을 탐색 하는 함수를 철저히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-205">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="b5e3f-206">[첫 번째 클래스 함수](first-class-functions.md) 는 함수를 많이 탐색 하 여 다양 한 컨텍스트에서 사용할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-206">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="b5e3f-207">추가 정보</span><span class="sxs-lookup"><span data-stu-id="b5e3f-207">Further reading</span></span>

<span data-ttu-id="b5e3f-208">함수형 [시리즈는를 사용한](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) F#함수형 프로그래밍에 대해 배우는 또 다른 유용한 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-208">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="b5e3f-209">개념을 설명 하는 기능을 사용 하 여 F# 실용적이 고 읽기 쉬운 방식으로 함수형 프로그래밍의 기본 사항을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="b5e3f-209">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>
