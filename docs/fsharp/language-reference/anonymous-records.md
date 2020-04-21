---
title: 익명 레코드
description: 데이터 조작에 도움이 되는 언어 기능인 익명 레코드를 생성하고 사용하는 방법을 알아봅니다.
ms.date: 06/12/2019
ms.openlocfilehash: 121f0f638dff2ae529b2488d8e3b1ad9c064cf90
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738507"
---
# <a name="anonymous-records"></a><span data-ttu-id="04d48-103">익명 레코드</span><span class="sxs-lookup"><span data-stu-id="04d48-103">Anonymous Records</span></span>

<span data-ttu-id="04d48-104">익명 레코드는 사용하기 전에 선언할 필요가 없는 명명된 값의 간단한 집계입니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-104">Anonymous records are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="04d48-105">구조체 또는 참조 유형으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-105">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="04d48-106">기본적으로 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-106">They're reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="04d48-107">구문</span><span class="sxs-lookup"><span data-stu-id="04d48-107">Syntax</span></span>

<span data-ttu-id="04d48-108">다음 예제에서는 익명 레코드 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-108">The following examples demonstrate the anonymous record syntax.</span></span> <span data-ttu-id="04d48-109">항목으로 `[item]` 구분된 항목은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-109">Items delimited as `[item]` are optional.</span></span>

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a><span data-ttu-id="04d48-110">기본 사용</span><span class="sxs-lookup"><span data-stu-id="04d48-110">Basic usage</span></span>

<span data-ttu-id="04d48-111">익명 레코드는 인스턴스화 전에 선언할 필요가 없는 F# 레코드 유형으로 가장 잘 생각됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-111">Anonymous records are best thought of as F# record types that don't need to be declared before instantiation.</span></span>

<span data-ttu-id="04d48-112">예를 들어 익명 레코드를 생성하는 함수와 상호 작용하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-112">For example, here how you can interact with a function that produces an anonymous record:</span></span>

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

<span data-ttu-id="04d48-113">다음 예제는 익명 레코드를 입력으로 하는 `printCircleStats` 함수를 통해 이전 예제에서 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-113">The following example expands on the previous one with a `printCircleStats` function that takes an anonymous record as input:</span></span>

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

<span data-ttu-id="04d48-114">입력 `printCircleStats` 형식과 동일한 "셰이프"가 없는 익명 레코드 형식을 사용하여 호출하면 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-114">Calling `printCircleStats` with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:</span></span>

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a><span data-ttu-id="04d48-115">구조체 익명 레코드</span><span class="sxs-lookup"><span data-stu-id="04d48-115">Struct anonymous records</span></span>

<span data-ttu-id="04d48-116">익명 레코드는 선택적 `struct` 키워드를 사용 하 고 구조체로 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-116">Anonymous records can also be defined as struct with the optional `struct` keyword.</span></span> <span data-ttu-id="04d48-117">다음 예제는 구조체 익명 레코드를 생성하고 사용하여 이전 레코드를 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-117">The following example augments the previous one by producing and consuming a struct anonymous record:</span></span>

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

### <a name="structness-inference"></a><span data-ttu-id="04d48-118">실구조 추론</span><span class="sxs-lookup"><span data-stu-id="04d48-118">Structness inference</span></span>

<span data-ttu-id="04d48-119">또한 구조체 익명 레코드를 사용하면 호출 사이트에서 `struct` 키워드를 지정할 필요가 없는 "구조체 추론"도 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-119">Struct anonymous records also allow for "structness inference" where you do not need to specify the `struct` keyword at the call site.</span></span> <span data-ttu-id="04d48-120">이 예제에서는 호출할 `struct` `printCircleStats`때 키워드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-120">In this example, you elide the `struct` keyword when calling `printCircleStats`:</span></span>

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

<span data-ttu-id="04d48-121">역패턴 - 입력 `struct` 형식이 구조체 익명 레코드가 아닌 경우 를 지정하는 것은 컴파일에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-121">The reverse pattern - specifying `struct` when the input type is not a struct anonymous record - will fail to compile.</span></span>

## <a name="embedding-anonymous-records-within-other-types"></a><span data-ttu-id="04d48-122">다른 형식 내에 익명 레코드 포함</span><span class="sxs-lookup"><span data-stu-id="04d48-122">Embedding anonymous records within other types</span></span>

<span data-ttu-id="04d48-123">사례가 기록인 [차별된 공용 구조체를](discriminated-unions.md) 선언하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-123">It's useful to declare [discriminated unions](discriminated-unions.md) whose cases are records.</span></span> <span data-ttu-id="04d48-124">그러나 레코드의 데이터가 구별된 공용 구조체와 동일한 형식인 경우 모든 형식을 상호 재귀로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-124">But if the data in the records is the same type as the discriminated union, you must define all types as mutually recursive.</span></span> <span data-ttu-id="04d48-125">익명 레코드를 사용하면 이러한 제한을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-125">Using anonymous records avoids this restriction.</span></span> <span data-ttu-id="04d48-126">다음은 패턴이 일치하는 예제 유형 및 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-126">What follows is an example type and function that pattern matches over it:</span></span>

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

## <a name="copy-and-update-expressions"></a><span data-ttu-id="04d48-127">식 복사 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="04d48-127">Copy and update expressions</span></span>

<span data-ttu-id="04d48-128">익명 레코드는 [복사 및 업데이트 식을](copy-and-update-record-expressions.md)통해 구성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-128">Anonymous records support construction with [copy and update expressions](copy-and-update-record-expressions.md).</span></span> <span data-ttu-id="04d48-129">예를 들어 기존 레코드의 데이터를 복사하는 익명 레코드의 새 인스턴스를 생성하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-129">For example, here's how you can construct a new instance of an anonymous record that copies an existing one's data:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

<span data-ttu-id="04d48-130">그러나 명명된 레코드와 달리 익명 레코드를 사용하면 복사 및 업데이트 식을 사용하여 완전히 다른 양식을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-130">However, unlike named records, anonymous records allow you to construct entirely different forms with copy and update expressions.</span></span> <span data-ttu-id="04d48-131">다음 예제는 이전 예제와 동일한 익명 레코드를 가져와서 새 익명 레코드로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-131">The follow example takes the same anonymous record from the previous example and expands it into a new anonymous record:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

<span data-ttu-id="04d48-132">명명된 레코드의 인스턴스에서 익명 레코드를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-132">It is also possible to construct anonymous records from instances of named records:</span></span>

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

<span data-ttu-id="04d48-133">참조 및 구조체 익명 레코드에서 데이터를 복사할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-133">You can also copy data to and from reference and struct anonymous records:</span></span>

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

## <a name="properties-of-anonymous-records"></a><span data-ttu-id="04d48-134">익명 레코드의 속성</span><span class="sxs-lookup"><span data-stu-id="04d48-134">Properties of anonymous records</span></span>

<span data-ttu-id="04d48-135">익명 레코드는 사용 방법을 완전히 이해하는 데 필수적인 여러 가지 특성을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-135">Anonymous records have a number of characteristics that are essential to fully understanding how they can be used.</span></span>

### <a name="anonymous-records-are-nominal"></a><span data-ttu-id="04d48-136">익명 레코드는 명목상</span><span class="sxs-lookup"><span data-stu-id="04d48-136">Anonymous records are nominal</span></span>

<span data-ttu-id="04d48-137">익명 레코드는 [명목 형식입니다.](https://en.wikipedia.org/wiki/Nominal_type_system)</span><span class="sxs-lookup"><span data-stu-id="04d48-137">Anonymous records are [nominal types](https://en.wikipedia.org/wiki/Nominal_type_system).</span></span> <span data-ttu-id="04d48-138">선행 선언이 필요하지 않은 명명된 [레코드](records.md) 유형(명목상)으로 가장 잘 생각됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-138">They are best thought as named [record](records.md) types (which are also nominal) that do not require an up-front declaration.</span></span>

<span data-ttu-id="04d48-139">두 개의 익명 레코드 선언을 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-139">Consider the following example with two anonymous record declarations:</span></span>

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

<span data-ttu-id="04d48-140">`x` 및 `y` 값은 서로 다른 형식을 가지며 서로 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-140">The `x` and `y` values have different types and are not compatible with one another.</span></span> <span data-ttu-id="04d48-141">그들은 동일하지 않으며 비교할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-141">They are not equatable and they are not comparable.</span></span> <span data-ttu-id="04d48-142">이를 설명하기 위해 명명된 레코드를 다음과 같은 것으로 간주하십시오.</span><span class="sxs-lookup"><span data-stu-id="04d48-142">To illustrate this, consider a named record equivalent:</span></span>

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

<span data-ttu-id="04d48-143">형식 등가 또는 비교와 관련하여 명명된 레코드 등가물과 비교할 때 익명 레코드에 대해 본질적으로 다른 것은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-143">There isn't anything inherently different about anonymous records when compared with their named record equivalents when concerning type equivalency or comparison.</span></span>

### <a name="anonymous-records-use-structural-equality-and-comparison"></a><span data-ttu-id="04d48-144">익명 레코드는 구조적 같음 및 비교를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-144">Anonymous records use structural equality and comparison</span></span>

<span data-ttu-id="04d48-145">레코드 유형과 마찬가지로 익명 레코드는 구조적으로 동일하며 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-145">Like record types, anonymous records are structurally equatable and comparable.</span></span> <span data-ttu-id="04d48-146">레코드 형식과 같이 모든 구성 유형이 같음과 비교를 지원하는 경우에만 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-146">This is only true if all constituent types support equality and comparison, like with record types.</span></span> <span data-ttu-id="04d48-147">같음 또는 비교를 지원하려면 두 개의 익명 레코드에 동일한 "셰이프"가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-147">To support equality or comparison, two anonymous records must have the same "shape".</span></span>

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a><span data-ttu-id="04d48-148">익명 레코드는 직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-148">Anonymous records are serializable</span></span>

<span data-ttu-id="04d48-149">명명된 레코드와 마찬가지로 익명 레코드를 직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-149">You can serialize anonymous records just as you can with named records.</span></span> <span data-ttu-id="04d48-150">다음은 [뉴턴소프트.Json을](https://www.nuget.org/packages/Newtonsoft.Json/)사용하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-150">Here is an example using [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span></span>

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip')

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

<span data-ttu-id="04d48-151">익명 레코드는 직렬화/역직렬화된 형식에 대한 도메인을 미리 정의할 필요 없이 네트워크를 통해 경량 데이터를 전송하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-151">Anonymous records are useful for sending lightweight data over a network without the need to define a domain for your serialized/deserialized types up front.</span></span>

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a><span data-ttu-id="04d48-152">C# 익명 형식과 상호 운용하는 익명 레코드</span><span class="sxs-lookup"><span data-stu-id="04d48-152">Anonymous records interoperate with C# anonymous types</span></span>

<span data-ttu-id="04d48-153">C# 익명 형식을 사용해야 하는 .NET [API를](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-153">It is possible to use a .NET API that requires the use of [C# anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="04d48-154">C# 익명 형식은 익명 레코드를 사용하여 상호 운용하는 것은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-154">C# anonymous types are trivial to interoperate with by using anonymous records.</span></span> <span data-ttu-id="04d48-155">다음 예제에서는 익명 레코드를 사용하여 익명 형식이 필요한 [LINQ](../../csharp/programming-guide/concepts/linq/index.md) 오버로드를 호출하는 방법을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-155">The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:</span></span>

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

<span data-ttu-id="04d48-156">.NET 전체에 사용되는 수많은 다른 API가 있으며 익명 형식의 전달을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-156">There are a multitude of other APIs used throughout .NET that require the use of passing in an anonymous type.</span></span> <span data-ttu-id="04d48-157">익명 레코드는 그들과 함께 작업하기위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-157">Anonymous records are your tool for working with them.</span></span>

## <a name="limitations"></a><span data-ttu-id="04d48-158">제한 사항</span><span class="sxs-lookup"><span data-stu-id="04d48-158">Limitations</span></span>

<span data-ttu-id="04d48-159">익명 레코드의 사용에는 몇 가지 제한사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-159">Anonymous records have some restrictions in their usage.</span></span> <span data-ttu-id="04d48-160">일부는 자신의 디자인에 내재되어 있지만, 다른 일부는 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-160">Some are inherent to their design, but others are amenable to change.</span></span>

### <a name="limitations-with-pattern-matching"></a><span data-ttu-id="04d48-161">패턴 일치의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="04d48-161">Limitations with pattern matching</span></span>

<span data-ttu-id="04d48-162">익명 레코드는 명명된 레코드와 달리 패턴 일치를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-162">Anonymous records do not support pattern matching, unlike named records.</span></span> <span data-ttu-id="04d48-163">세 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-163">There are three reasons:</span></span>

1. <span data-ttu-id="04d48-164">패턴은 명명된 레코드 유형과 달리 익명 레코드의 모든 필드를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-164">A pattern would have to account for every field of an anonymous record, unlike named record types.</span></span> <span data-ttu-id="04d48-165">익명 레코드는 구조적 하위 타이핑을 지원하지 않기 때문에 명목 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-165">This is because anonymous records do not support structural subtyping – they are nominal types.</span></span>
2. <span data-ttu-id="04d48-166">(1) 때문에 각 고유 패턴이 다른 익명 레코드 형식을 의미하므로 패턴 일치 식에 추가 패턴을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-166">Because of (1), there is no ability to have additional patterns in a pattern match expression, as each distinct pattern would imply a different anonymous record type.</span></span>
3. <span data-ttu-id="04d48-167">(3) 때문에 익명 레코드 패턴은 "점" 표기법의 사용보다 더 자세한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-167">Because of (3), any anonymous record pattern would be more verbose than the use of “dot” notation.</span></span>

<span data-ttu-id="04d48-168">[제한된 컨텍스트에서 패턴 일치를 허용하는](https://github.com/fsharp/fslang-suggestions/issues/713)개방형 언어 제안이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-168">There is an open language suggestion to [allow pattern matching in limited contexts](https://github.com/fsharp/fslang-suggestions/issues/713).</span></span>

### <a name="limitations-with-mutability"></a><span data-ttu-id="04d48-169">변경 가능성의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="04d48-169">Limitations with mutability</span></span>

<span data-ttu-id="04d48-170">현재 는 데이터로 `mutable` 익명 레코드를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-170">It is not currently possible to define an anonymous record with `mutable` data.</span></span> <span data-ttu-id="04d48-171">가변 데이터를 허용하는 [개방형 언어 제안이](https://github.com/fsharp/fslang-suggestions/issues/732) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-171">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/732) to allow mutable data.</span></span>

### <a name="limitations-with-struct-anonymous-records"></a><span data-ttu-id="04d48-172">구조체 익명 레코드의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="04d48-172">Limitations with struct anonymous records</span></span>

<span data-ttu-id="04d48-173">구조체 익명 레코드를 또는 `IsByRefLike` `IsReadOnly`로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04d48-173">It is not possible to declare struct anonymous records as `IsByRefLike` or `IsReadOnly`.</span></span> <span data-ttu-id="04d48-174">익명 레코드에 대한 `IsByRefLike` [개방형 언어 제안이](https://github.com/fsharp/fslang-suggestions/issues/712) 있습니다. `IsReadOnly`</span><span class="sxs-lookup"><span data-stu-id="04d48-174">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/712) to for `IsByRefLike` and `IsReadOnly` anonymous records.</span></span>
