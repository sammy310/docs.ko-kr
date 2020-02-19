---
title: 익명 레코드
description: 데이터 조작을 돕는 언어 기능인 생성을 사용 하 고 익명 레코드를 사용 하는 방법에 대해 알아봅니다.
ms.date: 06/12/2019
ms.openlocfilehash: 061fd3279c84b9a3161c687d9392947ee7ce9c83
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453028"
---
# <a name="anonymous-records"></a>익명 레코드

익명 레코드는 사용 하기 전에 선언 하지 않아도 되는 명명 된 값의 단순 집합체입니다. 구조체 또는 참조 형식 중 하나로 선언할 수 있습니다. 기본적으로 참조 형식입니다.

## <a name="syntax"></a>구문

다음 예제에서는 익명 레코드 구문을 보여 줍니다. `[item]`로 구분 된 항목은 선택 사항입니다.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>기본적인 사용 방법

익명 레코드는 인스턴스화 전에 선언 하지 F# 않아도 되는 레코드 형식으로 간주 됩니다.

예를 들어 다음과 같이 익명 레코드를 생성 하는 함수와 상호 작용할 수 있습니다.

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

다음 예제에서는 익명 레코드를 입력으로 사용 하는 `printCircleStats` 함수를 사용 하 여 이전 예제를 확장 합니다.

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

입력 형식과 동일한 "셰이프"를 포함 하지 않는 익명 레코드 형식으로 `printCircleStats`를 호출 하면 컴파일이 실패 합니다.

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>익명 레코드 구조체

선택적 `struct` 키워드를 사용 하 여 익명 레코드를 구조체로 정의할 수도 있습니다. 다음 예제에서는 구조체 익명 레코드를 생성 하 고 사용 하 여 이전 예제를 보강 합니다.

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

### <a name="structness-inference"></a>Structness 유추

또한 구조체 익명 레코드는 호출 사이트에서 `struct` 키워드를 지정할 필요가 없는 "structness 유추"를 허용 합니다. 이 예제에서는 `printCircleStats`를 호출할 때 `struct` 키워드를 elide 합니다.

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

입력 형식이 구조체 익명 레코드가 아닌 경우 `struct`를 지정 하는 역방향 패턴은 컴파일되지 않습니다.

## <a name="embedding-anonymous-records-within-other-types"></a>다른 형식 내에 익명 레코드 포함

케이스가 레코드 인 구별 된 [공용 구조체](discriminated-unions.md) 를 선언 하는 것이 유용 합니다. 그러나 레코드의 데이터가 구별 된 공용 구조체와 동일한 유형인 경우 모든 형식을 상호 재귀로 정의 해야 합니다. 익명 레코드를 사용 하면 이러한 제한이 방지 됩니다. 다음은 패턴에 일치 하는 형식 및 함수 예제입니다.

```fsharp
type FullName = { FirstName: string; LastName: string }

// Note that using a named for Manager and Executive would require mutually recursive definitions.
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

익명 레코드는 [복사 및 업데이트 식을](copy-and-update-record-expressions.md)사용한 생성을 지원 합니다. 예를 들어 기존 항목의 데이터를 복사 하는 익명 레코드의 새 인스턴스를 생성 하는 방법은 다음과 같습니다.

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

그러나 명명 된 레코드와 달리 익명 레코드를 사용 하면 복사 및 업데이트 식이 있는 완전히 다른 폼을 생성할 수 있습니다. 다음 예제에서는 이전 예제와 동일한 익명 레코드를 사용 하 여 새 익명 레코드로 확장 합니다.

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

또한 명명 된 레코드의 인스턴스에서 익명 레코드를 생성할 수 있습니다.

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

참조 및 구조체 익명 레코드 간에 데이터를 복사할 수도 있습니다.

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

익명 레코드에는 사용할 수 있는 방법을 완전히 이해 하는 데 필요한 여러 가지 특징이 있습니다.

### <a name="anonymous-records-are-nominal"></a>익명 레코드는 명목상입니다.

익명 레코드는 [명목상 형식](https://en.wikipedia.org/wiki/Nominal_type_system)입니다. 이는 사전 선언이 필요 하지 않은 명명 된 [레코드](records.md) 형식 (명목상 이기도 함) 이라고 하는 것이 가장 좋습니다.

다음 예제에서는 두 개의 익명 레코드 선언을 사용 합니다.

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

`x` 및 `y` 값은 서로 다른 형식을 가지 며 서로 호환 되지 않습니다. Equatable 되지 않으며 비교할 수 없습니다. 이를 설명 하기 위해 명명 된 레코드를 동일한 것으로 간주 합니다.

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

형식 동등 또는 비교와 관련 하 여 해당 명명 된 레코드와 비교할 때 익명 레코드에 대해 근본적으로 다른 것은 없습니다.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>익명 레코드는 구조적 같음 및 비교를 사용 합니다.

레코드 형식과 마찬가지로 익명 레코드는 구조적으로 equatable 있고 비교할 수 있습니다. 이는 모든 구성 유형이 레코드 유형과 같이 같음 및 비교를 지 원하는 경우에만 적용 됩니다. 같음 또는 비교를 지원 하려면 두 개의 익명 레코드가 동일한 "셰이프"를 가져야 합니다.

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>익명 레코드는 serialize 할 수 있습니다.

명명 된 레코드를 사용할 때와 마찬가지로 익명 레코드를 직렬화 할 수 있습니다. [Newtonsoft.json](https://www.nuget.org/packages/Newtonsoft.Json/)를 사용 하는 예제는 다음과 같습니다.

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip') 

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

익명 레코드는 직렬화/역직렬화 된 형식에 대 한 도메인을 정의 하지 않고도 네트워크를 통해 경량 데이터를 전송 하는 데 유용 합니다.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>익명 레코드는 C# 익명 형식과 상호 운용 됩니다.

익명 형식을 사용 해야 하는 .net API를 사용할 수 있습니다. [ C# ](../../csharp/programming-guide/classes-and-structs/anonymous-types.md) C#익명 형식은 익명 레코드를 사용 하 여와 상호 운용할 수 있습니다. 다음 예제에서는 익명 레코드를 사용 하 여 무명 형식이 필요한 [LINQ](../../csharp/programming-guide/concepts/linq/index.md) 오버 로드를 호출 하는 방법을 보여 줍니다.

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

.NET 전체에서 사용 되는 다른 Api는 익명 형식으로 전달 해야 합니다. 익명 레코드는 사용할 수 있는 도구입니다.

## <a name="limitations"></a>제한 사항

익명 레코드의 용도에는 몇 가지 제한이 있습니다. 일부는 디자인에 내재 되어 있지만 다른 일부는 변경 적합할.

### <a name="limitations-with-pattern-matching"></a>패턴 일치에 대 한 제한 사항

익명 레코드는 명명 된 레코드와 달리 패턴 일치를 지원 하지 않습니다. 세 가지 이유는 다음과 같습니다.

1. 패턴은 명명 된 레코드 형식과 달리 익명 레코드의 모든 필드를 고려 해야 합니다. 이는 익명 레코드가 구조적 구성은을 지원 하지 않기 때문입니다 .이는 명목상 유형입니다.
2. (1)로 인해 각 고유 패턴이 서로 다른 익명 레코드 형식을 암시 하므로 패턴 일치 식에 추가 패턴을 포함할 수 없습니다.
3. (3)로 인해 모든 익명 레코드 패턴은 "점" 표기법을 사용 하는 것 보다 더 자세한 정보를 표시 합니다.

[제한 된 컨텍스트에서 패턴 일치를 허용](https://github.com/fsharp/fslang-suggestions/issues/713)하는 개방형 언어 제안이 있습니다.

### <a name="limitations-with-mutability"></a>가변성의 제한 사항

현재 `mutable` 데이터를 사용 하 여 익명 레코드를 정의할 수 없습니다. 변경 가능한 데이터를 허용 하는 [개방형 언어 제안이](https://github.com/fsharp/fslang-suggestions/issues/732) 있습니다.

### <a name="limitations-with-struct-anonymous-records"></a>구조체 익명 레코드의 제한 사항

구조체 익명 레코드를 `IsByRefLike` 또는 `IsReadOnly`로 선언할 수 없습니다. `IsByRefLike` 및 `IsReadOnly` 익명 레코드에 대 한 [공개 언어 제안이](https://github.com/fsharp/fslang-suggestions/issues/712) 있습니다.
