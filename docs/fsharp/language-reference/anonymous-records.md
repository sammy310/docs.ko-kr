---
title: 익명 레코드
description: 데이터 조작을 돕는 언어 기능인 생성을 사용 하 고 익명 레코드를 사용 하는 방법에 대해 알아봅니다.
ms.date: 06/12/2019
ms.openlocfilehash: 13950048f02ab74362f8174725f5f8615d9d7654
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739817"
---
# <a name="anonymous-records"></a><span data-ttu-id="4237b-103">익명 레코드</span><span class="sxs-lookup"><span data-stu-id="4237b-103">Anonymous Records</span></span>

<span data-ttu-id="4237b-104">익명 레코드는 사용 하기 전에 선언 하지 않아도 되는 명명 된 값의 단순 집합체입니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-104">Anonymous records are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="4237b-105">구조체 또는 참조 형식 중 하나로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-105">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="4237b-106">기본적으로 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-106">They're reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="4237b-107">구문</span><span class="sxs-lookup"><span data-stu-id="4237b-107">Syntax</span></span>

<span data-ttu-id="4237b-108">다음 예제에서는 익명 레코드 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-108">The following examples demonstrate the anonymous record syntax.</span></span> <span data-ttu-id="4237b-109">로 구분 `[item]` 된 항목은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-109">Items delimited as `[item]` are optional.</span></span>

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a><span data-ttu-id="4237b-110">기본 사용법</span><span class="sxs-lookup"><span data-stu-id="4237b-110">Basic usage</span></span>

<span data-ttu-id="4237b-111">익명 레코드는 인스턴스화 전에 선언 하지 않아도 되는 F # 레코드 형식으로 가장 잘 생각 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-111">Anonymous records are best thought of as F# record types that don't need to be declared before instantiation.</span></span>

<span data-ttu-id="4237b-112">예를 들어 다음과 같이 익명 레코드를 생성 하는 함수와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-112">For example, here how you can interact with a function that produces an anonymous record:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

<span data-ttu-id="4237b-113">다음 예제에서는 `printCircleStats` 익명 레코드를 입력으로 사용 하는 함수를 사용 하 여 이전 예제를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-113">The following example expands on the previous one with a `printCircleStats` function that takes an anonymous record as input:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let printCircleStats r (stats: {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

<span data-ttu-id="4237b-114">`printCircleStats`입력 형식과 동일한 "셰이프"를 포함 하지 않는 익명 레코드 형식을 사용 하 여를 호출 하면 컴파일이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-114">Calling `printCircleStats` with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:</span></span>

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a><span data-ttu-id="4237b-115">익명 레코드 구조체</span><span class="sxs-lookup"><span data-stu-id="4237b-115">Struct anonymous records</span></span>

<span data-ttu-id="4237b-116">선택적 키워드를 사용 하 여 익명 레코드를 구조체로 정의할 수도 있습니다 `struct` .</span><span class="sxs-lookup"><span data-stu-id="4237b-116">Anonymous records can also be defined as struct with the optional `struct` keyword.</span></span> <span data-ttu-id="4237b-117">다음 예제에서는 구조체 익명 레코드를 생성 하 고 사용 하 여 이전 예제를 보강 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-117">The following example augments the previous one by producing and consuming a struct anonymous record:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    // Note that the keyword comes before the '{| |}' brace pair
    struct {| Area = a; Circumference = c; Diameter = d |}

// the 'struct' keyword also comes before the '{| |}' brace pair when declaring the parameter type
let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

### <a name="structness-inference"></a><span data-ttu-id="4237b-118">Structness 유추</span><span class="sxs-lookup"><span data-stu-id="4237b-118">Structness inference</span></span>

<span data-ttu-id="4237b-119">또한 구조체 익명 레코드는 호출 사이트에서 키워드를 지정할 필요가 없는 "structness 유추"를 허용 `struct` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-119">Struct anonymous records also allow for "structness inference" where you do not need to specify the `struct` keyword at the call site.</span></span> <span data-ttu-id="4237b-120">이 예제에서는를 `struct` 호출할 때 키워드를 elide 합니다 `printCircleStats` .</span><span class="sxs-lookup"><span data-stu-id="4237b-120">In this example, you elide the `struct` keyword when calling `printCircleStats`:</span></span>

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

<span data-ttu-id="4237b-121">`struct`입력 형식이 구조체 익명 레코드가 아닌 경우를 지정 하는 역방향 패턴은 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-121">The reverse pattern - specifying `struct` when the input type is not a struct anonymous record - will fail to compile.</span></span>

## <a name="embedding-anonymous-records-within-other-types"></a><span data-ttu-id="4237b-122">다른 형식 내에 익명 레코드 포함</span><span class="sxs-lookup"><span data-stu-id="4237b-122">Embedding anonymous records within other types</span></span>

<span data-ttu-id="4237b-123">케이스가 레코드 인 구별 된 [공용 구조체](discriminated-unions.md) 를 선언 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-123">It's useful to declare [discriminated unions](discriminated-unions.md) whose cases are records.</span></span> <span data-ttu-id="4237b-124">그러나 레코드의 데이터가 구별 된 공용 구조체와 동일한 유형인 경우 모든 형식을 상호 재귀로 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-124">But if the data in the records is the same type as the discriminated union, you must define all types as mutually recursive.</span></span> <span data-ttu-id="4237b-125">익명 레코드를 사용 하면 이러한 제한이 방지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-125">Using anonymous records avoids this restriction.</span></span> <span data-ttu-id="4237b-126">다음은 패턴에 일치 하는 형식 및 함수 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-126">What follows is an example type and function that pattern matches over it:</span></span>

```fsharp
type FullName = { FirstName: string; LastName: string }

// Note that using a named record for Manager and Executive would require mutually recursive definitions.
type Employee =
    | Engineer of FullName
    | Manager of {| Name: FullName; Reports: Employee list |}
    | Executive of {| Name: FullName; Reports: Employee list; Assistant: Employee |}

let getFirstName e =
    match e with
    | Engineer fullName -> fullName.FirstName
    | Manager m -> m.Name.FirstName
    | Executive ex -> ex.Name.FirstName
```

## <a name="copy-and-update-expressions"></a><span data-ttu-id="4237b-127">식 복사 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="4237b-127">Copy and update expressions</span></span>

<span data-ttu-id="4237b-128">익명 레코드는 [복사 및 업데이트 식을](copy-and-update-record-expressions.md)사용한 생성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-128">Anonymous records support construction with [copy and update expressions](copy-and-update-record-expressions.md).</span></span> <span data-ttu-id="4237b-129">예를 들어 기존 항목의 데이터를 복사 하는 익명 레코드의 새 인스턴스를 생성 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-129">For example, here's how you can construct a new instance of an anonymous record that copies an existing one's data:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

<span data-ttu-id="4237b-130">그러나 명명 된 레코드와 달리 익명 레코드를 사용 하면 복사 및 업데이트 식이 있는 완전히 다른 폼을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-130">However, unlike named records, anonymous records allow you to construct entirely different forms with copy and update expressions.</span></span> <span data-ttu-id="4237b-131">다음 예제에서는 이전 예제와 동일한 익명 레코드를 사용 하 여 새 익명 레코드로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-131">The follow example takes the same anonymous record from the previous example and expands it into a new anonymous record:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

<span data-ttu-id="4237b-132">또한 명명 된 레코드의 인스턴스에서 익명 레코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-132">It is also possible to construct anonymous records from instances of named records:</span></span>

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

<span data-ttu-id="4237b-133">참조 및 구조체 익명 레코드 간에 데이터를 복사할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-133">You can also copy data to and from reference and struct anonymous records:</span></span>

```fsharp
// Copy data from a reference record into a struct anonymous record
type R1 = { X: int }
let r1 = { X = 1 }

let data1 = struct {| r1 with Y = 1 |}

// Copy data from a struct record into a reference anonymous record
[<Struct>]
type R2 = { X: int }
let r2 = { X = 1 }

let data2 = {| r1 with Y = 1 |}

// Copy the reference anonymous record data into a struct anonymous record
let data3 = struct {| data2 with Z = r2.X |}
```

## <a name="properties-of-anonymous-records"></a><span data-ttu-id="4237b-134">익명 레코드의 속성</span><span class="sxs-lookup"><span data-stu-id="4237b-134">Properties of anonymous records</span></span>

<span data-ttu-id="4237b-135">익명 레코드에는 사용할 수 있는 방법을 완전히 이해 하는 데 필요한 여러 가지 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-135">Anonymous records have a number of characteristics that are essential to fully understanding how they can be used.</span></span>

### <a name="anonymous-records-are-nominal"></a><span data-ttu-id="4237b-136">익명 레코드는 명목상입니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-136">Anonymous records are nominal</span></span>

<span data-ttu-id="4237b-137">익명 레코드는 [명목상 형식](https://en.wikipedia.org/wiki/Nominal_type_system)입니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-137">Anonymous records are [nominal types](https://en.wikipedia.org/wiki/Nominal_type_system).</span></span> <span data-ttu-id="4237b-138">이는 사전 선언이 필요 하지 않은 명명 된 [레코드](records.md) 형식 (명목상 이기도 함) 이라고 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-138">They are best thought as named [record](records.md) types (which are also nominal) that do not require an up-front declaration.</span></span>

<span data-ttu-id="4237b-139">다음 예제에서는 두 개의 익명 레코드 선언을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-139">Consider the following example with two anonymous record declarations:</span></span>

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

<span data-ttu-id="4237b-140">`x`및 `y` 값은 서로 다른 형식을 가지 며 서로 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-140">The `x` and `y` values have different types and are not compatible with one another.</span></span> <span data-ttu-id="4237b-141">Equatable 되지 않으며 비교할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-141">They are not equatable and they are not comparable.</span></span> <span data-ttu-id="4237b-142">이를 설명 하기 위해 명명 된 레코드를 동일한 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-142">To illustrate this, consider a named record equivalent:</span></span>

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

<span data-ttu-id="4237b-143">형식 동등 또는 비교와 관련 하 여 해당 명명 된 레코드와 비교할 때 익명 레코드에 대해 근본적으로 다른 것은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-143">There isn't anything inherently different about anonymous records when compared with their named record equivalents when concerning type equivalency or comparison.</span></span>

### <a name="anonymous-records-use-structural-equality-and-comparison"></a><span data-ttu-id="4237b-144">익명 레코드는 구조적 같음 및 비교를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-144">Anonymous records use structural equality and comparison</span></span>

<span data-ttu-id="4237b-145">레코드 형식과 마찬가지로 익명 레코드는 구조적으로 equatable 있고 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-145">Like record types, anonymous records are structurally equatable and comparable.</span></span> <span data-ttu-id="4237b-146">이는 모든 구성 유형이 레코드 유형과 같이 같음 및 비교를 지 원하는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-146">This is only true if all constituent types support equality and comparison, like with record types.</span></span> <span data-ttu-id="4237b-147">같음 또는 비교를 지원 하려면 두 개의 익명 레코드가 동일한 "셰이프"를 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-147">To support equality or comparison, two anonymous records must have the same "shape".</span></span>

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a><span data-ttu-id="4237b-148">익명 레코드는 serialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-148">Anonymous records are serializable</span></span>

<span data-ttu-id="4237b-149">명명 된 레코드를 사용할 때와 마찬가지로 익명 레코드를 직렬화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-149">You can serialize anonymous records just as you can with named records.</span></span> <span data-ttu-id="4237b-150">[에서Newtonsoft.Js를](https://www.nuget.org/packages/Newtonsoft.Json/)사용 하는 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-150">Here is an example using [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span></span>

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip')

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn $"Name: {phillip.name} Age: %d{phillip.age}"
```

<span data-ttu-id="4237b-151">익명 레코드는 직렬화/역직렬화 된 형식에 대 한 도메인을 정의 하지 않고도 네트워크를 통해 경량 데이터를 전송 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-151">Anonymous records are useful for sending lightweight data over a network without the need to define a domain for your serialized/deserialized types up front.</span></span>

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a><span data-ttu-id="4237b-152">익명 레코드는 c # 익명 형식과 상호 운용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-152">Anonymous records interoperate with C# anonymous types</span></span>

<span data-ttu-id="4237b-153">[C # 익명 형식을](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)사용 해야 하는 .net API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-153">It is possible to use a .NET API that requires the use of [C# anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="4237b-154">C # 무명 형식은 익명 레코드를 사용 하 여와 상호 운용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-154">C# anonymous types are trivial to interoperate with by using anonymous records.</span></span> <span data-ttu-id="4237b-155">다음 예제에서는 익명 레코드를 사용 하 여 무명 형식이 필요한 [LINQ](../../csharp/programming-guide/concepts/linq/index.md) 오버 로드를 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-155">The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:</span></span>

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn $"{ng.Name} has first letter {ng.FirstLetter}"
```

<span data-ttu-id="4237b-156">.NET 전체에서 사용 되는 다른 Api는 익명 형식으로 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-156">There are a multitude of other APIs used throughout .NET that require the use of passing in an anonymous type.</span></span> <span data-ttu-id="4237b-157">익명 레코드는 사용할 수 있는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-157">Anonymous records are your tool for working with them.</span></span>

## <a name="limitations"></a><span data-ttu-id="4237b-158">제한 사항</span><span class="sxs-lookup"><span data-stu-id="4237b-158">Limitations</span></span>

<span data-ttu-id="4237b-159">익명 레코드의 용도에는 몇 가지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-159">Anonymous records have some restrictions in their usage.</span></span> <span data-ttu-id="4237b-160">일부는 디자인에 내재 되어 있지만 다른 일부는 변경 적합할.</span><span class="sxs-lookup"><span data-stu-id="4237b-160">Some are inherent to their design, but others are amenable to change.</span></span>

### <a name="limitations-with-pattern-matching"></a><span data-ttu-id="4237b-161">패턴 일치에 대 한 제한 사항</span><span class="sxs-lookup"><span data-stu-id="4237b-161">Limitations with pattern matching</span></span>

<span data-ttu-id="4237b-162">익명 레코드는 명명 된 레코드와 달리 패턴 일치를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-162">Anonymous records do not support pattern matching, unlike named records.</span></span> <span data-ttu-id="4237b-163">세 가지 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-163">There are three reasons:</span></span>

1. <span data-ttu-id="4237b-164">패턴은 명명 된 레코드 형식과 달리 익명 레코드의 모든 필드를 고려 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-164">A pattern would have to account for every field of an anonymous record, unlike named record types.</span></span> <span data-ttu-id="4237b-165">이는 익명 레코드가 구조적 구성은을 지원 하지 않기 때문입니다 .이는 명목상 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-165">This is because anonymous records do not support structural subtyping – they are nominal types.</span></span>
2. <span data-ttu-id="4237b-166">(1)로 인해 각 고유 패턴이 서로 다른 익명 레코드 형식을 암시 하므로 패턴 일치 식에 추가 패턴을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-166">Because of (1), there is no ability to have additional patterns in a pattern match expression, as each distinct pattern would imply a different anonymous record type.</span></span>
3. <span data-ttu-id="4237b-167">(3)로 인해 모든 익명 레코드 패턴은 "점" 표기법을 사용 하는 것 보다 더 자세한 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-167">Because of (3), any anonymous record pattern would be more verbose than the use of “dot” notation.</span></span>

<span data-ttu-id="4237b-168">[제한 된 컨텍스트에서 패턴 일치를 허용](https://github.com/fsharp/fslang-suggestions/issues/713)하는 개방형 언어 제안이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-168">There is an open language suggestion to [allow pattern matching in limited contexts](https://github.com/fsharp/fslang-suggestions/issues/713).</span></span>

### <a name="limitations-with-mutability"></a><span data-ttu-id="4237b-169">가변성의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="4237b-169">Limitations with mutability</span></span>

<span data-ttu-id="4237b-170">현재는 데이터를 사용 하 여 익명 레코드를 정의할 수 없습니다 `mutable` .</span><span class="sxs-lookup"><span data-stu-id="4237b-170">It is not currently possible to define an anonymous record with `mutable` data.</span></span> <span data-ttu-id="4237b-171">변경 가능한 데이터를 허용 하는 [개방형 언어 제안이](https://github.com/fsharp/fslang-suggestions/issues/732) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4237b-171">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/732) to allow mutable data.</span></span>

### <a name="limitations-with-struct-anonymous-records"></a><span data-ttu-id="4237b-172">구조체 익명 레코드의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="4237b-172">Limitations with struct anonymous records</span></span>

<span data-ttu-id="4237b-173">구조체 익명 레코드는 또는로 선언할 수 없습니다 `IsByRefLike` `IsReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="4237b-173">It is not possible to declare struct anonymous records as `IsByRefLike` or `IsReadOnly`.</span></span> <span data-ttu-id="4237b-174">및 익명 레코드에 대 한 [공개 언어 제안이](https://github.com/fsharp/fslang-suggestions/issues/712) 있습니다 `IsByRefLike` `IsReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="4237b-174">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/712) to for `IsByRefLike` and `IsReadOnly` anonymous records.</span></span>
