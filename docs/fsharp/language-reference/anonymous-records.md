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
# <a name="anonymous-records"></a>익명 레코드

익명 레코드는 사용하기 전에 선언할 필요가 없는 명명된 값의 간단한 집계입니다. 구조체 또는 참조 유형으로 선언할 수 있습니다. 기본적으로 참조 형식입니다.

## <a name="syntax"></a>구문

다음 예제에서는 익명 레코드 구문을 보여 줍니다. 항목으로 `[item]` 구분된 항목은 선택 사항입니다.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>기본 사용

익명 레코드는 인스턴스화 전에 선언할 필요가 없는 F# 레코드 유형으로 가장 잘 생각됩니다.

예를 들어 익명 레코드를 생성하는 함수와 상호 작용하는 방법은 다음과 같습니다.

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

다음 예제는 익명 레코드를 입력으로 하는 `printCircleStats` 함수를 통해 이전 예제에서 확장합니다.

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

입력 `printCircleStats` 형식과 동일한 "셰이프"가 없는 익명 레코드 형식을 사용하여 호출하면 컴파일되지 않습니다.

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>구조체 익명 레코드

익명 레코드는 선택적 `struct` 키워드를 사용 하 고 구조체로 정의할 수도 있습니다. 다음 예제는 구조체 익명 레코드를 생성하고 사용하여 이전 레코드를 보강합니다.

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

### <a name="structness-inference"></a>실구조 추론

또한 구조체 익명 레코드를 사용하면 호출 사이트에서 `struct` 키워드를 지정할 필요가 없는 "구조체 추론"도 허용됩니다. 이 예제에서는 호출할 `struct` `printCircleStats`때 키워드를 삭제합니다.

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

역패턴 - 입력 `struct` 형식이 구조체 익명 레코드가 아닌 경우 를 지정하는 것은 컴파일에 실패합니다.

## <a name="embedding-anonymous-records-within-other-types"></a>다른 형식 내에 익명 레코드 포함

사례가 기록인 [차별된 공용 구조체를](discriminated-unions.md) 선언하는 것이 유용합니다. 그러나 레코드의 데이터가 구별된 공용 구조체와 동일한 형식인 경우 모든 형식을 상호 재귀로 정의해야 합니다. 익명 레코드를 사용하면 이러한 제한을 피할 수 있습니다. 다음은 패턴이 일치하는 예제 유형 및 함수입니다.

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

## <a name="copy-and-update-expressions"></a>식 복사 및 업데이트

익명 레코드는 [복사 및 업데이트 식을](copy-and-update-record-expressions.md)통해 구성을 지원합니다. 예를 들어 기존 레코드의 데이터를 복사하는 익명 레코드의 새 인스턴스를 생성하는 방법은 다음과 같습니다.

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

그러나 명명된 레코드와 달리 익명 레코드를 사용하면 복사 및 업데이트 식을 사용하여 완전히 다른 양식을 구성할 수 있습니다. 다음 예제는 이전 예제와 동일한 익명 레코드를 가져와서 새 익명 레코드로 확장합니다.

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

명명된 레코드의 인스턴스에서 익명 레코드를 생성할 수도 있습니다.

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

참조 및 구조체 익명 레코드에서 데이터를 복사할 수도 있습니다.

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

## <a name="properties-of-anonymous-records"></a>익명 레코드의 속성

익명 레코드는 사용 방법을 완전히 이해하는 데 필수적인 여러 가지 특성을 가지고 있습니다.

### <a name="anonymous-records-are-nominal"></a>익명 레코드는 명목상

익명 레코드는 [명목 형식입니다.](https://en.wikipedia.org/wiki/Nominal_type_system) 선행 선언이 필요하지 않은 명명된 [레코드](records.md) 유형(명목상)으로 가장 잘 생각됩니다.

두 개의 익명 레코드 선언을 예로 들어 보겠습니다.

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

`x` 및 `y` 값은 서로 다른 형식을 가지며 서로 호환되지 않습니다. 그들은 동일하지 않으며 비교할 수 없습니다. 이를 설명하기 위해 명명된 레코드를 다음과 같은 것으로 간주하십시오.

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

형식 등가 또는 비교와 관련하여 명명된 레코드 등가물과 비교할 때 익명 레코드에 대해 본질적으로 다른 것은 없습니다.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>익명 레코드는 구조적 같음 및 비교를 사용합니다.

레코드 유형과 마찬가지로 익명 레코드는 구조적으로 동일하며 비교할 수 있습니다. 레코드 형식과 같이 모든 구성 유형이 같음과 비교를 지원하는 경우에만 해당됩니다. 같음 또는 비교를 지원하려면 두 개의 익명 레코드에 동일한 "셰이프"가 있어야 합니다.

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>익명 레코드는 직렬화할 수 있습니다.

명명된 레코드와 마찬가지로 익명 레코드를 직렬화할 수 있습니다. 다음은 [뉴턴소프트.Json을](https://www.nuget.org/packages/Newtonsoft.Json/)사용하는 예입니다.

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip')

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

익명 레코드는 직렬화/역직렬화된 형식에 대한 도메인을 미리 정의할 필요 없이 네트워크를 통해 경량 데이터를 전송하는 데 유용합니다.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>C# 익명 형식과 상호 운용하는 익명 레코드

C# 익명 형식을 사용해야 하는 .NET [API를](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)사용할 수 있습니다. C# 익명 형식은 익명 레코드를 사용하여 상호 운용하는 것은 간단합니다. 다음 예제에서는 익명 레코드를 사용하여 익명 형식이 필요한 [LINQ](../../csharp/programming-guide/concepts/linq/index.md) 오버로드를 호출하는 방법을 보여 주었습니다.

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

.NET 전체에 사용되는 수많은 다른 API가 있으며 익명 형식의 전달을 사용해야 합니다. 익명 레코드는 그들과 함께 작업하기위한 도구입니다.

## <a name="limitations"></a>제한 사항

익명 레코드의 사용에는 몇 가지 제한사항이 있습니다. 일부는 자신의 디자인에 내재되어 있지만, 다른 일부는 변경할 수 있습니다.

### <a name="limitations-with-pattern-matching"></a>패턴 일치의 제한 사항

익명 레코드는 명명된 레코드와 달리 패턴 일치를 지원하지 않습니다. 세 가지 이유가 있습니다.

1. 패턴은 명명된 레코드 유형과 달리 익명 레코드의 모든 필드를 고려해야 합니다. 익명 레코드는 구조적 하위 타이핑을 지원하지 않기 때문에 명목 유형입니다.
2. (1) 때문에 각 고유 패턴이 다른 익명 레코드 형식을 의미하므로 패턴 일치 식에 추가 패턴을 가질 수 없습니다.
3. (3) 때문에 익명 레코드 패턴은 "점" 표기법의 사용보다 더 자세한 것입니다.

[제한된 컨텍스트에서 패턴 일치를 허용하는](https://github.com/fsharp/fslang-suggestions/issues/713)개방형 언어 제안이 있습니다.

### <a name="limitations-with-mutability"></a>변경 가능성의 제한 사항

현재 는 데이터로 `mutable` 익명 레코드를 정의할 수 없습니다. 가변 데이터를 허용하는 [개방형 언어 제안이](https://github.com/fsharp/fslang-suggestions/issues/732) 있습니다.

### <a name="limitations-with-struct-anonymous-records"></a>구조체 익명 레코드의 제한 사항

구조체 익명 레코드를 또는 `IsByRefLike` `IsReadOnly`로 선언할 수 없습니다. 익명 레코드에 대한 `IsByRefLike` [개방형 언어 제안이](https://github.com/fsharp/fslang-suggestions/issues/712) 있습니다. `IsReadOnly`
