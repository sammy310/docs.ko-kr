---
title: 활성 패턴
description: 활성 패턴을 사용 하 여 입력된 데이터를 분할 하는 명명 된 파티션을 정의 하는 방법을 알아봅니다는 F# 프로그래밍 언어입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 25ab255574390d3761fe788aeb413c8ee04fda2a
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690418"
---
# <a name="active-patterns"></a><span data-ttu-id="657f0-103">활성 패턴</span><span class="sxs-lookup"><span data-stu-id="657f0-103">Active Patterns</span></span>

<span data-ttu-id="657f0-104">*활성 패턴* 이러한 이름을 사용 하 여 패턴 일치 구별된 된 공용 구조체에 대 한 것 처럼 식에에서는 입력된 데이터를 분할 하는 명명 된 파티션을 정의할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="657f0-105">활성 패턴을 사용하여 각 파티션에 대한 사용자 지정 방식으로 데이터를 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="657f0-106">구문</span><span class="sxs-lookup"><span data-stu-id="657f0-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="657f0-107">설명</span><span class="sxs-lookup"><span data-stu-id="657f0-107">Remarks</span></span>

<span data-ttu-id="657f0-108">이전 구문에서 식별자에 의해 표현 되는 입력된 데이터의 파티션에 대 한 이름 *인수*, 또는 즉, 인수의 모든 값의 집합의 하위 집합에 대 한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="657f0-109">활성 패턴 정의에 최대 7 개의 파티션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="657f0-110">합니다 *식* 데이터를 분해 하는 형식에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="657f0-111">인수에 속하는 지정 된 값의 명명 된 파티션을 확인 하는 것에 대 한 규칙을 정의 하는 활성 패턴 정의 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="657f0-112">(| 및 |) 기호 라고 *바나나 클립* let 바인딩이 형식에 의해 생성 함수를 호출 하 고는 *활성 인식기*합니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="657f0-113">예를 들어 인수를 사용 하 여 활성 패턴을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="657f0-114">다음 예제와 같이 식에서 일치 하는 패턴의 활성 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="657f0-115">이 프로그램의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-115">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="657f0-116">활성 패턴의 또 다른 용도 동일한 기본 데이터의 여러 가지 가능한 표현 사이 있을 때와 같은 여러 가지 방법으로 데이터 형식을 분해 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="657f0-117">예를 들어, 한 `Color` 는 RGB 표현 또는 HSB 표현으로 개체를 분해할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="657f0-118">위 프로그램의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-118">The output of the above program is as follows:</span></span>

```
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

<span data-ttu-id="657f0-119">조합 활성 패턴을 사용 하 여 이러한 두 가지 파티션 수만 적절 한 형태로 데이터를 분해 하 고 적절 한 데이터는 계산을 위한 가장 편리한 폼에 대해 적절 한 계산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="657f0-120">결과 패턴 일치 식을 사용 데이터를 읽을 수 있는 매우를 크게 간소화 잠재적으로 복잡 한 분기 및 코드를 분석 하는 데이터는 편리한 방식으로 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="657f0-121">부분 활성 패턴</span><span class="sxs-lookup"><span data-stu-id="657f0-121">Partial Active Patterns</span></span>

<span data-ttu-id="657f0-122">때로는 일부만 입력 공간 분할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="657f0-123">이런 경우는 일부 입력와 일치 하지만 다른 입력에 맞게 실패 부분 패턴 집합을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="657f0-124">값을 생성 하지 않을 수 있는 활성 패턴 이라고 *부분 활성 패턴*; 옵션 형식으로 반환 값을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="657f0-125">와일드 카드 문자를 사용 하면 부분 활성 패턴을 정의 하려면 (\_) 바나나 클립 내 패턴의 목록 끝에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="657f0-126">다음 코드 부분 활성 패턴의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="657f0-127">이전 예제의 출력은 아래와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-127">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="657f0-128">부분 활성 패턴을 사용 하는 경우 때때로 개별 선택 비연속 또는 함께 사용할 수 없습니다 있지만 될 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="657f0-129">다음 예제에서 패턴 사각형 및 패턴 큐브는 아닙니다이 일부 숫자 사각형 및 64와 같은 큐브.</span><span class="sxs-lookup"><span data-stu-id="657f0-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="657f0-130">다음 프로그램 사각형 및 정육면체 패턴을 결합 하는 AND 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="657f0-131">최대 1000 모두 사각형 및 큐브 뿐만 큐브만 되는 모든 정수 출력.</span><span class="sxs-lookup"><span data-stu-id="657f0-131">It print out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span> 

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="657f0-132">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-132">The output is as follows:</span></span>

```
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

## <a name="parameterized-active-patterns"></a><span data-ttu-id="657f0-133">매개 변수가 있는 활성 패턴</span><span class="sxs-lookup"><span data-stu-id="657f0-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="657f0-134">활성 패턴은 항상 일치 하는 항목에 대 한 하나 이상의 인수를 사용 하지만 경우 이름 인수를 추가로 걸릴 수 있습니다 *매개 변수가 있는 활성 패턴* 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="657f0-135">추가 인수는 특수화 되어야 하는 일반적인 패턴을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="657f0-136">종종 문자열을 구문 분석할 정규식을 사용 하는 활성 패턴 또한 부분 활성 패턴을 사용 하는 다음 코드와 같이 추가 매개 변수로 정규식을 포함 하는 예를 들어 `Integer` 이전 코드 예제에서 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="657f0-137">이 예제에서는 다양 한 날짜 형식에 대 한 정규식을 사용 하는 문자열은 일반 ParseRegex 활성 패턴에 맞게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="657f0-138">정수 활성 패턴 일치 하는 문자열을 DateTime 생성자에 전달할 수 있는 정수로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="657f0-139">이전 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-139">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="657f0-140">활성 패턴 패턴 일치 식에만 제한 되지 않습니다., let 바인딩에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="657f0-141">이전 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="657f0-141">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="657f0-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="657f0-142">See also</span></span>

- [<span data-ttu-id="657f0-143">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="657f0-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="657f0-144">일치 식</span><span class="sxs-lookup"><span data-stu-id="657f0-144">Match Expressions</span></span>](match-expressions.md)
