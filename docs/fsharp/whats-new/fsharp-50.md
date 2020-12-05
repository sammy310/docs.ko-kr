---
title: 'F # 5.0의 새로운 기능-F # 가이드'
description: 'F # 5.0에서 사용할 수 있는 새로운 기능에 대 한 개요를 확인 하세요.'
ms.date: 11/06/2020
ms.openlocfilehash: 2384f1a75f5e708dc6f170d82fa15c5e0f54c85d
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740187"
---
# <a name="whats-new-in-f-50"></a><span data-ttu-id="0443a-103">F# 5.0의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="0443a-103">What's new in F# 5.0</span></span>

<span data-ttu-id="0443a-104">F # 5.0은 F # 언어 및 F# 대화형에 몇 가지 향상 된 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-104">F# 5.0 adds several improvements to the F# language and F# Interactive.</span></span> <span data-ttu-id="0443a-105">**.Net 5** 와 함께 출시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-105">It is released with **.NET 5**.</span></span>

<span data-ttu-id="0443a-106">[.NET 다운로드 페이지](https://dotnet.microsoft.com/download)에서 최신 .NET SDK를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-106">You can download the latest .NET SDK from the [.NET downloads page](https://dotnet.microsoft.com/download).</span></span>

## <a name="get-started"></a><span data-ttu-id="0443a-107">시작</span><span class="sxs-lookup"><span data-stu-id="0443a-107">Get started</span></span>

<span data-ttu-id="0443a-108">F # 5.0은 모든 .NET Core 배포 및 Visual Studio 도구에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-108">F# 5.0 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="0443a-109">자세한 내용은 [F # 시작](../get-started/index.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0443a-109">For more information, see [Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="package-references-in-f-scripts"></a><span data-ttu-id="0443a-110">F # 스크립트의 패키지 참조</span><span class="sxs-lookup"><span data-stu-id="0443a-110">Package references in F# scripts</span></span>

<span data-ttu-id="0443a-111">F # 5는 구문을 사용 하 여 F # 스크립트에서 패키지 참조를 지원 `#r "nuget:..."` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-111">F# 5 brings support for package references in F# scripts with `#r "nuget:..."` syntax.</span></span> <span data-ttu-id="0443a-112">예를 들어 다음 패키지 참조를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-112">For example, consider the following package reference:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json"

open Newtonsoft.Json

let o = {| X = 2; Y = "Hello" |}

printfn $"{JsonConvert.SerializeObject o}"
```

<span data-ttu-id="0443a-113">패키지 이름 뒤에 다음과 같은 명시적 버전을 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-113">You can also supply an explicit version after the name of the package like this:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json,11.0.1"
```

<span data-ttu-id="0443a-114">패키지 참조는 ML.NET와 같은 네이티브 종속성이 있는 패키지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-114">Package references support packages with native dependencies, such as ML.NET.</span></span>

<span data-ttu-id="0443a-115">패키지 참조는 종속 항목 참조에 대 한 특별 한 요구 사항이 있는 패키지도 지원 `.dll` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-115">Package references also support packages with special requirements about referencing dependent `.dll`s.</span></span> <span data-ttu-id="0443a-116">예를 들어, 사용자가 수동으로 해당 종속이 참조 되었는지 확인 하는 데 사용 되는 [Fparsec](https://www.nuget.org/packages/FParsec/) 패키지는 `FParsecCS.dll` `FParsec.dll` F# 대화형에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-116">For example, the [FParsec](https://www.nuget.org/packages/FParsec/) package used to require that users manually ensure that its dependent `FParsecCS.dll` was referenced first before `FParsec.dll` was referenced in F# Interactive.</span></span> <span data-ttu-id="0443a-117">더 이상 필요 하지 않으며 다음과 같이 패키지를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-117">This is no longer needed, and you can reference the package as follows:</span></span>

```fsharp
#r "nuget: FParsec"

open FParsec

let test p str =
    match run p str with
    | Success(result, _, _)   -> printfn $"Success: {result}"
    | Failure(errorMsg, _, _) -> printfn $"Failure: {errorMsg}"

test pfloat "1.234"
```

<span data-ttu-id="0443a-118">이 기능은 [F # 도구 RFC FST-1027](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1027-fsi-references.md)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-118">This feature implements [F# Tooling RFC FST-1027](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1027-fsi-references.md).</span></span> <span data-ttu-id="0443a-119">패키지 참조에 대 한 자세한 내용은 [F# 대화형](../tools/fsharp-interactive/index.md) 자습서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0443a-119">For more information on package references, see the [F# Interactive](../tools/fsharp-interactive/index.md) tutorial.</span></span>

## <a name="string-interpolation"></a><span data-ttu-id="0443a-120">문자열 보간</span><span class="sxs-lookup"><span data-stu-id="0443a-120">String interpolation</span></span>

<span data-ttu-id="0443a-121">F # 보간된 문자열은 c # 또는 JavaScript 보간된 문자열과 매우 유사 합니다 .이 문자열은 문자열 리터럴 내에서 "구멍"으로 코드를 작성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-121">F# interpolated strings are fairly similar to C# or JavaScript interpolated strings, in that they let you write code in "holes" inside of a string literal.</span></span> <span data-ttu-id="0443a-122">기본 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-122">Here's a basic example:</span></span>

```fsharp
let name = "Phillip"
let age = 29
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

<span data-ttu-id="0443a-123">그러나 F # 보간된 문자열은 함수와 마찬가지로 형식화 된 보간를 허용 `sprintf` 하 여 보간된 컨텍스트 내의 식이 특정 형식을 따르는지를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-123">However, F# interpolated strings also allow for typed interpolations, just like the `sprintf` function, to enforce that an expression inside of an interpolated context conforms to a particular type.</span></span> <span data-ttu-id="0443a-124">동일한 형식 지정자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-124">It uses the same format specifiers.</span></span>

```fsharp
let name = "Phillip"
let age = 29

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

<span data-ttu-id="0443a-125">앞의 형식화 된 보간 예제에서는 `%s` 보간을 형식으로 요구 하는 `string` 반면에는 `%d` 보간이 필요 합니다 `integer` .</span><span class="sxs-lookup"><span data-stu-id="0443a-125">In the preceding typed interpolation example, the `%s` requires the interpolation to be of type `string`, whereas the `%d` requires the interpolation to be an `integer`.</span></span>

<span data-ttu-id="0443a-126">또한 임의의 F # 식 (또는 식)을 보간 컨텍스트의 측면에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-126">Additionally, any arbitrary F# expression (or expressions) can be placed in side of an interpolation context.</span></span> <span data-ttu-id="0443a-127">다음과 같이 더 복잡 한 식을 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-127">It is even possible to write a more complicated expression, like so:</span></span>

```fsharp
let str =
    $"""The result of squaring each odd item in {[1..10]} is:
{
    let square x = x * x
    let isOdd x = x % 2 <> 0
    let oddSquares xs =
        xs
        |> List.filter isOdd
        |> List.map square
    oddSquares [1..10]
}
"""
```

<span data-ttu-id="0443a-128">실제로는이 작업을 수행 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-128">Although we don't recommend doing this too much in practice.</span></span>

<span data-ttu-id="0443a-129">이 기능은 [F # RFC FS-1001](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1001-StringInterpolation.md)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-129">This feature implements [F# RFC FS-1001](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1001-StringInterpolation.md).</span></span>

## <a name="support-for-nameof"></a><span data-ttu-id="0443a-130">Nameof에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="0443a-130">Support for nameof</span></span>

<span data-ttu-id="0443a-131">F # 5는 `nameof` 사용 되는 기호를 확인 하 고 f # 소스에서 해당 이름을 생성 하는 연산자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-131">F# 5 supports the `nameof` operator, which resolves the symbol it's being used for and produces its name in F# source.</span></span> <span data-ttu-id="0443a-132">이는 로깅과 같은 다양 한 시나리오에서 유용 하며 소스 코드의 변경 내용에 대해 로깅을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-132">This is useful in various scenarios, such as logging, and protects your logging against changes in source code.</span></span>

```fsharp
let months =
    [
        "January"; "February"; "March"; "April";
        "May"; "June"; "July"; "August"; "September";
        "October"; "November"; "December"
    ]

let lookupMonth month =
    if (month > 12 || month < 1) then
        invalidArg (nameof month) (sprintf "Value passed in was %d." month)

    months.[month-1]

printfn $"{lookupMonth 12}"
printfn $"{lookupMonth 1}"
printfn $"{lookupMonth 13}"
```

<span data-ttu-id="0443a-133">마지막 줄에서는 예외를 throw 하 고 오류 메시지에 "month"가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-133">The last line will throw an exception and "month" will be shown in the error message.</span></span>

<span data-ttu-id="0443a-134">거의 모든 F # 구문의 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-134">You can take a name of nearly every F# construct:</span></span>

```fsharp
module M =
    let f x = nameof x

printfn $"{M.f 12}"
printfn $"{nameof M}"
printfn $"{nameof M.f}"
```

<span data-ttu-id="0443a-135">연산자가 작동 하는 방식에 대 한 세 가지 최종 추가 사항이 변경 되었습니다. `nameof<'type-parameter>` 제네릭 형식 매개 변수에는 폼이 추가 되 고 `nameof` 패턴 일치 식에서는 패턴으로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-135">Three final additions are changes to how operators work: the addition of the `nameof<'type-parameter>` form for generic type parameters, and the ability to use `nameof` as a pattern in a pattern match expression.</span></span>

<span data-ttu-id="0443a-136">연산자의 이름을 사용 하면 해당 소스 문자열이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-136">Taking a name of an operator gives its source string.</span></span> <span data-ttu-id="0443a-137">컴파일된 폼이 필요한 경우에는 연산자의 컴파일된 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-137">If you need the compiled form, use the compiled name of an operator:</span></span>

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

<span data-ttu-id="0443a-138">형식 매개 변수의 이름을 사용 하려면 약간 다른 구문이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-138">Taking the name of a type parameter requires a slightly different syntax:</span></span>

```fsharp
type C<'TType> =
    member _.TypeName = nameof<'TType>
```

<span data-ttu-id="0443a-139">이는 `typeof<'T>` 및 연산자와 유사 `typedefof<'T>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-139">This is similar to the `typeof<'T>` and `typedefof<'T>` operators.</span></span>

<span data-ttu-id="0443a-140">또한 F # 5는 `nameof` 식에 사용할 수 있는 패턴에 대 한 지원을 추가 합니다 `match` .</span><span class="sxs-lookup"><span data-stu-id="0443a-140">F# 5 also adds support for a `nameof` pattern that can be used in `match` expressions:</span></span>

```fsharp
[<Struct; IsByRefLike>]
type RecordedEvent = { EventType: string; Data: ReadOnlySpan<byte> }

type MyEvent =
    | AData of int
    | BData of string

let deserialize (e: RecordedEvent) : MyEvent =
    match e.EventType with
    | nameof AData -> AData (JsonSerializer.Deserialize<int> e.Data)
    | nameof BData -> BData (JsonSerializer.Deserialize<string> e.Data)
    | t -> failwithf "Invalid EventType: %s" t
```

<span data-ttu-id="0443a-141">이전 코드는 일치 식에서 문자열 리터럴 대신 ' nameof '를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-141">The preceding code uses 'nameof' instead of the string literal in the match expression.</span></span>

<span data-ttu-id="0443a-142">이 기능은 [F # RFC FS-1003](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1003-nameof-operator.md)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-142">This feature implements [F# RFC FS-1003](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1003-nameof-operator.md).</span></span>

## <a name="open-type-declarations"></a><span data-ttu-id="0443a-143">개방형 형식 선언</span><span class="sxs-lookup"><span data-stu-id="0443a-143">Open type declarations</span></span>

<span data-ttu-id="0443a-144">또한 F # 5는 개방형 형식 선언에 대 한 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-144">F# 5 also adds support for open type declarations.</span></span> <span data-ttu-id="0443a-145">개방형 형식 선언은 F # 의미 체계에 적합 한 몇 가지 다른 구문과 약간 다른 동작을 제외 하 고 c #에서 정적 클래스를 여는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-145">An open type declaration is like opening a static class in C#, except with some different syntax and some slightly different behavior to fit F# semantics.</span></span>

<span data-ttu-id="0443a-146">개방형 형식 선언에서는 모든 형식을 사용 하 여 `open` 내부에 정적 콘텐츠를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-146">With open type declarations, you can `open` any type to expose static contents inside of it.</span></span> <span data-ttu-id="0443a-147">또한 `open` F #으로 정의 된 공용 구조체 및 레코드를 통해 해당 콘텐츠를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-147">Additionally, you can `open` F#-defined unions and records to expose their contents.</span></span> <span data-ttu-id="0443a-148">예를 들어, 모듈에 union이 정의 되어 있고 해당 사례에 액세스 하려고 하지만 전체 모듈을 열지 않으려는 경우이 방법이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-148">For example, this can be useful if you have a union defined in a module and want to access its cases, but don't want to open the entire module.</span></span>

```fsharp
open type System.Math

let x = Min(1.0, 2.0)

module M =
    type DU = A | B | C

    let someOtherFunction x = x + 1

// Open only the type inside the module
open type M.DU

printfn $"{A}"
```

<span data-ttu-id="0443a-149">C #과 달리 `open type` 동일한 이름의 멤버를 노출 하는 두 가지 형식을 사용 하는 경우 마지막 형식의 멤버가 `open` 다른 이름을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-149">Unlike C#, when you `open type` on two types that expose a member with the same name, the member from the last type being `open`ed shadows the other name.</span></span> <span data-ttu-id="0443a-150">이미 존재 하는 숨김과 관련 된 F # 의미 체계와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-150">This is consistent with F# semantics around shadowing that exist already.</span></span>

<span data-ttu-id="0443a-151">이 기능은 [F # RFC FS-1068](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1068-open-type-declaration.md)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-151">This feature implements [F# RFC FS-1068](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1068-open-type-declaration.md).</span></span>

## <a name="consistent-slicing-behavior-for-built-in-data-types"></a><span data-ttu-id="0443a-152">기본 제공 데이터 형식에 대 한 일관적인 조각화 동작</span><span class="sxs-lookup"><span data-stu-id="0443a-152">Consistent slicing behavior for built-in data types</span></span>

<span data-ttu-id="0443a-153">`FSharp.Core`F # 5 이전에 일관 되지 않은 상태로 사용 되는 기본 제공 데이터 형식 (배열, 목록, 문자열, 2d 배열, 3d 배열, 4d 배열)의 조각화에 대 한 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-153">Behavior for slicing the built-in `FSharp.Core` data types (array, list, string, 2D array, 3D array, 4D array) used to not be consistent prior to F# 5.</span></span> <span data-ttu-id="0443a-154">일부 edge-case 동작에서 예외를 throw 했 고 일부는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-154">Some edge-case behavior threw an exception and some wouldn't.</span></span> <span data-ttu-id="0443a-155">F # 5에서 모든 기본 제공 형식은 이제 생성 하지 못하는 조각에 대 한 빈 조각을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-155">In F# 5, all built-in types now return empty slices for slices that are impossible to generate:</span></span>

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

// Before: would return empty list
// F# 5: same
let emptyList = l.[-2..(-1)]

// Before: would throw exception
// F# 5: returns empty array
let emptyArray = a.[-2..(-1)]

// Before: would throw exception
// F# 5: returns empty string
let emptyString = s.[-2..(-1)]
```

<span data-ttu-id="0443a-156">이 기능은 [F # RFC FS-1077](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-tolerant-slicing.md)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-156">This feature implements [F# RFC FS-1077](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-tolerant-slicing.md).</span></span>

## <a name="fixed-index-slices-for-3d-and-4d-arrays-in-fsharpcore"></a><span data-ttu-id="0443a-157">Fsharp.core에서 3D 및 4D 배열의 고정 인덱스 조각</span><span class="sxs-lookup"><span data-stu-id="0443a-157">Fixed-index slices for 3D and 4D arrays in FSharp.Core</span></span>

<span data-ttu-id="0443a-158">F # 5.0은 기본 제공 3D 및 4D 배열 형식의 고정 인덱스를 사용 하 여 조각화를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-158">F# 5.0 brings support for slicing with a fixed index in the built-in 3D and 4D array types.</span></span>

<span data-ttu-id="0443a-159">이를 설명 하기 위해 다음 3D 배열을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-159">To illustrate this, consider the following 3D array:</span></span>

<span data-ttu-id="0443a-160">*z = 0*</span><span class="sxs-lookup"><span data-stu-id="0443a-160">*z = 0*</span></span>
| <span data-ttu-id="0443a-161">x\y</span><span class="sxs-lookup"><span data-stu-id="0443a-161">x\y</span></span>   | <span data-ttu-id="0443a-162">0</span><span class="sxs-lookup"><span data-stu-id="0443a-162">0</span></span> | <span data-ttu-id="0443a-163">1</span><span class="sxs-lookup"><span data-stu-id="0443a-163">1</span></span> |
|-------|---|---|
| <span data-ttu-id="0443a-164">**0**</span><span class="sxs-lookup"><span data-stu-id="0443a-164">**0**</span></span> | <span data-ttu-id="0443a-165">0</span><span class="sxs-lookup"><span data-stu-id="0443a-165">0</span></span> | <span data-ttu-id="0443a-166">1</span><span class="sxs-lookup"><span data-stu-id="0443a-166">1</span></span> |
| <span data-ttu-id="0443a-167">**1**</span><span class="sxs-lookup"><span data-stu-id="0443a-167">**1**</span></span> | <span data-ttu-id="0443a-168">2</span><span class="sxs-lookup"><span data-stu-id="0443a-168">2</span></span> | <span data-ttu-id="0443a-169">3</span><span class="sxs-lookup"><span data-stu-id="0443a-169">3</span></span> |

<span data-ttu-id="0443a-170">*z = 1*</span><span class="sxs-lookup"><span data-stu-id="0443a-170">*z = 1*</span></span>
| <span data-ttu-id="0443a-171">x\y</span><span class="sxs-lookup"><span data-stu-id="0443a-171">x\y</span></span>   | <span data-ttu-id="0443a-172">0</span><span class="sxs-lookup"><span data-stu-id="0443a-172">0</span></span> | <span data-ttu-id="0443a-173">1</span><span class="sxs-lookup"><span data-stu-id="0443a-173">1</span></span> |
|-------|---|---|
| <span data-ttu-id="0443a-174">**0**</span><span class="sxs-lookup"><span data-stu-id="0443a-174">**0**</span></span> | <span data-ttu-id="0443a-175">4</span><span class="sxs-lookup"><span data-stu-id="0443a-175">4</span></span> | <span data-ttu-id="0443a-176">5</span><span class="sxs-lookup"><span data-stu-id="0443a-176">5</span></span> |
| <span data-ttu-id="0443a-177">**1**</span><span class="sxs-lookup"><span data-stu-id="0443a-177">**1**</span></span> | <span data-ttu-id="0443a-178">6</span><span class="sxs-lookup"><span data-stu-id="0443a-178">6</span></span> | <span data-ttu-id="0443a-179">7</span><span class="sxs-lookup"><span data-stu-id="0443a-179">7</span></span> |

<span data-ttu-id="0443a-180">배열에서 조각을 추출 하려면 어떻게 해야 `[| 4; 5 |]` 하나요?</span><span class="sxs-lookup"><span data-stu-id="0443a-180">What if you wanted to extract the slice `[| 4; 5 |]` from the array?</span></span> <span data-ttu-id="0443a-181">이제 매우 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-181">This is now very simple!</span></span>

```fsharp
// First, create a 3D array to slice

let dim = 2
let m = Array3D.zeroCreate<int> dim dim dim

let mutable count = 0

for z in 0..dim-1 do
    for y in 0..dim-1 do
        for x in 0..dim-1 do
            m.[x,y,z] <- count
            count <- count + 1

// Now let's get the [4;5] slice!
m.[*, 0, 1]
```

<span data-ttu-id="0443a-182">이 기능은 [F # RFC FS-1077b](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-3d-4d-fixed-index-slicing.md)를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-182">This feature implements [F# RFC FS-1077b](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-3d-4d-fixed-index-slicing.md).</span></span>

## <a name="f-quotations-improvements"></a><span data-ttu-id="0443a-183">F # 인용의 향상 된 기능</span><span class="sxs-lookup"><span data-stu-id="0443a-183">F# quotations improvements</span></span>

<span data-ttu-id="0443a-184">이제 F # [코드 인용구](../language-reference/code-quotations.md) 에 형식 제약 조건 정보를 유지 하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-184">F# [code quotations](../language-reference/code-quotations.md) now have the ability to retain type constraint information.</span></span> <span data-ttu-id="0443a-185">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0443a-185">Consider the following example:</span></span>

```fsharp
open FSharp.Linq.RuntimeHelpers

let eval q = LeafExpressionConverter.EvaluateQuotation q

let inline negate x = -x
// val inline negate: x: ^a ->  ^a when  ^a : (static member ( ~- ) :  ^a ->  ^a)

<@ negate 1.0 @>  |> eval
```

<span data-ttu-id="0443a-186">함수에서 생성 된 제약 조건은 `inline` 코드 따옴표로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-186">The constraint generated by the `inline` function is retained in the code quotation.</span></span> <span data-ttu-id="0443a-187">`negate`이제 함수의 quotated 폼을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-187">The `negate` function's quotated form can now be evaluated.</span></span>

<span data-ttu-id="0443a-188">이 기능은 [F # RFC FS-1071](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1071-witness-passing-quotations.md)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-188">This feature implements [F# RFC FS-1071](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1071-witness-passing-quotations.md).</span></span>

## <a name="applicative-computation-expressions"></a><span data-ttu-id="0443a-189">Applicative 계산 식</span><span class="sxs-lookup"><span data-stu-id="0443a-189">Applicative Computation Expressions</span></span>

<span data-ttu-id="0443a-190">[CEs (계산 식)](../language-reference/computation-expressions.md) 는 오늘날 "상황별 계산"을 모델링 하는 데 사용 되거나 더 함수형 프로그래밍에 익숙한 용어 monadic 계산에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-190">[Computation expressions (CEs)](../language-reference/computation-expressions.md) are used today to model "contextual computations", or in more functional programming-friendly terminology, monadic computations.</span></span>

<span data-ttu-id="0443a-191">F # 5는 다른 계산 모델을 제공 하는 applicative CEs를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-191">F# 5 introduces applicative CEs, which offer a different computational model.</span></span> <span data-ttu-id="0443a-192">Applicative CEs를 사용 하면 모든 계산이 독립적이 고 그 결과가 끝에 누적 되어 제공 되는 보다 효율적인 계산을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-192">Applicative CEs allow for more efficient computations provided that every computation is independent, and their results are accumulated at the end.</span></span> <span data-ttu-id="0443a-193">계산도 서로 독립적 이면 일반적으로 병렬화 되어 CE 작성자가 보다 효율적인 라이브러리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-193">When computations are independent of one another, they are also trivially parallelizable, allowing CE authors to write more efficient libraries.</span></span> <span data-ttu-id="0443a-194">이 혜택은 제한에서 제공 되지만 이전에 계산 된 값에 의존 하는 계산은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-194">This benefit comes at a restriction, though: computations that depend on previously computed values are not allowed.</span></span>

<span data-ttu-id="0443a-195">다음 예제에서는 형식에 대 한 기본 applicative CE를 보여 줍니다 `Result` .</span><span class="sxs-lookup"><span data-stu-id="0443a-195">The follow example shows a basic applicative CE for the `Result` type.</span></span>

```fsharp
// First, define a 'zip' function
module Result =
    let zip x1 x2 =
        match x1,x2 with
        | Ok x1res, Ok x2res -> Ok (x1res, x2res)
        | Error e, _ -> Error e
        | _, Error e -> Error e

// Next, define a builder with 'MergeSources' and 'BindReturn'
type ResultBuilder() =
    member _.MergeSources(t1: Result<'T,'U>, t2: Result<'T1,'U>) = Result.zip t1 t2
    member _.BindReturn(x: Result<'T,'U>, f) = Result.map f x

let result = ResultBuilder()

let run r1 r2 r3 =
    // And here is our applicative!
    let res1: Result<int, string> =
        result {
            let! a = r1
            and! b = r2
            and! c = r3
            return a + b - c
        }

    match res1 with
    | Ok x -> printfn $"{nameof res1} is: %d{x}"
    | Error e -> printfn $"{nameof res1} is: {e}"

let printApplicatives () =
    let r1 = Ok 2
    let r2 = Ok 3 // Error "fail!"
    let r3 = Ok 4

    run r1 r2 r3
    run r1 (Error "failure!") r3
```

<span data-ttu-id="0443a-196">현재 라이브러리에서 CEs를 노출 하는 라이브러리 작성자 인 경우 주의 해야 할 몇 가지 추가 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-196">If you're a library author who exposes CEs in their library today, there are some additional considerations you'll need to be aware of.</span></span>

<span data-ttu-id="0443a-197">이 기능은 [F # RFC FS-1063](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1063-support-letbang-andbang-for-applicative-functors.md)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-197">This feature implements [F# RFC FS-1063](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1063-support-letbang-andbang-for-applicative-functors.md).</span></span>

## <a name="interfaces-can-be-implemented-at-different-generic-instantiations"></a><span data-ttu-id="0443a-198">다른 제네릭 인스턴스화에 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-198">Interfaces can be implemented at different generic instantiations</span></span>

<span data-ttu-id="0443a-199">이제 서로 다른 제네릭 인스턴스화에 동일한 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-199">You can now implement the same interface at different generic instantiations:</span></span>

```fsharp
type IA<'T> =
    abstract member Get : unit -> 'T

type MyClass() =
    interface IA<int> with
        member x.Get() = 1
    interface IA<string> with
        member x.Get() = "hello"

let mc = MyClass()
let iaInt = mc :> IA<int>
let iaString = mc :> IA<string>

iaInt.Get() // 1
iaString.Get() // "hello"
```

<span data-ttu-id="0443a-200">이 기능은 [F # RFC FS-1031](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1031-Allow%20implementing%20the%20same%20interface%20at%20different%20generic%20instantiations%20in%20the%20same%20type.md)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-200">This feature implements [F# RFC FS-1031](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1031-Allow%20implementing%20the%20same%20interface%20at%20different%20generic%20instantiations%20in%20the%20same%20type.md).</span></span>

## <a name="default-interface-member-consumption"></a><span data-ttu-id="0443a-201">기본 인터페이스 멤버 사용</span><span class="sxs-lookup"><span data-stu-id="0443a-201">Default interface member consumption</span></span>

<span data-ttu-id="0443a-202">F # 5를 사용 하면 [기본 구현으로 인터페이스](../../csharp/tutorials/default-interface-methods-versions.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-202">F# 5 lets you consume [interfaces with default implementations](../../csharp/tutorials/default-interface-methods-versions.md).</span></span>

<span data-ttu-id="0443a-203">다음과 같이 c #으로 정의 된 인터페이스를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-203">Consider an interface defined in C# like this:</span></span>

```csharp
using System;

namespace CSharp
{
    public interface MyDimasd
    {
        public int Z => 0;
    }
}
```

<span data-ttu-id="0443a-204">인터페이스를 구현 하는 표준 방법 중 하나를 통해 F #에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-204">You can consume it in F# through any of the standard means of implementing an interface:</span></span>

```fsharp
open CSharp

// You can implement the interface via a class
type MyType() =
    member _.M() = ()

    interface MyDim

let md = MyType() :> MyDim
printfn $"DIM from C#: %d{md.Z}"

// You can also implement it via an object expression
let md' = { new MyDim }
printfn $"DIM from C# but via Object Expression: %d{md'.Z}"
```

<span data-ttu-id="0443a-205">이를 통해 사용자가 기본 구현을 사용할 수 있도록 하는 최신 c #으로 작성 된 c # 코드 및 .NET 구성 요소를 안전 하 게 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-205">This lets you safely take advantage of C# code and .NET components written in modern C# when they expect users to be able to consume a default implementation.</span></span>

<span data-ttu-id="0443a-206">이 기능은 [F # RFC FS-1074](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1074-default-interface-member-consumption.md)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-206">This feature implements [F# RFC FS-1074](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1074-default-interface-member-consumption.md).</span></span>

## <a name="simplified-interop-with-nullable-value-types"></a><span data-ttu-id="0443a-207">Nullable 값 형식을 사용한 간소화 된 interop</span><span class="sxs-lookup"><span data-stu-id="0443a-207">Simplified interop with nullable value types</span></span>

<span data-ttu-id="0443a-208">[Nullable](https://docs.microsoft.com/dotnet/api/system.nullable-1) 형식 (현재는 nullable 형식 이라고 함)은 F #에서 오래 된 것 이지만 일반적으로 이러한 형식으로 상호 작용 하는 것은 `Nullable` `Nullable<SomeType>` 값을 전달할 때마다 또는 래퍼를 생성 해야 하기 때문에 일반적으로 약간의 어려움입니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-208">[Nullable (value) types](https://docs.microsoft.com/dotnet/api/system.nullable-1) (called Nullable Types historically) have long been supported by F#, but interacting with them has traditionally been somewhat of a pain since you'd have to construct a `Nullable` or `Nullable<SomeType>` wrapper every time you wanted to pass a value.</span></span> <span data-ttu-id="0443a-209">이제 컴파일러는 `Nullable<ThatValueType>` 대상 형식이와 일치 하는 경우 값 형식을로 암시적으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-209">Now the compiler will implicitly convert a value type into a `Nullable<ThatValueType>` if the target type matches.</span></span> <span data-ttu-id="0443a-210">이제 다음 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-210">The following code is now possible:</span></span>

```fsharp
#r "nuget: Microsoft.Data.Analysis"

open Microsoft.Data.Analysis

let dateTimes = PrimitiveDataFrameColumn<DateTime>("DateTimes")

// The following line used to fail to compile
dateTimes.Append(DateTime.Parse("2019/01/01"))

// The previous line is now equivalent to this line
dateTimes.Append(Nullable<DateTime>(DateTime.Parse("2019/01/01")))
```

<span data-ttu-id="0443a-211">이 기능은 [F # RFC FS-1075](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1075-nullable-interop.md)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-211">This feature implements [F# RFC FS-1075](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1075-nullable-interop.md).</span></span>

## <a name="preview-reverse-indexes"></a><span data-ttu-id="0443a-212">미리 보기: 인덱스 반전</span><span class="sxs-lookup"><span data-stu-id="0443a-212">Preview: reverse indexes</span></span>

<span data-ttu-id="0443a-213">F # 5에는 역방향 인덱스를 허용 하기 위한 미리 보기도 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-213">F# 5 also introduces a preview for allowing reverse indexes.</span></span> <span data-ttu-id="0443a-214">구문은 `^idx`입니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-214">The syntax is `^idx`.</span></span> <span data-ttu-id="0443a-215">목록의 끝에서 요소 1 값을 사용할 수 있는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-215">Here's how you can an element 1 value from the end of a list:</span></span>

```fsharp
let xs = [1..10]

// Get element 1 from the end:
xs.[^1]

// From the end slices

let lastTwoOldStyle = xs.[(xs.Length-2)..]

let lastTwoNewStyle = xs.[^1..]

lastTwoOldStyle = lastTwoNewStyle // true
```

<span data-ttu-id="0443a-216">사용자 고유의 형식에 대해 역방향 인덱스를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-216">You can also define reverse indexes for your own types.</span></span> <span data-ttu-id="0443a-217">이렇게 하려면 다음 메서드를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-217">To do so, you'll need to implement the following method:</span></span>

```fsharp
GetReverseIndex: dimension: int -> offset: int
```

<span data-ttu-id="0443a-218">형식에 대 한 예제는 `Span<'T>` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-218">Here's an example for the `Span<'T>` type:</span></span>

```fsharp
open System

type Span<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

    member sp.GetReverseIndex(_, offset: int) =
        sp.Length - offset

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn $"{arr}"

let run () =
    let sp = [| 1; 2; 3; 4; 5 |].AsSpan()

    // Pre-# 5.0 slicing on a Span<'T>
    printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
    printSpan sp.[..3] // [|1; 2; 3|]
    printSpan sp.[1..3] // |2; 3|]

    // Same slices, but only using from-the-end index
    printSpan sp.[..^0] // [|1; 2; 3; 4; 5|]
    printSpan sp.[..^2] // [|1; 2; 3|]
    printSpan sp.[^4..^2] // [|2; 3|]

run() // Prints the same thing twice
```

<span data-ttu-id="0443a-219">이 기능은 [F # RFC FS-1076](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1076-from-the-end-slicing.md)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-219">This feature implements [F# RFC FS-1076](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1076-from-the-end-slicing.md).</span></span>

## <a name="preview-overloads-of-custom-keywords-in-computation-expressions"></a><span data-ttu-id="0443a-220">미리 보기: 계산 식의 사용자 지정 키워드 오버 로드</span><span class="sxs-lookup"><span data-stu-id="0443a-220">Preview: overloads of custom keywords in computation expressions</span></span>

<span data-ttu-id="0443a-221">계산 식은 라이브러리 및 프레임 워크 작성자를 위한 강력한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-221">Computation expressions are a powerful feature for library and framework authors.</span></span> <span data-ttu-id="0443a-222">잘 알려진 멤버를 정의 하 고 작업 중인 도메인에 대해 DSL을 구성 하 여 구성 요소의 표현을을 크게 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-222">They allow you to greatly improve the expressiveness of your components by letting you define well-known members and form a DSL for the domain you're working in.</span></span>

<span data-ttu-id="0443a-223">F # 5는 계산 식에서 사용자 지정 작업을 오버 로드 하기 위한 미리 보기 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-223">F# 5 adds preview support for overloading custom operations in Computation Expressions.</span></span> <span data-ttu-id="0443a-224">다음 코드를 작성 하 고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-224">It allows the following code to be written and consumed:</span></span>

```fsharp
open System

type InputKind =
    | Text of placeholder:string option
    | Password of placeholder: string option

type InputOptions =
  { Label: string option
    Kind : InputKind
    Validators : (string -> bool) array }

type InputBuilder() =
    member t.Yield(_) =
      { Label = None
        Kind = Text None
        Validators = [||] }

    [<CustomOperation("text")>]
    member this.Text(io, ?placeholder) =
        { io with Kind = Text placeholder }

    [<CustomOperation("password")>]
    member this.Password(io, ?placeholder) =
        { io with Kind = Password placeholder }

    [<CustomOperation("label")>]
    member this.Label(io, label) =
        { io with Label = Some label }

    [<CustomOperation("with_validators")>]
    member this.Validators(io, [<ParamArray>] validators) =
        { io with Validators = validators }

let input = InputBuilder()

let name =
    input {
    label "Name"
    text
    with_validators
        (String.IsNullOrWhiteSpace >> not)
    }

let email =
    input {
    label "Email"
    text "Your email"
    with_validators
        (String.IsNullOrWhiteSpace >> not)
        (fun s -> s.Contains "@")
    }

let password =
    input {
    label "Password"
    password "Must contains at least 6 characters, one number and one uppercase"
    with_validators
        (String.exists Char.IsUpper)
        (String.exists Char.IsDigit)
        (fun s -> s.Length >= 6)
    }
```

<span data-ttu-id="0443a-225">이러한 변경을 수행 하기 전에 `InputBuilder` 형식을 형식으로 작성할 수 있지만 예제에서 사용 하는 방식으로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-225">Prior to this change, you could write the `InputBuilder` type as it is, but you couldn't use it the way it's used in the example.</span></span> <span data-ttu-id="0443a-226">오버 로드, 선택적 매개 변수 및 현재 `System.ParamArray` 형식이 허용 되므로 모든 항목은 예상한 대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-226">Since overloads, optional parameters, and now `System.ParamArray` types are allowed, everything just works as you'd expect it to.</span></span>

<span data-ttu-id="0443a-227">이 기능은 [F # RFC FS-1056](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1056-allow-custom-operation-overloads.md)을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0443a-227">This feature implements [F# RFC FS-1056](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1056-allow-custom-operation-overloads.md).</span></span>
