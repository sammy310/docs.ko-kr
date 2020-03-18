---
title: 인덱스 및 범위를 사용하여 데이터 범위 탐색
description: 이 고급 자습서에서는 인덱스 및 범위를 사용하여 순차적 데이터 세트를 검사하는 데이터 탐색을 살펴봅니다.
ms.date: 03/11/2020
ms.technology: csharp-fundamentals
ms.custom: mvc
ms.openlocfilehash: 82aad968e2efc437c82a7c8250bcd108b60b09e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156496"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="26c79-103">인덱스 및 범위</span><span class="sxs-lookup"><span data-stu-id="26c79-103">Indices and ranges</span></span>

<span data-ttu-id="26c79-104">범위와 인덱스는 시퀀스의 단일 요소 또는 범위에 액세스하기 위한 간결한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in a sequence.</span></span>

<span data-ttu-id="26c79-105">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-105">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="26c79-106">시퀀스에서 범위에 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-106">Use the syntax for ranges in a sequence.</span></span>
> - <span data-ttu-id="26c79-107">각 시퀀스의 시작 및 끝에 대한 설계 의사 결정을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-107">Understand the design decisions for the start and end of each sequence.</span></span>
> - <span data-ttu-id="26c79-108"><xref:System.Index> 및 <xref:System.Range> 형식에 대한 시나리오를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-108">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="26c79-109">인덱스 및 범위에 대한 언어 지원</span><span class="sxs-lookup"><span data-stu-id="26c79-109">Language support for indices and ranges</span></span>

<span data-ttu-id="26c79-110">이 언어 지원은 다음과 같은 두 가지 새 형식 및 두 가지 새 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-110">This language support relies on two new types and two new operators:</span></span>

- <span data-ttu-id="26c79-111"><xref:System.Index?displayProperty=nameWithType>는 인덱스를 시퀀스로 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-111"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="26c79-112">인덱스가 시퀀스의 끝을 기준으로 하도록 지정하는 끝부터 인덱스 연산자 `^`입니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-112">The index from end operator `^`, which specifies that an index is relative to the end of a sequence.</span></span>
- <span data-ttu-id="26c79-113"><xref:System.Range?displayProperty=nameWithType>는 시퀀스의 하위 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-113"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="26c79-114">범위의 시작과 끝을 피연산자로 지정하는 범위 연산자 `..`입니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-114">The range operator `..`, which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="26c79-115">인덱스에 대한 규칙을 사용하여 시작하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-115">Let's start with the rules for indices.</span></span> <span data-ttu-id="26c79-116">`sequence`배열을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-116">Consider an array `sequence`.</span></span> <span data-ttu-id="26c79-117">`0` 인덱스는 `sequence[0]`과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-117">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="26c79-118">`^0` 인덱스는 `sequence[sequence.Length]`와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-118">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="26c79-119">`sequence[^0]` 식은 `sequence[sequence.Length]`처럼 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-119">The expression `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="26c79-120">`n`이 어떤 숫자이든, 인덱스 `^n`은 `sequence[sequence.Length - n]`과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-120">For any number `n`, the index `^n` is the same as `sequence[sequence.Length - n]`.</span></span>

```csharp
string[] words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

<span data-ttu-id="26c79-121">다음과 같이 `^1` 인덱스를 사용하여 마지막 단어를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-121">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="26c79-122">초기화 아래에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-122">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="26c79-123">한 범위는 어떤 범위의 *시작* 및 *끝*을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-123">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="26c79-124">여러 범위는 배타적입니다. 즉, ‘끝’이 범위에 포함되지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="26c79-124">Ranges are exclusive, meaning the *end* isn't included in the range.</span></span> <span data-ttu-id="26c79-125">`[0..sequence.Length]`가 전체 범위를 나타내는 것처럼 `[0..^0]` 범위는 전체 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-125">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span>

<span data-ttu-id="26c79-126">다음 코드는 “quick”, “brown”, “fox”라는 단어를 포함하는 하위 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-126">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="26c79-127">이 하위 범위에는 `words[1]`부터 `words[3]`까지 포함되며,</span><span class="sxs-lookup"><span data-stu-id="26c79-127">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="26c79-128">`words[4]` 요소가 범위에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-128">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="26c79-129">다음 코드를 같은 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-129">Add the following code to the same method.</span></span> <span data-ttu-id="26c79-130">대화형 창의 맨 아래에 다음 코드를 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-130">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="26c79-131">다음 코드는 “lazy”와 “dog”를 포함하는 하위 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-131">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="26c79-132">이 하위 범위에는 `words[^2]`과 `words[^1]`이 포함되며.</span><span class="sxs-lookup"><span data-stu-id="26c79-132">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="26c79-133">끝 인덱스 `words[^0]`는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-133">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="26c79-134">다음 코드도 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-134">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="26c79-135">다음 예제는 시작만, 끝만, 그리고 시작과 끝이 모두 열린 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-135">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="26c79-136">범위나 인덱스를 변수로 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-136">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="26c79-137">그러면 이 변수를 `[` 및 `]` 문자 사이에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-137">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="26c79-138">다음 샘플에서는 이러한 선택에 대한 여러 이유를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-138">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="26c79-139">`x`, `y` 및 `z`를 수정하여 다양한 조합을 시도해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-139">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="26c79-140">실험할 때는 올바른 조합을 위해 `x`가 `y`보다 작고 `y`가 `z`보다 작은 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-140">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="26c79-141">새 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-141">Add the following code in a new method.</span></span> <span data-ttu-id="26c79-142">다양한 조합을 시도해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-142">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="type-support-for-indices-and-ranges"></a><span data-ttu-id="26c79-143">인덱스 및 범위에 대한 형식 지원</span><span class="sxs-lookup"><span data-stu-id="26c79-143">Type support for indices and ranges</span></span>

<span data-ttu-id="26c79-144">인덱스 및 범위는 시퀀스에서 단일 요소 또는 요소의 하위 범위에 액세스하기 위한 명확하고 간결한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-144">Indexes and ranges provide clear, concise syntax to access a single element or a subrange of elements in a sequence.</span></span> <span data-ttu-id="26c79-145">인덱스 식은 일반적으로 시퀀스의 요소 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-145">An index expression typically returns the type of the elements of a sequence.</span></span> <span data-ttu-id="26c79-146">범위 식은 일반적으로 소스 시퀀스와 동일한 시퀀스 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-146">A range expression typically returns the same sequence type as the source sequence.</span></span>

<span data-ttu-id="26c79-147"><xref:System.Index> 또는 <xref:System.Range> 매개 변수를 사용하여 [인덱서](../programming-guide/indexers/index.md)를 제공하는 형식은 각각 인덱스 또는 범위를 명시적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-147">Any type that provides an [indexer](../programming-guide/indexers/index.md) with an <xref:System.Index> or <xref:System.Range> parameter explicitly supports indices or ranges respectively.</span></span> <span data-ttu-id="26c79-148">단일 <xref:System.Range> 매개 변수를 사용하는 인덱서는 다양한 시퀀스 형식(예: <xref:System.Span%601?displayProperty=nameWithType>)을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-148">An indexer that takes a single <xref:System.Range> parameter may return a different sequence type, such as <xref:System.Span%601?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="26c79-149">이름이 `Length` 또는 `Count`이고 액세스 가능한 getter 및 반환 형식 `int`를 갖는 속성이 있는 경우 형식은 **countable**입니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-149">A type is **countable** if it has a property named `Length` or `Count` with an accessible getter and a return type of `int`.</span></span> <span data-ttu-id="26c79-150">인덱스 또는 범위를 명시적으로 지원하지 않는 countable 형식은 해당 형식에 대한 암시적 지원을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-150">A countable type that doesn't explicitly support indices or ranges may provide an implicit support for them.</span></span> <span data-ttu-id="26c79-151">자세한 내용은 [기능 제한 참고](~/_csharplang/proposals/csharp-8.0/ranges.md)의 [암시적 인덱스 지원](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) 및 [암시적 범위 지원](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26c79-151">For more information, see the [Implicit Index support](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) and [Implicit Range support](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) sections of the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span> <span data-ttu-id="26c79-152">암시적 범위 지원을 사용하는 범위는 소스 시퀀스와 동일한 시퀀스 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-152">Ranges using implicit range support return the same sequence type as the source sequence.</span></span>

<span data-ttu-id="26c79-153">예를 들어, .NET 형식 <xref:System.String>, <xref:System.Span%601> 및 <xref:System.ReadOnlySpan%601>은 인덱스와 범위를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-153">For example, the following .NET types support both indices and ranges: <xref:System.String>, <xref:System.Span%601>, and <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="26c79-154"><xref:System.Collections.Generic.List%601>는 인덱스는 지원하고 범위는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-154">The <xref:System.Collections.Generic.List%601> supports indices but doesn't support ranges.</span></span>

<span data-ttu-id="26c79-155"><xref:System.Array>에는 좀 더 미묘한 동작이 더 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-155"><xref:System.Array> has more nuanced behavior.</span></span> <span data-ttu-id="26c79-156">1차원 배열은 인덱스와 범위를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-156">Single dimension arrays support both indices and ranges.</span></span> <span data-ttu-id="26c79-157">다차원 배열은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-157">Multi-dimensional arrays don't.</span></span> <span data-ttu-id="26c79-158">다차원 배열에 대한 인덱서에는 단일 매개 변수가 아닌 여러 개의 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-158">The indexer for a multi-dimensional array has multiple parameters, not a single parameter.</span></span> <span data-ttu-id="26c79-159">배열의 배열이라고도 하는 가변 배열은 범위와 인덱서를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-159">Jagged arrays, also referred to as an array of arrays, support both ranges and indexers.</span></span> <span data-ttu-id="26c79-160">다음 예에서는 가변 배열의 사각형 하위 섹션을 반복하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-160">The following example shows how to iterate a rectangular subsection of a jagged array.</span></span> <span data-ttu-id="26c79-161">첫 행과 마지막 3개 행을 제외하고, 선택된 각 행에서 첫 열과 마지막 2개 열을 제외하고 중앙의 섹션을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-161">It iterates the section in the center, excluding the first and last three rows, and the first and last two columns from each selected row:</span></span>

[!code-csharp[JaggedArrays](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_JaggedArrays)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="26c79-162">인덱스 및 범위에 대한 시나리오</span><span class="sxs-lookup"><span data-stu-id="26c79-162">Scenarios for indices and ranges</span></span>

<span data-ttu-id="26c79-163">더 큰 시퀀스의 하위 범위를 분석할 때 자주 범위와 인덱스를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-163">You'll often use ranges and indices when you want to analyze a subrange of a larger sequence.</span></span> <span data-ttu-id="26c79-164">새 구문에서는 어떤 하위 범위가 관련되었는지 더 명확히 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-164">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="26c79-165">로컬 함수 `MovingAverage`는 <xref:System.Range>를 인수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-165">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="26c79-166">그러면 메서드가 최솟값, 최댓값, 평균을 계산할 때 이 범위만 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-166">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="26c79-167">프로젝트에 다음 코드를 시도해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="26c79-167">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]
