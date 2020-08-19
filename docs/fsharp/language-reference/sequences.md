---
title: 시퀀스
description: '데이터의 순서가 지정 된 컬렉션이 크고 모든 요소를 사용할 필요가 없는 경우 F # 시퀀스를 사용 하는 방법에 대해 알아봅니다.'
ms.date: 08/13/2020
ms.openlocfilehash: c84e0aebcc79a595c0ae3b9075648fb629bdd65c
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559039"
---
# <a name="sequences"></a><span data-ttu-id="c4e41-103">시퀀스</span><span class="sxs-lookup"><span data-stu-id="c4e41-103">Sequences</span></span>

<span data-ttu-id="c4e41-104">*시퀀스* 는 단일 형식의 논리적 일련의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-104">A *sequence* is a logical series of elements all of one type.</span></span> <span data-ttu-id="c4e41-105">시퀀스는 광범위 하 고 정렬 된 데이터 컬렉션이 있지만 모든 요소를 반드시 사용할 필요는 없는 경우에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-105">Sequences are particularly useful when you have a large, ordered collection of data but do not necessarily expect to use all of the elements.</span></span> <span data-ttu-id="c4e41-106">개별 시퀀스 요소는 필요에 따라 계산 되므로 모든 요소가 사용 되지 않는 상황에서 시퀀스는 목록 보다 더 나은 성능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-106">Individual sequence elements are computed only as required, so a sequence can provide better performance than a list in situations in which not all the elements are used.</span></span> <span data-ttu-id="c4e41-107">시퀀스는 `seq<'T>` 의 별칭인 형식으로 표현 됩니다 <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="c4e41-107">Sequences are represented by the `seq<'T>` type, which is an alias for <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="c4e41-108">따라서 인터페이스를 구현 하는 모든 .NET 형식을 <xref:System.Collections.Generic.IEnumerable%601> 시퀀스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-108">Therefore, any .NET type that implements <xref:System.Collections.Generic.IEnumerable%601> interface can be used as a sequence.</span></span> <span data-ttu-id="c4e41-109">[Seq 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html) 은 시퀀스와 관련 된 조작을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-109">The [Seq module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html) provides support for manipulations involving sequences.</span></span>

## <a name="sequence-expressions"></a><span data-ttu-id="c4e41-110">시퀀스 식</span><span class="sxs-lookup"><span data-stu-id="c4e41-110">Sequence Expressions</span></span>

<span data-ttu-id="c4e41-111">*시퀀스 식은* 시퀀스로 계산 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-111">A *sequence expression* is an expression that evaluates to a sequence.</span></span> <span data-ttu-id="c4e41-112">시퀀스 식은 많은 폼을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-112">Sequence expressions can take a number of forms.</span></span> <span data-ttu-id="c4e41-113">가장 간단한 형태는 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-113">The simplest form specifies a range.</span></span> <span data-ttu-id="c4e41-114">예를 `seq { 1 .. 5 }` 들어는 끝점 1과 5를 포함 하 여 다섯 개의 요소를 포함 하는 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-114">For example, `seq { 1 .. 5 }` creates a sequence that contains five elements, including the endpoints 1 and 5.</span></span> <span data-ttu-id="c4e41-115">두 개의 double 기간 사이에 증가 (또는 감소)를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-115">You can also specify an increment (or decrement) between two double periods.</span></span> <span data-ttu-id="c4e41-116">예를 들어 다음 코드는 10의 배수로 이루어진 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-116">For example, the following code creates the sequence of multiples of 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

<span data-ttu-id="c4e41-117">시퀀스 식은 시퀀스의 값을 생성 하는 F # 식으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-117">Sequence expressions are made up of F# expressions that produce values of the sequence.</span></span> <span data-ttu-id="c4e41-118">값을 프로그래밍 방식으로 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-118">You can also generate values programmatically:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

<span data-ttu-id="c4e41-119">이전 예제에서는 연산자를 사용 하 여 해당 `->` 값이 시퀀스의 일부가 될 식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-119">The previous sample uses the `->` operator, which allows you to specify an expression whose value will become a part of the sequence.</span></span> <span data-ttu-id="c4e41-120">`->`뒤에 오는 코드의 모든 부분에서 값을 반환 하는 경우에만를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-120">You can only use `->` if every part of the code that follows it returns a value.</span></span>

<span data-ttu-id="c4e41-121">또는 키워드를 지정 하 고 다음과 같은 옵션을 지정할 수 있습니다 `do` `yield` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-121">Alternatively, you can specify the `do` keyword, with an optional `yield` that follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

<span data-ttu-id="c4e41-122">다음 코드에서는 표를 나타내는 배열에 대 한 인덱스와 함께 좌표 쌍의 목록을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-122">The following code generates a list of coordinate pairs along with an index into an array that represents the grid.</span></span> <span data-ttu-id="c4e41-123">첫 번째 식에는를 `for` `do` 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-123">Note that the first `for` expression requires a `do` to be specified.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

<span data-ttu-id="c4e41-124">`if`시퀀스에 사용 되는 식은 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-124">An `if` expression used in a sequence is a filter.</span></span> <span data-ttu-id="c4e41-125">예를 들어, 형식이 인 함수를 포함 하 고 있다고 가정 하 고 소수 숫자만 포함 하는 시퀀스를 생성 하려면 `isprime` `int -> bool` 다음과 같이 시퀀스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-125">For example, to generate a sequence of only prime numbers, assuming that you have a function `isprime` of type `int -> bool`, construct the sequence as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

<span data-ttu-id="c4e41-126">앞에서 설명한 것 처럼 `do` `else` 와 함께 이동 하는 분기가 없기 때문에이 필요 `if` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-126">As mentioned previously, `do` is required here because there is no `else` branch that goes with the `if`.</span></span> <span data-ttu-id="c4e41-127">를 사용 하려고 하면 `->` 모든 분기에서 값을 반환 하지 않는다는 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-127">If you try to use `->`, you'll get an error saying that not all branches return a value.</span></span>

## <a name="the-yield-keyword"></a><span data-ttu-id="c4e41-128">`yield!` 키워드</span><span class="sxs-lookup"><span data-stu-id="c4e41-128">The `yield!` keyword</span></span>

<span data-ttu-id="c4e41-129">경우에 따라 요소의 시퀀스를 다른 시퀀스에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-129">Sometimes, you may wish to include a sequence of elements into another sequence.</span></span> <span data-ttu-id="c4e41-130">시퀀스를 다른 시퀀스 내에 포함 하려면 키워드를 사용 해야 합니다 `yield!` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-130">To include a sequence within another sequence, you'll need to use the `yield!` keyword:</span></span>

```fsharp
// Repeats '1 2 3 4 5' ten times
seq {
    for _ in 1..10 do
        yield! seq { 1; 2; 3; 4; 5}
}
```

<span data-ttu-id="c4e41-131">를 고려 하는 또 다른 방법은 `yield!` 내부 시퀀스를 평면화 한 다음 포함 하는 시퀀스에이를 포함 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-131">Another way of thinking of `yield!` is that it flattens an inner sequence and then includes that in the containing sequence.</span></span>

<span data-ttu-id="c4e41-132">`yield!`식에를 사용 하는 경우 다른 모든 단일 값은 키워드를 사용 해야 합니다 `yield` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-132">When `yield!` is used in an expression, all other single values must use the `yield` keyword:</span></span>

```fsharp
// Combine repeated values with their values
seq {
    for x in 1..10 do
        yield x
        yield! seq { for i in 1..x -> i}
}
```

<span data-ttu-id="c4e41-133">이전 예에서는의 값 `x` 을 각각에 대해에서로 생성 합니다 `1` `x` `x` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-133">The previous example will produce the value of `x` in addition to all values from `1` to `x` for each `x`.</span></span>

## <a name="examples"></a><span data-ttu-id="c4e41-134">예제</span><span class="sxs-lookup"><span data-stu-id="c4e41-134">Examples</span></span>

<span data-ttu-id="c4e41-135">첫 번째 예에서는 반복, 필터 및 양보를 포함 하는 시퀀스 식을 사용 하 여 배열을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-135">The first example uses a sequence expression that contains an iteration, a filter, and a yield to generate an array.</span></span> <span data-ttu-id="c4e41-136">이 코드는 1에서 100 사이의 일련 번호 시퀀스를 콘솔에 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-136">This code prints a sequence of prime numbers between 1 and 100 to the console.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

<span data-ttu-id="c4e41-137">다음 예에서는 두 개의 요소로 구성 된 튜플로 구성 된 곱하기 테이블을 만듭니다. 각 요소는 두 개의 요소와 제품으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-137">The following example creates a multiplication table that consists of tuples of three elements, each consisting of two factors and the product:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

<span data-ttu-id="c4e41-138">다음 예제에서는를 사용 하 여 `yield!` 개별 시퀀스를 단일 최종 시퀀스로 결합 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-138">The following example demonstrates the use of `yield!` to combine individual sequences into a single final sequence.</span></span> <span data-ttu-id="c4e41-139">이 경우 이진 트리의 각 하위 트리에 대 한 시퀀스는 재귀적 함수에서 연결 되어 최종 시퀀스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-139">In this case, the sequences for each subtree in a binary tree are concatenated in a recursive function to produce the final sequence.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a><span data-ttu-id="c4e41-140">시퀀스 사용</span><span class="sxs-lookup"><span data-stu-id="c4e41-140">Using Sequences</span></span>

<span data-ttu-id="c4e41-141">시퀀스는 [목록과](lists.md)동일한 많은 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-141">Sequences support many of the same functions as [lists](lists.md).</span></span> <span data-ttu-id="c4e41-142">시퀀스는 키 생성 함수를 사용 하 여 그룹화 및 계산 등의 작업도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-142">Sequences also support operations such as grouping and counting by using key-generating functions.</span></span> <span data-ttu-id="c4e41-143">시퀀스는 버킷이라고을 추출 하는 더 다양 한 함수도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-143">Sequences also support more diverse functions for extracting subsequences.</span></span>

<span data-ttu-id="c4e41-144">목록, 배열, 집합 및 맵과 같은 많은 데이터 형식은 열거 가능한 컬렉션 이므로 암시적으로 시퀀스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-144">Many data types, such as lists, arrays, sets, and maps are implicitly sequences because they are enumerable collections.</span></span> <span data-ttu-id="c4e41-145">시퀀스를 인수로 사용 하는 함수는을 구현 하는 .NET 데이터 형식 외에도 일반적인 F # 데이터 형식과 함께 사용할 수 `System.Collections.Generic.IEnumerable<'T>` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-145">A function that takes a sequence as an argument works with any of the common F# data types, in addition to any .NET data type that implements `System.Collections.Generic.IEnumerable<'T>`.</span></span> <span data-ttu-id="c4e41-146">목록을 인수로 사용 하는 함수와 대조 하 여 목록만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-146">Contrast this to a function that takes a list as an argument, which can only take lists.</span></span> <span data-ttu-id="c4e41-147">형식은 `seq<'T>` 에 대 한 형식 약어입니다 `IEnumerable<'T>` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-147">The type `seq<'T>` is a type abbreviation for `IEnumerable<'T>`.</span></span> <span data-ttu-id="c4e41-148">즉, `System.Collections.Generic.IEnumerable<'T>` F #의 배열, 목록, 집합 및 맵을 포함 하는 제네릭을 구현 하는 모든 형식 및 대부분의 .net 컬렉션 형식은 형식과 호환 되며 `seq` 시퀀스가 필요한 모든 곳에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-148">This means that any type that implements the generic `System.Collections.Generic.IEnumerable<'T>`, which includes arrays, lists, sets, and maps in F#, and also most .NET collection types, is compatible with the `seq` type and can be used wherever a sequence is expected.</span></span>

## <a name="module-functions"></a><span data-ttu-id="c4e41-149">모듈 함수</span><span class="sxs-lookup"><span data-stu-id="c4e41-149">Module Functions</span></span>

<span data-ttu-id="c4e41-150">[Fsharp.core 네임 스페이스](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections.html) 의 [Seq 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html) 에는 시퀀스 작업을 위한 함수가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-150">The [Seq module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html) in the [FSharp.Collections namespace](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections.html) contains functions for working with sequences.</span></span> <span data-ttu-id="c4e41-151">이러한 함수는 모두 열거 가능 하므로 시퀀스로 처리 될 수 있기 때문에 목록, 배열, 맵 및 집합 에서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-151">These functions work with lists, arrays, maps, and sets as well, because all of those types are enumerable, and therefore can be treated as sequences.</span></span>

## <a name="creating-sequences"></a><span data-ttu-id="c4e41-152">시퀀스 만들기</span><span class="sxs-lookup"><span data-stu-id="c4e41-152">Creating Sequences</span></span>

<span data-ttu-id="c4e41-153">앞에서 설명한 대로 시퀀스 식을 사용 하거나 특정 함수를 사용 하 여 시퀀스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-153">You can create sequences by using sequence expressions, as described previously, or by using certain functions.</span></span>

<span data-ttu-id="c4e41-154">[Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#empty)를 사용 하 여 빈 시퀀스를 만들거나 [seq. singleton](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#singleton)을 사용 하 여 지정 된 요소의 시퀀스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-154">You can create an empty sequence by using [Seq.empty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#empty), or you can create a sequence of just one specified element by using [Seq.singleton](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#singleton).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet9.fs)]

<span data-ttu-id="c4e41-155">[Seq.init](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#init) 를 사용 하 여 사용자가 제공 하는 함수를 사용 하 여 요소가 생성 되는 시퀀스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-155">You can use [Seq.init](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#init) to create a sequence for which the elements are created by using a function that you provide.</span></span> <span data-ttu-id="c4e41-156">또한 시퀀스의 크기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-156">You also provide a size for the sequence.</span></span> <span data-ttu-id="c4e41-157">이 함수는 시퀀스를 반복할 때까지 요소가 생성 되지 않는다는 점을 제외 하 고는 [List.init](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#init)와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-157">This function is just like [List.init](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#init), except that the elements are not created until you iterate through the sequence.</span></span> <span data-ttu-id="c4e41-158">다음 코드에서는를 사용 하는 방법을 보여 줍니다 `Seq.init` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-158">The following code illustrates the use of `Seq.init`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet10.fs)]

<span data-ttu-id="c4e41-159">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-159">The output is</span></span>

```console
0 10 20 30 40
```

<span data-ttu-id="c4e41-160">[Seq.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#ofArray) [&#60;&#62; 함수](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#ofList)를 사용 하 여 배열 및 목록에서 시퀀스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-160">By using [Seq.ofArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#ofArray) and [Seq.ofList&#60;'T&#62; Function](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#ofList), you can create sequences from arrays and lists.</span></span> <span data-ttu-id="c4e41-161">그러나 캐스트 연산자를 사용 하 여 배열 및 목록을 시퀀스로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-161">However, you can also convert arrays and lists to sequences by using a cast operator.</span></span> <span data-ttu-id="c4e41-162">다음 코드에서는 두 가지 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-162">Both techniques are shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet11.fs)]

<span data-ttu-id="c4e41-163">[Seq. 캐스트](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#cast)를 사용 하 여에 정의 된 것과 같은 약하게 형식화 된 컬렉션에서 시퀀스를 만들 수 있습니다 `System.Collections` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-163">By using [Seq.cast](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#cast), you can create a sequence from a weakly typed collection, such as those defined in `System.Collections`.</span></span> <span data-ttu-id="c4e41-164">이러한 약하게 형식화 된 컬렉션은 요소 형식을 가지 `System.Object` 며 제네릭이 아닌 형식을 사용 하 여 열거 됩니다 `System.Collections.Generic.IEnumerable&#96;1` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-164">Such weakly typed collections have the element type `System.Object` and are enumerated by using the non-generic `System.Collections.Generic.IEnumerable&#96;1` type.</span></span> <span data-ttu-id="c4e41-165">다음 코드에서는를 사용 하 여를 `Seq.cast` 시퀀스로 변환 하는 방법을 보여 줍니다 `System.Collections.ArrayList` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-165">The following code illustrates the use of `Seq.cast` to convert an `System.Collections.ArrayList` into a sequence.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet12.fs)]

<span data-ttu-id="c4e41-166">[Seq.initInfinite](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#initInfinite) 함수를 사용 하 여 무한 시퀀스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-166">You can define infinite sequences by using the [Seq.initInfinite](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#initInfinite) function.</span></span> <span data-ttu-id="c4e41-167">이러한 시퀀스의 경우 요소의 인덱스에서 각 요소를 생성 하는 함수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-167">For such a sequence, you provide a function that generates each element from the index of the element.</span></span> <span data-ttu-id="c4e41-168">지연 계산으로 인해 무한 시퀀스를 사용할 수 있습니다. 요소는 지정 된 함수를 호출 하 여 필요에 따라 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-168">Infinite sequences are possible because of lazy evaluation; elements are created as needed by calling the function that you specify.</span></span> <span data-ttu-id="c4e41-169">다음 코드 예제에서는 부동 소수점 숫자의 무한 시퀀스를 생성 합니다 .이 경우 연속 되는 정수의 사각형 reciprocals 교대로 반복 되는 연속 된 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-169">The following code example produces an infinite sequence of floating point numbers, in this case the alternating series of reciprocals of squares of successive integers.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet13.fs)]

<span data-ttu-id="c4e41-170">[펼침](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#unfold) 는 상태를 사용 하는 계산 함수에서 시퀀스를 생성 하 고 시퀀스의 각 후속 요소를 생성 하도록 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-170">[Seq.unfold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#unfold) generates a sequence from a computation function that takes a state and transforms it to produce each subsequent element in the sequence.</span></span> <span data-ttu-id="c4e41-171">상태는 각 요소를 계산 하는 데 사용 되는 값 이며 각 요소가 계산 될 때 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-171">The state is just a value that is used to compute each element, and can change as each element is computed.</span></span> <span data-ttu-id="c4e41-172">에 대 한 두 번째 인수는 `Seq.unfold` 시퀀스를 시작 하는 데 사용 되는 초기 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-172">The second argument to `Seq.unfold` is the initial value that is used to start the sequence.</span></span> <span data-ttu-id="c4e41-173">`Seq.unfold` 는 상태에 대해 옵션 유형을 사용 합니다 .이를 통해 값을 반환 하 여 시퀀스를 종료할 수 있습니다 `None` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-173">`Seq.unfold` uses an option type for the state, which enables you to terminate the sequence by returning the `None` value.</span></span> <span data-ttu-id="c4e41-174">다음 코드에서는 `seq1` 작업에 의해 생성 되는 및 시퀀스의 두 가지 예를 보여 줍니다 `fib` `unfold` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-174">The following code shows two examples of sequences, `seq1` and `fib`, that are generated by an `unfold` operation.</span></span> <span data-ttu-id="c4e41-175">첫 번째는 `seq1` 숫자를 20 개까지 포함 하는 간단한 시퀀스 일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-175">The first, `seq1`, is just a simple sequence with numbers up to 20.</span></span> <span data-ttu-id="c4e41-176">두 번째는를 사용 하 여 `fib` `unfold` 피보나치 시퀀스를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-176">The second, `fib`, uses `unfold` to compute the Fibonacci sequence.</span></span> <span data-ttu-id="c4e41-177">피보나치 시퀀스의 각 요소는 이전의 두 피보나치 번호의 합계 이므로 상태 값은 시퀀스의 이전 두 숫자로 구성 된 튜플입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-177">Because each element in the Fibonacci sequence is the sum of the previous two Fibonacci numbers, the state value is a tuple that consists of the previous two numbers in the sequence.</span></span> <span data-ttu-id="c4e41-178">초기 값은 `(1,1)` 시퀀스에서 처음 두 개의 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-178">The initial value is `(1,1)`, the first two numbers in the sequence.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet14.fs)]

<span data-ttu-id="c4e41-179">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-179">The output is as follows:</span></span>

```console
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

<span data-ttu-id="c4e41-180">다음 코드는 무한 시퀀스의 값을 생성 하 고 계산 하기 위해 여기에 설명 된 다양 한 시퀀스 모듈 함수를 사용 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-180">The following code is an example that uses many of the sequence module functions described here to generate and compute the values of infinite sequences.</span></span> <span data-ttu-id="c4e41-181">코드를 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-181">The code might take a few minutes to run.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a><span data-ttu-id="c4e41-182">요소 검색 및 찾기</span><span class="sxs-lookup"><span data-stu-id="c4e41-182">Searching and Finding Elements</span></span>

<span data-ttu-id="c4e41-183">시퀀스는 다음과 같은 목록에서 사용할 수 있는 기능을 지원 합니다. [seq. exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#exists), [array.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#exists), seq. [Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#find), [seq. findindex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#findIndex), [Seq. pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#pick), [seq. trfind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFind)및 [seq.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFindIndex)</span><span class="sxs-lookup"><span data-stu-id="c4e41-183">Sequences support functionality available with lists: [Seq.exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#exists), [Seq.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#exists), [Seq.find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#find), [Seq.findIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#findIndex), [Seq.pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#pick), [Seq.tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFind), and [Seq.tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFindIndex).</span></span> <span data-ttu-id="c4e41-184">시퀀스에 사용할 수 있는 이러한 함수 버전은 검색 되는 요소 까지만 시퀀스를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-184">The versions of these functions that are available for sequences evaluate the sequence only up to the element that is being searched for.</span></span> <span data-ttu-id="c4e41-185">예제는 [목록](lists.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4e41-185">For examples, see [Lists](lists.md).</span></span>

## <a name="obtaining-subsequences"></a><span data-ttu-id="c4e41-186">버킷이라고 가져오기</span><span class="sxs-lookup"><span data-stu-id="c4e41-186">Obtaining Subsequences</span></span>

<span data-ttu-id="c4e41-187">[Seq. 필터](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#filter) 및 [seq. 선택](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#choose) 은 시퀀스 요소가 평가 될 때까지 필터링 및 선택이 발생 하지 않는다는 점을 제외 하면 목록에 사용할 수 있는 해당 함수와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-187">[Seq.filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#filter) and [Seq.choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#choose) are like the corresponding functions that are available for lists, except that the filtering and choosing does not occur until the sequence elements are evaluated.</span></span>

<span data-ttu-id="c4e41-188">[Seq. truncate](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#truncate) 은 다른 시퀀스에서 시퀀스를 만들지만 시퀀스를 지정 된 수의 요소로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-188">[Seq.truncate](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#truncate) creates a sequence from another sequence, but limits the sequence to a specified number of elements.</span></span> <span data-ttu-id="c4e41-189">[Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#take) 는 시퀀스의 시작 부분부터 지정 된 수의 요소만 포함 하는 새 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-189">[Seq.take](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#take) creates a new sequence that contains only a specified number of elements from the start of a sequence.</span></span> <span data-ttu-id="c4e41-190">시퀀스에 지정 된 것 보다 더 많은 요소가 있으면에서을 `Seq.take` throw `System.InvalidOperationException` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-190">If there are fewer elements in the sequence than you specify to take, `Seq.take` throws a `System.InvalidOperationException`.</span></span> <span data-ttu-id="c4e41-191">와의 차이 `Seq.take` 는 `Seq.truncate` `Seq.truncate` 요소 수가 지정한 수보다 적으면에서 오류를 생성 하지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-191">The difference between `Seq.take` and `Seq.truncate` is that `Seq.truncate` does not produce an error if the number of elements is fewer than the number you specify.</span></span>

<span data-ttu-id="c4e41-192">다음 코드에서는 및의 동작과의 차이점을 보여 `Seq.truncate` 줍니다 `Seq.take` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-192">The following code shows the behavior of and differences between `Seq.truncate` and `Seq.take`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet16.fs)]

<span data-ttu-id="c4e41-193">오류가 발생 하기 전의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-193">The output, before the error occurs, is as follows.</span></span>

```console
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
```

<span data-ttu-id="c4e41-194">[TakeWhile](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#takeWhile)를 사용 하 여 조건자 함수 (부울 함수)를 지정 하 고 조건자가 인 원래 시퀀스의 요소로 구성 된 다른 시퀀스에서 시퀀스를 만든 다음 조건자가 반환 하는 `true` 첫 번째 요소 앞에서 중지할 수 있습니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-194">By using [Seq.takeWhile](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#takeWhile), you can specify a predicate function (a Boolean function) and create a sequence from another sequence made up of those elements of the original sequence for which the predicate is `true`, but stop before the first element for which the predicate returns `false`.</span></span> <span data-ttu-id="c4e41-195">[Seq. skip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#skip) 은 다른 시퀀스의 지정 된 수의 첫 번째 요소를 건너뛰고 나머지 요소를 반환 하는 시퀀스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-195">[Seq.skip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#skip) returns a sequence that skips a specified number of the first elements of another sequence and returns the remaining elements.</span></span> <span data-ttu-id="c4e41-196">[SkipWhile](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#skipWhile) 는 조건자가 반환 되는 한 다른 시퀀스의 첫 번째 요소를 건너뛴 `true` 다음 조건자가 반환 하는 첫 번째 요소부터 시작 하 여 나머지 요소를 반환 하는 시퀀스를 반환 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-196">[Seq.skipWhile](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#skipWhile) returns a sequence that skips the first elements of another sequence as long as the predicate returns `true`, and then returns the remaining elements, starting with the first element for which the predicate returns `false`.</span></span>

<span data-ttu-id="c4e41-197">다음 코드 예제에서는, 및의 차이점을 보여 줍니다 `Seq.takeWhile` `Seq.skip` `Seq.skipWhile` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-197">The following code example illustrates the behavior of and differences between `Seq.takeWhile`, `Seq.skip`, and `Seq.skipWhile`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet17.fs)]

<span data-ttu-id="c4e41-198">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-198">The output is as follows.</span></span>

```console
1 4 9
36 49 64 81 100
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a><span data-ttu-id="c4e41-199">시퀀스 변환</span><span class="sxs-lookup"><span data-stu-id="c4e41-199">Transforming Sequences</span></span>

<span data-ttu-id="c4e41-200">[Seq. 쌍](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#pairwise) 은 입력 시퀀스의 연속 요소가 튜플로 그룹화 되는 새 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-200">[Seq.pairwise](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#pairwise) creates a new sequence in which successive elements of the input sequence are grouped into tuples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet18.fs)]

<span data-ttu-id="c4e41-201">[Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#windowed) 는와 유사 합니다. `Seq.pairwise` 단, 튜플 시퀀스를 생성 하는 대신 시퀀스에서 인접 한 요소 ( *창*)의 복사본을 포함 하는 배열 시퀀스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-201">[Seq.windowed](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#windowed) is like `Seq.pairwise`, except that instead of producing a sequence of tuples, it produces a sequence of arrays that contain copies of adjacent elements (a *window*) from the sequence.</span></span> <span data-ttu-id="c4e41-202">각 배열에 원하는 인접 요소 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-202">You specify the number of adjacent elements you want in each array.</span></span>

<span data-ttu-id="c4e41-203">다음 코드 예제에서는 `Seq.windowed`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-203">The following code example demonstrates the use of `Seq.windowed`.</span></span> <span data-ttu-id="c4e41-204">이 경우 창의 요소 수는 3입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-204">In this case the number of elements in the window is 3.</span></span> <span data-ttu-id="c4e41-205">이 예제에서는 `printSeq` 앞의 코드 예제에서 정의 된를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-205">The example uses `printSeq`, which is defined in the previous code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet180.fs)]

<span data-ttu-id="c4e41-206">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-206">The output is as follows.</span></span>

<span data-ttu-id="c4e41-207">초기 시퀀스:</span><span class="sxs-lookup"><span data-stu-id="c4e41-207">Initial sequence:</span></span>

```console
1.0 1.5 2.0 1.5 1.0 1.5

Windows of length 3:
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|]

Moving average:
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a><span data-ttu-id="c4e41-208">여러 시퀀스를 사용 하는 작업</span><span class="sxs-lookup"><span data-stu-id="c4e41-208">Operations with Multiple Sequences</span></span>

<span data-ttu-id="c4e41-209">[Seq.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#zip) 및 [Seq.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#zip3) 은 두 개 또는 세 개의 시퀀스를 사용 하 고 튜플 시퀀스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-209">[Seq.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#zip) and [Seq.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#zip3) take two or three sequences and produce a sequence of tuples.</span></span> <span data-ttu-id="c4e41-210">이러한 함수는 [목록](lists.md)에 사용할 수 있는 해당 함수와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-210">These functions are like the corresponding functions available for [lists](lists.md).</span></span> <span data-ttu-id="c4e41-211">한 시퀀스를 두 개 이상의 시퀀스로 분리 하는 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-211">There is no corresponding functionality to separate one sequence into two or more sequences.</span></span> <span data-ttu-id="c4e41-212">시퀀스에이 기능이 필요한 경우 시퀀스를 목록으로 변환 하 고 [list. 압축 풀기](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-212">If you need this functionality for a sequence, convert the sequence to a list and use [List.unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip).</span></span>

## <a name="sorting-comparing-and-grouping"></a><span data-ttu-id="c4e41-213">정렬, 비교 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="c4e41-213">Sorting, Comparing, and Grouping</span></span>

<span data-ttu-id="c4e41-214">목록에 대해 지원 되는 정렬 함수도 시퀀스와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-214">The sorting functions supported for lists also work with sequences.</span></span> <span data-ttu-id="c4e41-215">여기에는 [seq. sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sort) 및 [sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sortBy)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-215">This includes [Seq.sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sort) and [Seq.sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sortBy).</span></span> <span data-ttu-id="c4e41-216">이러한 함수는 전체 시퀀스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-216">These functions iterate through the whole sequence.</span></span>

<span data-ttu-id="c4e41-217">[Seq. compareWith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#compareWith) 함수를 사용 하 여 두 시퀀스를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-217">You compare two sequences by using the [Seq.compareWith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#compareWith) function.</span></span> <span data-ttu-id="c4e41-218">함수는 연속 된 요소를 차례로 비교 하 고, 첫 번째 같지 않은 쌍을 발견할 경우 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-218">The function compares successive elements in turn, and stops when it encounters the first unequal pair.</span></span> <span data-ttu-id="c4e41-219">추가 요소는 비교에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-219">Any additional elements do not contribute to the comparison.</span></span>

<span data-ttu-id="c4e41-220">다음 코드는 `Seq.compareWith`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-220">The following code shows the use of `Seq.compareWith`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet19.fs)]

<span data-ttu-id="c4e41-221">위의 코드에서는 첫 번째 요소만 계산 및 검사 되 고 결과는-1입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-221">In the previous code, only the first element is computed and examined, and the result is -1.</span></span>

<span data-ttu-id="c4e41-222">[Seq.countby](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#countBy) 는 각 요소에 대 한 *키* 라는 값을 생성 하는 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-222">[Seq.countBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#countBy) takes a function that generates a value called a *key* for each element.</span></span> <span data-ttu-id="c4e41-223">각 요소에 대해이 함수를 호출 하 여 각 요소에 대 한 키를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-223">A key is generated for each element by calling this function on each element.</span></span> <span data-ttu-id="c4e41-224">`Seq.countBy` 그런 다음는 키 값을 포함 하는 시퀀스와 키의 각 값을 생성 한 요소 수의 개수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-224">`Seq.countBy` then returns a sequence that contains the key values, and a count of the number of elements that generated each value of the key.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet201.fs)]

<span data-ttu-id="c4e41-225">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-225">The output is as follows.</span></span>

```console
(1, 34) (2, 33) (0, 33)
```

<span data-ttu-id="c4e41-226">위의 출력은 키 1, 키 2를 생성 한 33 값 및 키 0을 생성 한 33 값을 생성 한 원래 시퀀스의 요소가 34 개 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-226">The previous output shows that there were 34 elements of the original sequence that produced the key 1, 33 values that produced the key 2, and 33 values that produced the key 0.</span></span>

<span data-ttu-id="c4e41-227">[Seq. groupBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#groupBy)를 호출 하 여 시퀀스의 요소를 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-227">You can group elements of a sequence by calling [Seq.groupBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#groupBy).</span></span> <span data-ttu-id="c4e41-228">`Seq.groupBy` 요소에서 키를 생성 하는 시퀀스 및 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-228">`Seq.groupBy` takes a sequence and a function that generates a key from an element.</span></span> <span data-ttu-id="c4e41-229">함수는 시퀀스의 각 요소에 대해 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-229">The function is executed on each element of the sequence.</span></span> <span data-ttu-id="c4e41-230">`Seq.groupBy` 각 튜플의 첫 번째 요소가 키이 고 두 번째 요소가 해당 키를 생성 하는 요소의 시퀀스인 경우 튜플 시퀀스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-230">`Seq.groupBy` returns a sequence of tuples, where the first element of each tuple is the key and the second is a sequence of elements that produce that key.</span></span>

<span data-ttu-id="c4e41-231">다음 코드 예제에서는를 사용 하 여 `Seq.groupBy` 1에서 100 사이의 숫자 시퀀스를 고유 키 값이 0, 1, 2 인 세 개의 그룹으로 분할 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-231">The following code example shows the use of `Seq.groupBy` to partition the sequence of numbers from 1 to 100 into three groups that have the distinct key values 0, 1, and 2.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet202.fs)]

<span data-ttu-id="c4e41-232">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-232">The output is as follows.</span></span>

```console
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

<span data-ttu-id="c4e41-233">[Seq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#distinct)를 호출 하 여 중복 요소를 제거 하는 시퀀스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-233">You can create a sequence that eliminates duplicate elements by calling [Seq.distinct](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#distinct).</span></span> <span data-ttu-id="c4e41-234">또는 각 요소에서 키 생성 함수를 호출 하는 [seq.distinctby](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#distinctBy)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-234">Or you can use [Seq.distinctBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#distinctBy), which takes a key-generating function to be called on each element.</span></span> <span data-ttu-id="c4e41-235">결과 시퀀스에는 고유 키가 있는 원래 시퀀스의 요소가 포함 됩니다. 이전 요소에 대 한 중복 키를 생성 하는 이후 요소는 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-235">The resulting sequence contains elements of the original sequence that have unique keys; later elements that produce a duplicate key to an earlier element are discarded.</span></span>

<span data-ttu-id="c4e41-236">다음 코드 예제에서는를 사용 하는 방법을 보여 줍니다 `Seq.distinct` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-236">The following code example illustrates the use of `Seq.distinct`.</span></span> <span data-ttu-id="c4e41-237">`Seq.distinct` 이진 숫자를 나타내는 시퀀스를 생성 한 다음 유일한 고유 요소만 0과 1 임을 보여 주는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-237">`Seq.distinct` is demonstrated by generating sequences that represent binary numbers, and then showing that the only distinct elements are 0 and 1.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet22.fs)]

<span data-ttu-id="c4e41-238">다음 코드에서는 `Seq.distinctBy` 음수 및 양수가 포함 된 시퀀스를 시작 하 고 절대 값 함수를 키 생성 함수로 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-238">The following code demonstrates `Seq.distinctBy` by starting with a sequence that contains negative and positive numbers and using the absolute value function as the key-generating function.</span></span> <span data-ttu-id="c4e41-239">음수는 시퀀스에서 앞에 표시 되 고 동일한 절대값 또는 키를 갖는 양수 대신 선택 되므로 시퀀스의 음수에 해당 하는 모든 양수가 결과 시퀀스에 누락 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-239">The resulting sequence is missing all the positive numbers that correspond to the negative numbers in the sequence, because the negative numbers appear earlier in the sequence and therefore are selected instead of the positive numbers that have the same absolute value, or key.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a><span data-ttu-id="c4e41-240">읽기 전용 및 캐시 된 시퀀스</span><span class="sxs-lookup"><span data-stu-id="c4e41-240">Readonly and Cached Sequences</span></span>

<span data-ttu-id="c4e41-241">[Seq. readonly](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#readonly) 는 시퀀스의 읽기 전용 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-241">[Seq.readonly](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#readonly) creates a read-only copy of a sequence.</span></span> <span data-ttu-id="c4e41-242">`Seq.readonly` 는 배열과 같은 읽기/쓰기 컬렉션이 있고 원래 컬렉션을 수정 하지 않으려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-242">`Seq.readonly` is useful when you have a read-write collection, such as an array, and you do not want to modify the original collection.</span></span> <span data-ttu-id="c4e41-243">이 함수는 데이터 캡슐화를 유지 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-243">This function can be used to preserve data encapsulation.</span></span> <span data-ttu-id="c4e41-244">다음 코드 예제에서는 배열을 포함 하는 형식이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-244">In the following code example, a type that contains an array is created.</span></span> <span data-ttu-id="c4e41-245">속성은 배열을 노출 하지만 배열을 반환 하는 대신를 사용 하 여 배열에서 만든 시퀀스를 반환 합니다 `Seq.readonly` .</span><span class="sxs-lookup"><span data-stu-id="c4e41-245">A property exposes the array, but instead of returning an array, it returns a sequence that is created from the array by using `Seq.readonly`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet24.fs)]

<span data-ttu-id="c4e41-246">[Seq. cache](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#cache) 는 시퀀스의 저장 된 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-246">[Seq.cache](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#cache) creates a stored version of a sequence.</span></span> <span data-ttu-id="c4e41-247">를 사용 `Seq.cache` 하 여 시퀀스의 재평가를 방지 하거나 시퀀스를 사용 하는 스레드가 여러 개 있는 경우 각 요소가 한 번만 처리 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-247">Use `Seq.cache` to avoid reevaluation of a sequence, or when you have multiple threads that use a sequence, but you must make sure that each element is acted upon only one time.</span></span> <span data-ttu-id="c4e41-248">여러 스레드에서 사용 되는 시퀀스를 사용 하는 경우 원래 시퀀스에 대 한 값을 열거 하 고 계산 하는 하나의 스레드를 사용 하 고 나머지 스레드는 캐시 된 시퀀스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-248">When you have a sequence that is being used by multiple threads, you can have one thread that enumerates and computes the values for the original sequence, and remaining threads can use the cached sequence.</span></span>

## <a name="performing-computations-on-sequences"></a><span data-ttu-id="c4e41-249">시퀀스에 대 한 계산 수행</span><span class="sxs-lookup"><span data-stu-id="c4e41-249">Performing Computations on Sequences</span></span>

<span data-ttu-id="c4e41-250">간단한 산술 연산은 [seq. average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#average), [seq. sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sum), [Array.averageby](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#averageBy), [seq. sumby](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sumBy)등의 목록에서와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-250">Simple arithmetic operations are like those of lists, such as [Seq.average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#average), [Seq.sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sum), [Seq.averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#averageBy), [Seq.sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#sumBy), and so on.</span></span>

<span data-ttu-id="c4e41-251">[Seq. 접기](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#fold), [seq. 감소](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#reduce)및 [seq. scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#scan) 은 목록에 사용할 수 있는 해당 함수와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-251">[Seq.fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#fold), [Seq.reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#reduce), and [Seq.scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#scan) are like the corresponding functions that are available for lists.</span></span> <span data-ttu-id="c4e41-252">시퀀스는 지원을 나열 하는 이러한 함수의 전체 변형 하위 집합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e41-252">Sequences support a subset of the full variations of these functions that lists support.</span></span> <span data-ttu-id="c4e41-253">자세한 내용 및 예제는 [목록](lists.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4e41-253">For more information and examples, see [Lists](lists.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4e41-254">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4e41-254">See also</span></span>

- [<span data-ttu-id="c4e41-255">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="c4e41-255">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="c4e41-256">F# 형식</span><span class="sxs-lookup"><span data-stu-id="c4e41-256">F# Types</span></span>](fsharp-types.md)
