---
title: 계산 식
description: 제어 흐름 구문 및 바인딩을 사용 하 여 시퀀싱 하 F# 고 결합할 수 있는 계산을 작성 하기 위한 편리한 구문을 만드는 방법에 대해 알아봅니다.
ms.date: 03/15/2019
ms.openlocfilehash: ea560bb6eec82672544c7c442b671b63e405474c
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799052"
---
# <a name="computation-expressions"></a><span data-ttu-id="0bb03-103">계산 식</span><span class="sxs-lookup"><span data-stu-id="0bb03-103">Computation Expressions</span></span>

<span data-ttu-id="0bb03-104">의 F# 계산 식은 제어 흐름 구문 및 바인딩을 사용 하 여 시퀀싱 하 고 결합할 수 있는 계산을 작성 하는 편리한 구문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="0bb03-105">계산 식의 종류에 따라 monads, monoids, monad 변환기 및 applicative 함수를 표현 하는 방법으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="0bb03-106">그러나 Haskell의 *do 표기법* 과 같은 다른 언어와 달리, 이러한 언어는 단일 추상화에 연결 되지 않으며, 매크로 또는 다른 형태의 메타 프로그래밍를 사용 하 여 편리 하 고 상황에 맞는 구문을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="0bb03-107">개요</span><span class="sxs-lookup"><span data-stu-id="0bb03-107">Overview</span></span>

<span data-ttu-id="0bb03-108">계산은 많은 형태를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-108">Computations can take many forms.</span></span> <span data-ttu-id="0bb03-109">가장 일반적인 계산 형태는 단일 스레드 실행 이며 이해 하 고 수정 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="0bb03-110">그러나 일부 계산 형태는 단일 스레드 실행 만큼 간단 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="0bb03-111">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-111">Some examples include:</span></span>

- <span data-ttu-id="0bb03-112">비결 정적 계산</span><span class="sxs-lookup"><span data-stu-id="0bb03-112">Non-deterministic computations</span></span>
- <span data-ttu-id="0bb03-113">비동기 계산</span><span class="sxs-lookup"><span data-stu-id="0bb03-113">Asynchronous computations</span></span>
- <span data-ttu-id="0bb03-114">Effectful 계산</span><span class="sxs-lookup"><span data-stu-id="0bb03-114">Effectful computations</span></span>
- <span data-ttu-id="0bb03-115">인기 계산</span><span class="sxs-lookup"><span data-stu-id="0bb03-115">Generative computations</span></span>

<span data-ttu-id="0bb03-116">일반적으로 응용 프로그램의 특정 부분에서 수행 해야 하는 *상황* 에 맞는 계산이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="0bb03-117">컨텍스트를 구분 하는 코드를 작성 하는 것이 더 어려울 수 있습니다 .이 작업을 수행 하는 것을 방지 하기 위해 추상화 없이 지정 된 컨텍스트 외부에서 계산을 "누수" 하는 것이</span><span class="sxs-lookup"><span data-stu-id="0bb03-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="0bb03-118">이러한 추상화는 종종 직접 작성 하기가 쉽지 않으므로 **계산 식**이라고 하 F# 는 일반화 된 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="0bb03-119">계산 식은 상황에 맞는 계산을 인코딩하기 위한 일관 된 구문 및 추상화 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="0bb03-120">모든 계산 식은 *작성기* 형식에 의해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="0bb03-121">작성기 유형은 계산 식에 사용할 수 있는 작업을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="0bb03-122">사용자 지정 계산 식을 만드는 방법을 보여 주는 [새 계산 식 형식 만들기](computation-expressions.md#creating-a-new-type-of-computation-expression)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bb03-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="0bb03-123">구문 개요</span><span class="sxs-lookup"><span data-stu-id="0bb03-123">Syntax overview</span></span>

<span data-ttu-id="0bb03-124">모든 계산 식의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-124">All computation expressions have the following form:</span></span>

```fsharp
builder-expr { cexper }
```

<span data-ttu-id="0bb03-125">여기서 `builder-expr`은 계산 식을 정의 하는 작성기 형식의 이름이 고 `cexper`는 계산 식의 식 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="0bb03-126">예를 들어 `async` 계산 식 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="0bb03-127">이전 예제와 같이 계산 식 내에서 사용할 수 있는 특별 한 추가 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="0bb03-128">계산 식에는 다음과 같은 식 형식이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="0bb03-129">이러한 각 키워드와 기타 표준 F# 키워드는 지원 빌더 유형에 정의 된 경우 계산 식 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="0bb03-130">이에 대 한 유일한 예외는 `match!``let!`를 사용 하 여 결과에 대 한 패턴 일치를 sugar는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="0bb03-131">작성기 형식은 계산 식의 조각이 결합 되는 방법을 제어 하는 특수 메서드를 정의 하는 개체입니다. 즉, 해당 메서드는 계산 식이 동작 하는 방식을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="0bb03-132">작성기 클래스를 설명 하는 또 다른 방법은 루프 및 바인딩과 같은 여러 F# 구문의 작업을 사용자 지정할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="0bb03-133">`let!` 키워드는 다른 계산 식에 대 한 호출 결과를 이름에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="0bb03-134">`let`를 사용 하 여 계산 식에 대 한 호출을 바인딩하는 경우 계산 식의 결과를 얻지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="0bb03-135">대신 계산 식에 대 한 계산 되지 *않은 호출 값* 을 바인딩 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="0bb03-136">`let!`를 사용 하 여 결과에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="0bb03-137">`let!`은 작성기 형식의 `Bind(x, f)` 멤버에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="0bb03-138">`do!` 키워드는 작성기에서 `Zero` 멤버에 의해 정의 되는 `unit`와 유사한 형식을 반환 하는 계산 식을 호출 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="0bb03-139">[비동기 워크플로의](asynchronous-workflows.md)경우이 형식은 `Async<unit>`입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="0bb03-140">다른 계산 식의 경우 형식이 `CExpType<unit>`될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="0bb03-141">`do!`는 작성기 형식의 `Bind(x, f)` 멤버에 의해 정의 되며 `f` `unit`를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="0bb03-142">`yield` 키워드는 계산 식에서 값을 반환 하 여 <xref:System.Collections.Generic.IEnumerable%601>사용할 수 있도록 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="0bb03-143">[ C#에서 yield 키워드 ](../../csharp/language-reference/keywords/yield.md)와 마찬가지로 계산 식의 각 요소는 반복 될 때 다시 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-143">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="0bb03-144">`yield`는 작성기 형식의 `Yield(x)` 멤버에 의해 정의 됩니다. 여기서 `x`는 다시 생성할 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-144">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="0bb03-145">`yield!` 키워드는 계산 식에서 값 컬렉션을 평면화 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-145">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..3 -> i * i
    }

let cubes =
    seq {
        for i in 1..3 -> i * i * i
    }

let squaresAndCubes =
    seq {
        yield! squares
        yield! cubes
    }

printfn "%A" squaresAndCubes // Prints - 1; 4; 9; 1; 8; 27
```

<span data-ttu-id="0bb03-146">계산 식이 계산 되 면 `yield!`에서 호출한 계산 식의 항목이 하나씩 다시 생성 되 고 결과가 평면화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-146">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="0bb03-147">`yield!`는 작성기 형식의 `YieldFrom(x)` 멤버에 의해 정의 됩니다. 여기서 `x`는 값의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-147">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

### `return`

<span data-ttu-id="0bb03-148">`return` 키워드는 계산 식에 해당 하는 형식의 값을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-148">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="0bb03-149">`yield`를 사용 하는 계산 식 외에도 계산 식을 "완료" 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-149">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="0bb03-150">`return`는 작성기 형식의 `Return(x)` 멤버에 의해 정의 됩니다. 여기서 `x`는 래핑할 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-150">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="0bb03-151">`return!` 키워드는 계산 식의 값을 인식 하 고 해당 결과를 계산 식에 해당 하는 형식으로 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-151">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="0bb03-152">`return!`는 작성기 형식의 `ReturnFrom(x)` 멤버에 의해 정의 됩니다. 여기서 `x`는 다른 계산 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-152">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="0bb03-153">F# 4.5부터`match!`키워드를 사용 하면 결과에 대해 다른 계산 식과 패턴 일치에 대 한 호출을 인라인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-153">Starting with F# 4.5, the `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="0bb03-154">`match!`를 사용 하 여 계산 식을 호출 하는 경우 `let!`와 같은 호출의 결과를 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-154">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="0bb03-155">이는 결과가 [선택적인](options.md)인 계산 식을 호출할 때 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-155">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="0bb03-156">기본 제공 계산 식</span><span class="sxs-lookup"><span data-stu-id="0bb03-156">Built-in computation expressions</span></span>

<span data-ttu-id="0bb03-157">핵심 F# 라이브러리는 세 가지 기본 제공 계산 식인 [시퀀스 식](sequences.md), [비동기 워크플로](asynchronous-workflows.md)및 [쿼리 식을](query-expressions.md)정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-157">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="0bb03-158">새 계산 식 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="0bb03-158">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="0bb03-159">작성기 클래스를 만들고 클래스에 특정 특수 메서드를 정의 하 여 계산 식의 특성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-159">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="0bb03-160">작성기 클래스는 다음 표에 나열 된 대로 메서드를 선택적으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-160">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="0bb03-161">다음 표에서는 workflow builder 클래스에서 사용할 수 있는 메서드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-161">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="0bb03-162">**메서드**</span><span class="sxs-lookup"><span data-stu-id="0bb03-162">**Method**</span></span>|<span data-ttu-id="0bb03-163">**일반적인 서명**</span><span class="sxs-lookup"><span data-stu-id="0bb03-163">**Typical signature(s)**</span></span>|<span data-ttu-id="0bb03-164">**설명**</span><span class="sxs-lookup"><span data-stu-id="0bb03-164">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="0bb03-165">계산 식의 `let!` 및 `do!`에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-165">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="0bb03-166">계산 식을 함수로 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-166">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="0bb03-167">계산 식의 `return`에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-167">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="0bb03-168">계산 식의 `return!`에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-168">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="0bb03-169">`M<'T> -> M<'T>` 또는</span><span class="sxs-lookup"><span data-stu-id="0bb03-169">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="0bb03-170">계산 식을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-170">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="0bb03-171">`M<'T> * M<'T> -> M<'T>` 또는</span><span class="sxs-lookup"><span data-stu-id="0bb03-171">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="0bb03-172">계산 식의 시퀀싱을 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-172">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="0bb03-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` 또는</span><span class="sxs-lookup"><span data-stu-id="0bb03-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="0bb03-174">계산 식의 `for...do` 식에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-174">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="0bb03-175">계산 식의 `try...finally` 식에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-175">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="0bb03-176">계산 식의 `try...with` 식에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-176">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|<span data-ttu-id="0bb03-177">계산 식의 `use` 바인딩에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-177">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="0bb03-178">계산 식의 `while...do` 식에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-178">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="0bb03-179">계산 식의 `yield` 식에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-179">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="0bb03-180">계산 식의 `yield!` 식에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-180">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="0bb03-181">계산 식에서 `if...then` 식의 빈 `else` 분기에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-181">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|<span data-ttu-id="0bb03-182">계산 식이 `Run` 멤버에 따옴표로 전달 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-182">Indicates that the computation expression is passed to the `Run` member as a quotation.</span></span> <span data-ttu-id="0bb03-183">계산의 모든 인스턴스를 따옴표로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-183">It translates all instances of a computation into a quotation.</span></span>|

<span data-ttu-id="0bb03-184">작성기 클래스의 여러 메서드는 `M<'T>` 구문을 사용 하 고 반환 합니다 .이 구문은 일반적으로 결합 되는 계산의 종류에 대 한 `Async<'T>` (예: 비동기 워크플로에 대 한 및 시퀀스에 대 한 `Seq<'T>`)와 같이 개별적으로 정의 되는 형식입니다. 워크플로도.</span><span class="sxs-lookup"><span data-stu-id="0bb03-184">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="0bb03-185">이러한 메서드의 시그니처를 사용 하 여 서로 결합 하 고 중첩할 수 있으므로 한 구문에서 반환 된 워크플로 개체를 다음에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-185">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="0bb03-186">컴파일러는 계산 식을 구문 분석할 때 앞의 테이블에 있는 메서드와 계산 식의 코드를 사용 하 여 식을 일련의 중첩 된 함수 호출로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-186">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="0bb03-187">중첩 식은 다음과 같은 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-187">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="0bb03-188">위의 코드에서 `Run` 및 `Delay`에 대 한 호출은 계산 식 작성기 클래스에서 정의 되지 않은 경우 생략 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-188">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="0bb03-189">여기서는 `{| cexpr |}`로 표시 되는 계산 식의 본문은 다음 표에 설명 된 번역에 의해 작성기 클래스의 메서드와 관련 된 호출로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-189">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="0bb03-190">계산 식 `{| cexpr |}`은 이러한 번역에 따라 재귀적으로 정의 됩니다. 여기서 `expr` F# 은 식이고`cexpr`는 계산 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-190">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="0bb03-191">식</span><span class="sxs-lookup"><span data-stu-id="0bb03-191">Expression</span></span>|<span data-ttu-id="0bb03-192">변환</span><span class="sxs-lookup"><span data-stu-id="0bb03-192">Translation</span></span>|
|----------|-----------|
|<code>{ let binding in cexpr }</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{ let! pattern = expr in cexpr }</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ do! expr in cexpr }</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{ yield expr }</code>|`builder.Yield(expr)`|
|<code>{ yield! expr }</code>|`builder.YieldFrom(expr)`|
|<code>{ return expr }</code>|`builder.Return(expr)`|
|<code>{ return! expr }</code>|`builder.ReturnFrom(expr)`|
|<code>{ use pattern = expr in cexpr }</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ use! value = expr in cexpr }</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> { cexpr }))))</code>|
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else binder.Zero()</code>|
|<code>{ if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then { cexpr0 } else { cexpr1 }</code>|
|<code>{ match expr with &#124; pattern_i -> cexpr_i }</code>|<code>match expr with &#124; pattern_i -> { cexpr_i }</code>|
|<code>{ for pattern in expr do cexpr }</code>|<code>builder.For(enumeration, (fun pattern -> { cexpr }))</code>|
|<code>{ for identifier = expr1 to expr2 do cexpr }</code>|<code>builder.For(enumeration, (fun identifier -> { cexpr }))</code>|
|<code>{ while expr do cexpr }</code>|<code>builder.While(fun () -> expr, builder.Delay({ cexpr }))</code>|
|<code>{ try cexpr with &#124; pattern_i -> expr_i }</code>|<code>builder.TryWith(builder.Delay({ cexpr }), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{ try cexpr finally expr }</code>|<code>builder.TryFinally(builder.Delay( { cexpr }), (fun () -> expr))</code>|
|<code>{ cexpr1; cexpr2 }</code>|<code>builder.Combine({ cexpr1 }, { cexpr2 })</code>|
|<code>{ other-expr; cexpr }</code>|<code>expr; { cexpr }</code>|
|<code>{ other-expr }</code>|`expr; builder.Zero()`|

<span data-ttu-id="0bb03-193">위의 표에서는 `other-expr` 표에 나열 되지 않은 식에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-193">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="0bb03-194">작성기 클래스는 모든 메서드를 구현할 필요가 없으며 앞의 표에 나열 된 모든 번역을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-194">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="0bb03-195">구현 되지 않은 구문은 해당 형식의 계산 식에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-195">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="0bb03-196">예를 들어 계산 식에서 `use` 키워드를 지원 하지 않으려면 작성기 클래스에서 `Use` 정의를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-196">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="0bb03-197">다음 코드 예제에서는 한 번에 하나의 단계를 평가할 수 있는 일련의 단계로 계산을 캡슐화 하는 계산 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-197">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="0bb03-198">구분 된 공용 구조체 형식인 `OkOrException`는 지금까지 계산 된 식의 오류 상태를 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-198">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="0bb03-199">이 코드에서는 몇 가지 일반적인 패턴을 보여 줍니다. 몇 가지 일반적인 패턴은 몇 가지 작성기 메서드의 상용구 구현과 같이 계산 식에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-199">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

```fsharp
// Computations that can be run step by step
type Eventually<'T> =
    | Done of 'T
    | NotYetDone of (unit -> Eventually<'T>)

module Eventually =
    // The bind for the computations. Append 'func' to the
    // computation.
    let rec bind func expr =
        match expr with
        | Done value -> func value
        | NotYetDone work -> NotYetDone (fun () -> bind func (work()))

    // Return the final value wrapped in the Eventually type.
    let result value = Done value

    type OkOrException<'T> =
        | Ok of 'T
        | Exception of System.Exception

    // The catch for the computations. Stitch try/with throughout
    // the computation, and return the overall result as an OkOrException.
    let rec catch expr =
        match expr with
        | Done value -> result (Ok value)
        | NotYetDone work ->
            NotYetDone (fun () ->
                let res = try Ok(work()) with | exn -> Exception exn
                match res with
                | Ok cont -> catch cont // note, a tailcall
                | Exception exn -> result (Exception exn))

    // The delay operator.
    let delay func = NotYetDone (fun () -> func())

    // The stepping action for the computations.
    let step expr =
        match expr with
        | Done _ -> expr
        | NotYetDone func -> func ()

    // The rest of the operations are boilerplate.
    // The tryFinally operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryFinally expr compensation =
        catch (expr)
        |> bind (fun res -> 
            compensation();
            match res with
            | Ok value -> result value
            | Exception exn -> raise exn)

    // The tryWith operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryWith exn handler =
        catch exn
        |> bind (function Ok value -> result value | Exception exn -> handler exn)

    // The whileLoop operator.
    // This is boilerplate in terms of "result" and "bind".
    let rec whileLoop pred body =
        if pred() then body |> bind (fun _ -> whileLoop pred body)
        else result ()

    // The sequential composition operator.
    // This is boilerplate in terms of "result" and "bind".
    let combine expr1 expr2 =
        expr1 |> bind (fun () -> expr2)

    // The using operator.
    let using (resource: #System.IDisposable) func =
        tryFinally (func resource) (fun () -> resource.Dispose())

    // The forLoop operator.
    // This is boilerplate in terms of "catch", "result", and "bind".
    let forLoop (collection:seq<_>) func =
        let ie = collection.GetEnumerator()
        tryFinally 
            (whileLoop 
                (fun () -> ie.MoveNext()) 
                (delay (fun () -> let value = ie.Current in func value)))
            (fun () -> ie.Dispose())

// The builder class.
type EventuallyBuilder() =
    member x.Bind(comp, func) = Eventually.bind func comp
    member x.Return(value) = Eventually.result value
    member x.ReturnFrom(value) = value
    member x.Combine(expr1, expr2) = Eventually.combine expr1 expr2
    member x.Delay(func) = Eventually.delay func
    member x.Zero() = Eventually.result ()
    member x.TryWith(expr, handler) = Eventually.tryWith expr handler
    member x.TryFinally(expr, compensation) = Eventually.tryFinally expr compensation
    member x.For(coll:seq<_>, func) = Eventually.forLoop coll func
    member x.Using(resource, expr) = Eventually.using resource expr

let eventually = new EventuallyBuilder()

let comp = eventually {
    for x in 1..2 do
        printfn " x = %d" x
    return 3 + 4 }

// Try the remaining lines in F# interactive to see how this
// computation expression works in practice.
let step x = Eventually.step x

// returns "NotYetDone <closure>"
comp |> step

// prints "x = 1"
// returns "NotYetDone <closure>"
comp |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step 
```

<span data-ttu-id="0bb03-200">계산 식에는 식이 반환 하는 기본 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-200">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="0bb03-201">기본 형식은 계산 된 결과 또는 수행 될 수 있는 지연 계산을 나타내거나 일부 형식의 컬렉션을 반복 하는 방법을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-201">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="0bb03-202">이전 예제에서는 기본 형식이 **결국**였습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-202">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="0bb03-203">시퀀스 식의 경우 기본 형식은 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-203">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0bb03-204">쿼리 식의 경우 기본 형식은 <xref:System.Linq.IQueryable?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-204">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0bb03-205">비동기 워크플로의 경우 기본 형식은 [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-205">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="0bb03-206">`Async` 개체는 결과를 계산 하기 위해 수행할 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-206">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="0bb03-207">예를 들어 [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) 를 호출 하 여 계산을 실행 하 고 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-207">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="0bb03-208">사용자 지정 작업</span><span class="sxs-lookup"><span data-stu-id="0bb03-208">Custom Operations</span></span>

<span data-ttu-id="0bb03-209">계산 식에 대 한 사용자 지정 작업을 정의 하 고 계산 식에서 사용자 지정 작업을 연산자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-209">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="0bb03-210">예를 들어 쿼리 식에 쿼리 연산자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-210">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="0bb03-211">사용자 지정 작업을 정의 하는 경우 계산 식의 메서드에 Yield 및를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-211">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="0bb03-212">사용자 지정 작업을 정의 하려면 계산 식의 작성기 클래스에 배치한 다음 [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-212">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="0bb03-213">이 특성은 사용자 지정 작업에 사용 되는 이름인 문자열을 인수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-213">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="0bb03-214">이 이름은 계산 식의 여는 중괄호의 시작 부분에서 범위에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-214">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="0bb03-215">따라서이 블록에서 사용자 지정 작업과 이름이 같은 식별자를 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-215">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="0bb03-216">예를 들어 `all`와 같은 식별자 또는 쿼리 식의 `last`를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-216">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="0bb03-217">새 사용자 지정 작업으로 기존 작성기 확장</span><span class="sxs-lookup"><span data-stu-id="0bb03-217">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="0bb03-218">작성기 클래스가 이미 있는 경우이 작성기 클래스 외부에서 해당 사용자 지정 작업을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-218">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="0bb03-219">모듈에서 확장을 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-219">Extensions must be declared in modules.</span></span> <span data-ttu-id="0bb03-220">네임 스페이스는 동일한 파일 및 형식이 정의 된 동일한 네임 스페이스 선언 그룹을 제외 하 고 확장 멤버를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-220">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="0bb03-221">다음 예제에서는 기존 `Microsoft.FSharp.Linq.QueryBuilder` 클래스의 확장을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bb03-221">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="0bb03-222">참조</span><span class="sxs-lookup"><span data-stu-id="0bb03-222">See also</span></span>

- [<span data-ttu-id="0bb03-223">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="0bb03-223">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0bb03-224">비동기 워크플로</span><span class="sxs-lookup"><span data-stu-id="0bb03-224">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="0bb03-225">시퀀스</span><span class="sxs-lookup"><span data-stu-id="0bb03-225">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="0bb03-226">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="0bb03-226">Query Expressions</span></span>](query-expressions.md)
