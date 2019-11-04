---
title: 활성 패턴
description: 활성 패턴을 사용 하 여 F# 프로그래밍 언어로 입력 데이터를 세분 하는 명명 된 파티션을 정의 하는 방법을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: f5ed4a8600cba10d23d01628aba6ca07e543c586
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425102"
---
# <a name="active-patterns"></a><span data-ttu-id="ca933-103">활성 패턴</span><span class="sxs-lookup"><span data-stu-id="ca933-103">Active Patterns</span></span>

<span data-ttu-id="ca933-104">*활성 패턴* 을 사용 하면 입력 데이터를 구분 하는 명명 된 파티션을 정의할 수 있으므로 구분 된 공용 구조체의 경우와 마찬가지로 패턴 일치 식에 이러한 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="ca933-105">활성 패턴을 사용하여 각 파티션에 대한 사용자 지정 방식으로 데이터를 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="ca933-106">구문</span><span class="sxs-lookup"><span data-stu-id="ca933-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="ca933-107">주의</span><span class="sxs-lookup"><span data-stu-id="ca933-107">Remarks</span></span>

<span data-ttu-id="ca933-108">이전 구문에서 식별자는 *인수로*표시 되는 입력 데이터의 파티션에 대 한 이름입니다. 즉, 인수 값 집합의 하위 집합에 대 한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="ca933-109">활성 패턴 정의에는 최대 7 개의 파티션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="ca933-110">*식은* 데이터를 분해할 폼을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="ca933-111">활성 패턴 정의를 사용 하 여 인수로 지정 된 값이 속하는 명명 된 파티션을 결정 하는 규칙을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="ca933-112">(| 및 |) 기호를 *바나나 클립* 이라고 하며이 유형의 let 바인딩을 통해 만든 함수를 *활성 인식기*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="ca933-113">예를 들어 인수를 사용 하는 다음 활성 패턴을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="ca933-114">다음 예제와 같이 패턴 일치 식에 활성 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="ca933-115">이 프로그램의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-115">The output of this program is as follows:</span></span>

```console
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="ca933-116">활성 패턴의 또 다른 용도는 동일한 기본 데이터에 가능한 여러 표현이 있는 경우와 같이 여러 가지 방법으로 데이터 형식을 분해 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="ca933-117">예를 들어 `Color` 개체는 RGB 표현 또는 HSB 표현으로 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="ca933-118">위의 프로그램의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-118">The output of the above program is as follows:</span></span>

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

<span data-ttu-id="ca933-119">이러한 두 가지 방법을 함께 사용 하면 활성 패턴을 사용 하 여 데이터를 적절 한 형식으로 분할 및 분해 하 고 계산에 가장 편리한 형태로 적절 한 데이터에 대 한 적절 한 계산을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="ca933-120">결과 패턴 일치 식을 사용 하면 매우 쉽게 읽을 수 있는 편리한 방식으로 데이터를 작성 하 여 복잡 한 분기 및 데이터 분석 코드를 크게 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="ca933-121">부분 활성 패턴</span><span class="sxs-lookup"><span data-stu-id="ca933-121">Partial Active Patterns</span></span>

<span data-ttu-id="ca933-122">경우에 따라 입력 공간의 일부만 분할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="ca933-123">이 경우 일부 입력을 일치 하지만 다른 입력과 일치 하지 않는 partial 패턴 집합을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="ca933-124">항상 값을 생성 하지 않는 활성 패턴을 *부분 활성 패턴*이라고 합니다. 이러한 값에는 옵션 유형인 반환 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="ca933-125">부분 활성 패턴을 정의 하려면 바나나 클립 내부의 패턴 목록 끝에 와일드 카드 문자 (\_)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="ca933-126">다음 코드에서는 부분 활성 패턴을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="ca933-127">이전 예제의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-127">The output of the previous example is as follows:</span></span>

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="ca933-128">부분 활성 패턴을 사용 하는 경우 개별 선택 항목은 분리 되거나 함께 사용할 수 없지만 그렇지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="ca933-129">다음 예에서는 일부 숫자가 사각형과 큐브 (예: 64) 이기 때문에 패턴 사각형과 패턴 큐브는 비연속이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="ca933-130">다음 프로그램에서는 및 패턴을 사용 하 여 사각형과 큐브 패턴을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="ca933-131">사각형 및 큐브와 큐브와 큐브와 같은 모든 1000 정수를 출력 합니다 .이는 큐브 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-131">It print out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="ca933-132">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-132">The output is as follows:</span></span>

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

## <a name="parameterized-active-patterns"></a><span data-ttu-id="ca933-133">매개 변수가 있는 활성 패턴</span><span class="sxs-lookup"><span data-stu-id="ca933-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="ca933-134">활성 패턴은 항상 일치 하는 항목에 대 한 인수를 하나 이상 사용 하지만 추가 인수도 사용할 수 있습니다 .이 경우에는 이름 *매개 변수가 있는 활성 패턴이* 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="ca933-135">추가 인수를 사용 하면 일반 패턴을 특수화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="ca933-136">예를 들어, 정규식을 사용 하 여 문자열을 구문 분석 하는 활성 패턴은 다음 코드와 같이 정규식을 추가 매개 변수로 포함 하는 경우가 많습니다 .이 코드는 앞의 코드 예제에서 정의 된 부분 활성 패턴 `Integer` 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="ca933-137">이 예제에서는 일반 ParseRegex 활성 패턴을 사용자 지정 하기 위해 다양 한 날짜 형식에 정규식을 사용 하는 문자열을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="ca933-138">정수 활성 패턴은 일치 하는 문자열을 DateTime 생성자에 전달할 수 있는 정수로 변환 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="ca933-139">이전 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-139">The output of the previous code is as follows:</span></span>

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="ca933-140">활성 패턴은 패턴 일치 식 으로만 제한 되지 않으며 let 바인딩에서 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="ca933-141">이전 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca933-141">The output of the previous code is as follows:</span></span>

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="ca933-142">참조</span><span class="sxs-lookup"><span data-stu-id="ca933-142">See also</span></span>

- [<span data-ttu-id="ca933-143">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="ca933-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="ca933-144">일치 식</span><span class="sxs-lookup"><span data-stu-id="ca933-144">Match Expressions</span></span>](match-expressions.md)
