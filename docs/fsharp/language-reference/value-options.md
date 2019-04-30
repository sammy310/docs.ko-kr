---
title: 값 옵션
description: 에 대해 알아봅니다는 F# 옵션 종류의 구조체 버전인 값 옵션 종류입니다.
ms.date: 02/06/2019
ms.openlocfilehash: e1036c83189c853b3704d94ca245e4818acc98c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982581"
---
# <a name="value-options"></a><span data-ttu-id="88032-103">값 옵션</span><span class="sxs-lookup"><span data-stu-id="88032-103">Value Options</span></span>

<span data-ttu-id="88032-104">값 옵션 형식 F# 다음 두 경우 저장할 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88032-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="88032-105">시나리오에 적합 한 [ F# 옵션](options.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88032-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="88032-106">구조체를 사용 하는 시나리오의 성능 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88032-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="88032-107">일부 성능에 민감한 시나리오는 "해결" 구조체를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="88032-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="88032-108">참조 형식 대신 사용 하는 경우 복사 하는 추가 비용을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88032-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="88032-109">그러나 많은 F# 프로그램 일반적으로 실행 부하 과다 경로 통해 이동 하는 다양 한 선택적 형식을 인스턴스화하고 이러한 경우 구조체 수 종종 성능이 향상 전체 프로그램의 수명 동안.</span><span class="sxs-lookup"><span data-stu-id="88032-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, and in such cases, structs can often yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="88032-110">정의</span><span class="sxs-lookup"><span data-stu-id="88032-110">Definition</span></span>

<span data-ttu-id="88032-111">값 옵션으로 정의 됩니다는 [구분 된 공용 구조체 구조체](discriminated-unions.md#struct-discriminated-unions) 참조 옵션 형식과 비슷한입니다.</span><span class="sxs-lookup"><span data-stu-id="88032-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="88032-112">해당 정의가 이러한 방식으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88032-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="88032-113">구조적 같음 및 비교 값 옵션이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="88032-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="88032-114">주요 차이점은는 컴파일된 이름, 형식 이름 및 경우 대/소문자가 모든 이라는 것을 나타내는 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="88032-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="88032-115">값 옵션을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="88032-115">Using Value Options</span></span>

<span data-ttu-id="88032-116">값 옵션 처럼 사용 됩니다 [옵션](options.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88032-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="88032-117">`ValueSome` 값이 있는지를 나타내는 데 사용 되 고 `ValueNone` 값 없을 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88032-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

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

<span data-ttu-id="88032-118">와 마찬가지로 [옵션](options.md)를 반환 하는 함수에 대 한 명명 규칙 `ValueOption` 사용 하 여 접두사를 지정 하는 `try`합니다.</span><span class="sxs-lookup"><span data-stu-id="88032-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="88032-119">값 옵션 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="88032-119">Value Option properties and methods</span></span>

<span data-ttu-id="88032-120">지금은 값 옵션에 대 한 하나의 속성은: `Value`합니다.</span><span class="sxs-lookup"><span data-stu-id="88032-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="88032-121"><xref:System.InvalidOperationException> 값이 현재가이 속성을 호출할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="88032-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="88032-122">값 옵션 함수</span><span class="sxs-lookup"><span data-stu-id="88032-122">Value Option functions</span></span>

<span data-ttu-id="88032-123">값 옵션에 대 한 하나의 모듈 바인딩된 함수는 현재 `defaultValueArg`:</span><span class="sxs-lookup"><span data-stu-id="88032-123">There is currently one module-bound function for Value Options, `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

<span data-ttu-id="88032-124">와 마찬가지로 합니다 `defaultArg` 함수를 `defaultValueArg` 경우 지정 된 값 옵션의 기본 값을 반환 존재 않으면 그렇지 않은 경우 지정된 된 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88032-124">As with the `defaultArg` function, `defaultValueArg` returns the underlying value of the given Value Option if it exists; otherwise, it returns the specified default value.</span></span>

<span data-ttu-id="88032-125">이때 값 옵션에 대 한 다른 모듈 바인딩된 함수가 없는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88032-125">At this time, there are no other module-bound functions for Value Options.</span></span>

## <a name="see-also"></a><span data-ttu-id="88032-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="88032-126">See also</span></span>

- [<span data-ttu-id="88032-127">옵션</span><span class="sxs-lookup"><span data-stu-id="88032-127">Options</span></span>](options.md)
