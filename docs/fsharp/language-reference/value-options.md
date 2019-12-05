---
title: 값 옵션
description: 옵션 형식의 구조체 F# 버전인 Value 옵션 형식에 대해 알아봅니다.
ms.date: 12/04/2019
ms.openlocfilehash: 0e9882ab4acdf2757705ef6022516d3572d87ef2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837118"
---
# <a name="value-options"></a><span data-ttu-id="b5139-103">값 옵션</span><span class="sxs-lookup"><span data-stu-id="b5139-103">Value Options</span></span>

<span data-ttu-id="b5139-104">다음 두 가지 경우에 F# 값 옵션 유형이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="b5139-105">시나리오는 [ F# 옵션](options.md)에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="b5139-106">구조체를 사용 하면 시나리오에서 성능상의 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="b5139-107">일부 성능 관련 시나리오는 구조체를 사용 하 여 "해결" 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="b5139-108">참조 형식 대신 사용 하는 경우 복사의 추가 비용을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="b5139-109">그러나 큰 F# 프로그램은 일반적으로 실행 부하 과다 경로를 통해 전달 되는 많은 선택적 형식을 인스턴스화합니다. 이러한 경우에는 구조체를 통해 프로그램의 수명 동안 전반적인 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, and in such cases, structs can often yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="b5139-110">정의</span><span class="sxs-lookup"><span data-stu-id="b5139-110">Definition</span></span>

<span data-ttu-id="b5139-111">Value 옵션은 참조 옵션 형식과 비슷한 [구조체로 구분 된 공용 구조체](discriminated-unions.md#struct-discriminated-unions) 로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="b5139-112">해당 정의는 다음과 같은 방식으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="b5139-113">값 옵션은 구조적 같음 및 비교를 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="b5139-114">주요 차이점은 컴파일된 이름, 형식 이름 및 사례 이름이 모두 값 형식 임을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="b5139-115">값 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="b5139-115">Using Value Options</span></span>

<span data-ttu-id="b5139-116">값 옵션은 [옵션과](options.md)마찬가지로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="b5139-117">`ValueSome`은 값이 존재 함을 나타내는 데 사용 되며, `ValueNone` 값이 없을 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

<span data-ttu-id="b5139-118">[옵션과](options.md)마찬가지로 `ValueOption`을 반환 하는 함수에 대 한 명명 규칙은 `try`에 접두사로 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="b5139-119">Value 옵션 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="b5139-119">Value Option properties and methods</span></span>

<span data-ttu-id="b5139-120">현재 값 옵션에 대 한 속성은 `Value`입니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="b5139-121">이 속성이 호출 될 때 값이 없는 경우 <xref:System.InvalidOperationException> 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="b5139-122">Value 옵션 함수</span><span class="sxs-lookup"><span data-stu-id="b5139-122">Value Option functions</span></span>

<span data-ttu-id="b5139-123">Fsharp.core의 `ValueOption` 모듈에는 `Option` 모듈에 해당 하는 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-123">The `ValueOption` module in FSharp.Core contains equivalent functionality to the `Option` module.</span></span> <span data-ttu-id="b5139-124">`defaultValueArg`와 같이 이름에는 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-124">There are a few differences in name, such as `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

<span data-ttu-id="b5139-125">이는 `Option` 모듈에서 `defaultArg`와 동일 하 게 작동 하지만 대신 값 옵션에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5139-125">This acts just like `defaultArg` in the `Option` module, but operates on a Value Option instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5139-126">참조</span><span class="sxs-lookup"><span data-stu-id="b5139-126">See also</span></span>

- [<span data-ttu-id="b5139-127">Options</span><span class="sxs-lookup"><span data-stu-id="b5139-127">Options</span></span>](options.md)
