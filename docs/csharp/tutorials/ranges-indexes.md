---
title: 인덱스 및 범위를 사용하여 데이터 범위 탐색
description: 이 고급 자습서에서는 인덱스 및 범위를 사용하여 순차적 데이터 세트를 검사하는 데이터 탐색을 살펴봅니다.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: 64fae4581e265d4f70b8356d5c651b4fdaca3fe9
ms.sourcegitcommit: dd3b897feb5c4ac39732bb165848e37a344b0765
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/25/2019
ms.locfileid: "64431494"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="8fab6-103">인덱스 및 범위</span><span class="sxs-lookup"><span data-stu-id="8fab6-103">Indices and ranges</span></span>

<span data-ttu-id="8fab6-104">범위와 인덱스는 배열, <xref:System.Array>, <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601>에서 단일 요소 또는 범위에 액세스하기 위한 간결한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in an <xref:System.Array>, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="8fab6-105">이러한 기능을 통해 더 간결하고 분명한 구문으로 시퀀스의 단일 요소 또는 요소 범위에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-105">These features enable more concise, clear syntax to access single elements or ranges of elements in a sequence.</span></span>

<span data-ttu-id="8fab6-106">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="8fab6-107">시퀀스에서 범위에 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-107">Use the syntax for ranges in a sequence.</span></span>
> * <span data-ttu-id="8fab6-108">각 시퀀스의 시작 및 끝에 대한 설계 의사 결정을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-108">Understand the design decisions for the start and end of each sequence.</span></span>
> * <span data-ttu-id="8fab6-109"><xref:System.Index> 및 <xref:System.Range> 형식에 대한 시나리오를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-109">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="8fab6-110">인덱스 및 범위에 대한 언어 지원</span><span class="sxs-lookup"><span data-stu-id="8fab6-110">Language support for indices and ranges</span></span>

<span data-ttu-id="8fab6-111">인덱스 앞에 `^` 문자를 사용하여 **끝에서부터** 인덱스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-111">You can specify an index **from the end** using the `^` character before the index.</span></span> <span data-ttu-id="8fab6-112">끝에서부터의 인덱스는 `0..^0`이 전체 범위를 지정하는 규칙에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-112">Indexing from the end starts from the rule that `0..^0` specifies the entire range.</span></span> <span data-ttu-id="8fab6-113">전체 배열을 열거하려면 *첫 번째 요소*에서 시작하고 *마지막 요소를 통과*할 때까지 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-113">To enumerate an entire array, you start *at the first element*, and continue until you are *past the last element*.</span></span> <span data-ttu-id="8fab6-114">열거자에서 `MoveNext` 메서드의 동작을 고려해 봅니다. 즉 열거형이 마지막 요소를 통과하면 False를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-114">Think of the behavior of the `MoveNext` method on an enumerator: it returns false when the enumeration passes the last element.</span></span> <span data-ttu-id="8fab6-115">인덱스 `^0`은 “끝”, `array[array.Length]` 또는 마지막 요소 뒤에 오는 인덱스를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-115">The index `^0` means "the end", `array[array.Length]`, or the index that follows the last element.</span></span> <span data-ttu-id="8fab6-116">`array[2]`가 “앞에서부터 2번째” 요소를 의미한다는 것은 이미 잘 알고 계실 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-116">You are familiar with `array[2]` meaning the element "2 from the start".</span></span> <span data-ttu-id="8fab6-117">`array[^2]`는 “뒤에서부터 2번째” 요소를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-117">Now, `array[^2]` means the element "2 from the end".</span></span> 

<span data-ttu-id="8fab6-118">**범위**는 **범위 연산자** `..`를 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-118">You can specify a **range** with the **range operator**: `..`.</span></span> <span data-ttu-id="8fab6-119">예를 들어, `0..^0`은 배열의 전체 범위를 지정하는데, 앞에서부터 인덱스 0에서 뒤에서부터 인덱스 1까지(즉, ^0 인덱스는 은 포함되지 않음)를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-119">For example, `0..^0` specifies the entire range of the array: 0 from the start up to, but not including 0 from the end.</span></span> <span data-ttu-id="8fab6-120">피연산자 둘 다 “앞에서부터” 또는 “뒤에서부터”를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-120">Either operand may use "from the start" or "from the end".</span></span> <span data-ttu-id="8fab6-121">피연산자 둘 다 생략하는 것도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-121">Furthermore, either operand may be omitted.</span></span> <span data-ttu-id="8fab6-122">시작 인덱스의 기본값은 `0`, 끝 인덱스의 기본값은 `^0`입니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-122">The defaults are `0` for the start index, and `^0` for the end index.</span></span>

```csharp-interactive
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

<span data-ttu-id="8fab6-123">각 요소의 인덱스는 “앞에서부터”라는 개념과 “뒤에서부터”라는 개념과 범위에는 해당 범위의 끝은 포함되지 않음을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-123">The index of each element reinforces the concept of "from the start", and "from the end", and that ranges are exclusive of the end of the range.</span></span> <span data-ttu-id="8fab6-124">전체 배열의 “시작”은 첫 번째 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-124">The "start" of the entire array is the first element.</span></span> <span data-ttu-id="8fab6-125">전체 배열의 “끝”은 마지막 요소의 “뒤”에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-125">The "end" of the entire array is *past* the last element.</span></span>

<span data-ttu-id="8fab6-126">다음과 같이 `^1` 인덱스를 사용하여 마지막 단어를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-126">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="8fab6-127">초기화 아래에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-127">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="8fab6-128">다음 코드는 “quick”, “brown”, “fox”라는 단어를 포함하는 하위 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-128">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="8fab6-129">이 하위 범위에는 `words[1]`부터 `words[3]`까지 포함되며,</span><span class="sxs-lookup"><span data-stu-id="8fab6-129">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="8fab6-130">`words[4]` 요소가 범위에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-130">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="8fab6-131">다음 코드를 같은 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-131">Add the following code to the same method.</span></span> <span data-ttu-id="8fab6-132">대화형 창의 맨 아래에 다음 코드를 복사하여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-132">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="8fab6-133">다음 코드는 “lazy”와 “dog”를 포함하는 하위 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-133">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="8fab6-134">이 하위 범위에는 `words[^2]`과 `words[^1]`이 포함되며.</span><span class="sxs-lookup"><span data-stu-id="8fab6-134">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="8fab6-135">끝 인덱스 `words[^0]`는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-135">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="8fab6-136">다음 코드도 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-136">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="8fab6-137">다음 예제는 시작만, 끝만, 그리고 시작과 끝이 모두 열린 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-137">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="8fab6-138">범위나 인덱스를 변수로 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-138">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="8fab6-139">그러면 이 변수를 `[` 및 `]` 문자 사이에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-139">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="8fab6-140">앞의 예제에서는 추가적인 설명이 필요한 두 가지 설계 의사 결정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-140">The previous examples show two design decisions that require more explanation:</span></span>

- <span data-ttu-id="8fab6-141">범위가 *배타적*이면 마지막 인덱스의 요소가 범위에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-141">Ranges are *exclusive*, meaning the element at the last index isn't in the range.</span></span>
- <span data-ttu-id="8fab6-142">`^0` 인덱스는 컬렉션의 *끝*이지, 컬렉션의 *마지막 요소*가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-142">The index `^0` is *the end* of the collection, not *the last element* in the collection.</span></span>

<span data-ttu-id="8fab6-143">다음 샘플에서는 이러한 선택에 대한 여러 이유를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-143">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="8fab6-144">`x`, `y` 및 `z`를 수정하여 다양한 조합을 시도해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-144">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="8fab6-145">실험할 때는 올바른 조합을 위해 `x`가 `y`보다 작고 `y`가 `z`보다 작은 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-145">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="8fab6-146">새 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-146">Add the following code in a new method.</span></span> <span data-ttu-id="8fab6-147">다양한 조합을 시도해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-147">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="8fab6-148">인덱스 및 범위에 대한 시나리오</span><span class="sxs-lookup"><span data-stu-id="8fab6-148">Scenarios for Indices and Ranges</span></span>

<span data-ttu-id="8fab6-149">전체 시퀀스의 하위 범위에 대한 특정 분석을 수행할 때 범위와 인덱스를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-149">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="8fab6-150">새 구문에서는 어떤 하위 범위가 관련되었는지 더 명확히 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-150">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="8fab6-151">로컬 함수 `MovingAverage`는 <xref:System.Range>를 인수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-151">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="8fab6-152">그러면 메서드가 최솟값, 최댓값, 평균을 계산할 때 이 범위만 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-152">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="8fab6-153">프로젝트에 다음 코드를 시도해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-153">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="8fab6-154">완료된 코드는 [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) 리포지토리에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fab6-154">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
