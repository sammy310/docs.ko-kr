---
title: 활성 패턴
description: 활성 패턴을 사용하여 F# 프로그래밍 언어로 입력 데이터를 세분화하는 명명된 파티션을 정의하는 방법을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 898ef201369683bfd49d53e863e86f919f5837fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187067"
---
# <a name="active-patterns"></a><span data-ttu-id="48e42-103">활성 패턴</span><span class="sxs-lookup"><span data-stu-id="48e42-103">Active Patterns</span></span>

<span data-ttu-id="48e42-104">*활성 패턴을* 사용하면 입력 데이터를 세분화하는 명명된 파티션을 정의할 수 있으므로 구별된 공용 구조체와 마찬가지로 패턴 일치 식에서 이러한 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="48e42-105">활성 패턴을 사용하여 각 파티션에 대한 사용자 지정 방식으로 데이터를 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="48e42-106">구문</span><span class="sxs-lookup"><span data-stu-id="48e42-106">Syntax</span></span>

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a><span data-ttu-id="48e42-107">설명</span><span class="sxs-lookup"><span data-stu-id="48e42-107">Remarks</span></span>

<span data-ttu-id="48e42-108">이전 구문에서 식별자는 *인수로*표시되는 입력 데이터의 파티션에 대한 이름또는 인수의 모든 값 집합집합의 하위 집합에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="48e42-109">활성 패턴 정의에는 최대 7개의 파티션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="48e42-110">*식은* 데이터를 분해할 폼을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="48e42-111">활성 패턴 정의를 사용하여 인수로 지정된 값이 속한 명명된 파티션을 결정하는 규칙을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="48e42-112">(| 및 |) 기호를 *바나나 클립이라고* 하며 이러한 유형의 let 바인딩에 의해 생성된 함수를 *활성 인식기라고*합니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="48e42-113">예를 들어 인수와 함께 다음 활성 패턴을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="48e42-114">다음 예제와 같이 패턴 일치 식에서 활성 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="48e42-115">이 프로그램의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-115">The output of this program is as follows:</span></span>

```console
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="48e42-116">활성 패턴의 또 다른 용도는 동일한 기본 데이터에 다양한 가능한 표현이 있는 경우와 같이 여러 가지 방법으로 데이터 형식을 분해하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="48e42-117">예를 들어 `Color` 개체를 RGB 표현 또는 HSB 표현으로 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="48e42-118">위의 프로그램의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-118">The output of the above program is as follows:</span></span>

```console
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

<span data-ttu-id="48e42-119">이러한 두 가지 활성 패턴을 사용하면 데이터를 적절한 형식으로 분할 및 분해하고 계산에 가장 편리한 형태로 적절한 데이터에 대한 적절한 계산을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="48e42-120">결과 패턴 일치 식을 사용하면 매우 읽기 쉬운 편리한 방식으로 데이터를 작성할 수 있으므로 잠재적으로 복잡한 분기 및 데이터 분석 코드가 크게 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="48e42-121">부분 활성 패턴</span><span class="sxs-lookup"><span data-stu-id="48e42-121">Partial Active Patterns</span></span>

<span data-ttu-id="48e42-122">때로는 입력 공간의 일부만 분할해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="48e42-123">이 경우 일부 입력과 일치하지만 다른 입력과 일치하지 않는 부분 패턴 집합을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="48e42-124">항상 값을 생성하지 않는 활성 *패턴을 부분 활성 패턴이라고 합니다.* 옵션 형식인 반환 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="48e42-125">부분 활성 패턴을 정의하려면 바나나 클립 내부의 패턴 목록 끝에 와일드카드 문자()를\_사용합니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="48e42-126">다음 코드는 부분 활성 패턴의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="48e42-127">이전 예제의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-127">The output of the previous example is as follows:</span></span>

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="48e42-128">부분 활성 패턴을 사용하는 경우 개별 선택이 분리되거나 상호 배타적일 수 있지만 필요하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="48e42-129">다음 예제에서는 일부 숫자가 사각형과 64와 같은 큐브이기 때문에 패턴 정사각형과 패턴 큐브가 분리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="48e42-130">다음 프로그램은 AND 패턴을 사용하여 정사각형 및 큐브 패턴을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="48e42-131">정사각형과 큐브모두인 최대 1000개의 정수와 큐브만 인쇄됩니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-131">It prints out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="48e42-132">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-132">The output is as follows:</span></span>

```console
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="48e42-133">매개 변수화된 활성 패턴</span><span class="sxs-lookup"><span data-stu-id="48e42-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="48e42-134">활성 패턴은 항상 일치하는 항목에 대해 하나 이상의 인수를 사용하지만 추가 인수도 걸릴 수 있으며, 이 경우 이름 *매개 변수화된 활성 패턴이* 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="48e42-135">추가 인수를 사용하면 일반 패턴을 특수화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="48e42-136">예를 들어 문자열을 구문 분석하기 위해 정규식을 사용하는 활성 패턴에는 이전 코드 예제에서 정의된 부분 활성 `Integer` 패턴을 사용하는 다음 코드와 같이 정규식을 추가 매개 변수로 포함되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="48e42-137">이 예제에서는 다양한 날짜 형식에 정규식을 사용하는 문자열이 주어지므로 일반 ParseRegex 활성 패턴을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="48e42-138">정수 활성 패턴은 일치하는 문자열을 DateTime 생성자에 전달할 수 있는 정수로 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="48e42-139">이전 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-139">The output of the previous code is as follows:</span></span>

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="48e42-140">활성 패턴은 패턴 일치 식에만 국한되지 않고 let-bindings에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="48e42-141">이전 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48e42-141">The output of the previous code is as follows:</span></span>

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="48e42-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48e42-142">See also</span></span>

- [<span data-ttu-id="48e42-143">F # 언어 참조</span><span class="sxs-lookup"><span data-stu-id="48e42-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="48e42-144">일치 식</span><span class="sxs-lookup"><span data-stu-id="48e42-144">Match Expressions</span></span>](match-expressions.md)
