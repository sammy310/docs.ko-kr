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
# <a name="whats-new-in-f-50"></a>F# 5.0의 새로운 기능

F # 5.0은 F # 언어 및 F# 대화형에 몇 가지 향상 된 기능을 추가 합니다. **.Net 5** 와 함께 출시 됩니다.

[.NET 다운로드 페이지](https://dotnet.microsoft.com/download)에서 최신 .NET SDK를 다운로드할 수 있습니다.

## <a name="get-started"></a>시작

F # 5.0은 모든 .NET Core 배포 및 Visual Studio 도구에서 사용할 수 있습니다. 자세한 내용은 [F # 시작](../get-started/index.md) 을 참조 하세요.

## <a name="package-references-in-f-scripts"></a>F # 스크립트의 패키지 참조

F # 5는 구문을 사용 하 여 F # 스크립트에서 패키지 참조를 지원 `#r "nuget:..."` 합니다. 예를 들어 다음 패키지 참조를 살펴보겠습니다.

```fsharp
#r "nuget: Newtonsoft.Json"

open Newtonsoft.Json

let o = {| X = 2; Y = "Hello" |}

printfn $"{JsonConvert.SerializeObject o}"
```

패키지 이름 뒤에 다음과 같은 명시적 버전을 제공할 수도 있습니다.

```fsharp
#r "nuget: Newtonsoft.Json,11.0.1"
```

패키지 참조는 ML.NET와 같은 네이티브 종속성이 있는 패키지를 지원 합니다.

패키지 참조는 종속 항목 참조에 대 한 특별 한 요구 사항이 있는 패키지도 지원 `.dll` 합니다. 예를 들어, 사용자가 수동으로 해당 종속이 참조 되었는지 확인 하는 데 사용 되는 [Fparsec](https://www.nuget.org/packages/FParsec/) 패키지는 `FParsecCS.dll` `FParsec.dll` F# 대화형에서 참조 됩니다. 더 이상 필요 하지 않으며 다음과 같이 패키지를 참조할 수 있습니다.

```fsharp
#r "nuget: FParsec"

open FParsec

let test p str =
    match run p str with
    | Success(result, _, _)   -> printfn $"Success: {result}"
    | Failure(errorMsg, _, _) -> printfn $"Failure: {errorMsg}"

test pfloat "1.234"
```

이 기능은 [F # 도구 RFC FST-1027](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1027-fsi-references.md)을 구현 합니다. 패키지 참조에 대 한 자세한 내용은 [F# 대화형](../tools/fsharp-interactive/index.md) 자습서를 참조 하십시오.

## <a name="string-interpolation"></a>문자열 보간

F # 보간된 문자열은 c # 또는 JavaScript 보간된 문자열과 매우 유사 합니다 .이 문자열은 문자열 리터럴 내에서 "구멍"으로 코드를 작성할 수 있도록 합니다. 기본 예제는 다음과 같습니다.

```fsharp
let name = "Phillip"
let age = 29
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

그러나 F # 보간된 문자열은 함수와 마찬가지로 형식화 된 보간를 허용 `sprintf` 하 여 보간된 컨텍스트 내의 식이 특정 형식을 따르는지를 적용 합니다. 동일한 형식 지정자를 사용 합니다.

```fsharp
let name = "Phillip"
let age = 29

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

앞의 형식화 된 보간 예제에서는 `%s` 보간을 형식으로 요구 하는 `string` 반면에는 `%d` 보간이 필요 합니다 `integer` .

또한 임의의 F # 식 (또는 식)을 보간 컨텍스트의 측면에 배치할 수 있습니다. 다음과 같이 더 복잡 한 식을 작성할 수도 있습니다.

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

실제로는이 작업을 수행 하지 않는 것이 좋습니다.

이 기능은 [F # RFC FS-1001](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1001-StringInterpolation.md)을 구현 합니다.

## <a name="support-for-nameof"></a>Nameof에 대 한 지원

F # 5는 `nameof` 사용 되는 기호를 확인 하 고 f # 소스에서 해당 이름을 생성 하는 연산자를 지원 합니다. 이는 로깅과 같은 다양 한 시나리오에서 유용 하며 소스 코드의 변경 내용에 대해 로깅을 보호 합니다.

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

마지막 줄에서는 예외를 throw 하 고 오류 메시지에 "month"가 표시 됩니다.

거의 모든 F # 구문의 이름을 사용할 수 있습니다.

```fsharp
module M =
    let f x = nameof x

printfn $"{M.f 12}"
printfn $"{nameof M}"
printfn $"{nameof M.f}"
```

연산자가 작동 하는 방식에 대 한 세 가지 최종 추가 사항이 변경 되었습니다. `nameof<'type-parameter>` 제네릭 형식 매개 변수에는 폼이 추가 되 고 `nameof` 패턴 일치 식에서는 패턴으로를 사용할 수 있습니다.

연산자의 이름을 사용 하면 해당 소스 문자열이 제공 됩니다. 컴파일된 폼이 필요한 경우에는 연산자의 컴파일된 이름을 사용 합니다.

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

형식 매개 변수의 이름을 사용 하려면 약간 다른 구문이 필요 합니다.

```fsharp
type C<'TType> =
    member _.TypeName = nameof<'TType>
```

이는 `typeof<'T>` 및 연산자와 유사 `typedefof<'T>` 합니다.

또한 F # 5는 `nameof` 식에 사용할 수 있는 패턴에 대 한 지원을 추가 합니다 `match` .

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

이전 코드는 일치 식에서 문자열 리터럴 대신 ' nameof '를 사용 합니다.

이 기능은 [F # RFC FS-1003](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1003-nameof-operator.md)을 구현 합니다.

## <a name="open-type-declarations"></a>개방형 형식 선언

또한 F # 5는 개방형 형식 선언에 대 한 지원을 추가 합니다. 개방형 형식 선언은 F # 의미 체계에 적합 한 몇 가지 다른 구문과 약간 다른 동작을 제외 하 고 c #에서 정적 클래스를 여는 것과 같습니다.

개방형 형식 선언에서는 모든 형식을 사용 하 여 `open` 내부에 정적 콘텐츠를 노출할 수 있습니다. 또한 `open` F #으로 정의 된 공용 구조체 및 레코드를 통해 해당 콘텐츠를 표시할 수 있습니다. 예를 들어, 모듈에 union이 정의 되어 있고 해당 사례에 액세스 하려고 하지만 전체 모듈을 열지 않으려는 경우이 방법이 유용할 수 있습니다.

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

C #과 달리 `open type` 동일한 이름의 멤버를 노출 하는 두 가지 형식을 사용 하는 경우 마지막 형식의 멤버가 `open` 다른 이름을 숨깁니다. 이미 존재 하는 숨김과 관련 된 F # 의미 체계와 일치 합니다.

이 기능은 [F # RFC FS-1068](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1068-open-type-declaration.md)을 구현 합니다.

## <a name="consistent-slicing-behavior-for-built-in-data-types"></a>기본 제공 데이터 형식에 대 한 일관적인 조각화 동작

`FSharp.Core`F # 5 이전에 일관 되지 않은 상태로 사용 되는 기본 제공 데이터 형식 (배열, 목록, 문자열, 2d 배열, 3d 배열, 4d 배열)의 조각화에 대 한 동작입니다. 일부 edge-case 동작에서 예외를 throw 했 고 일부는 그렇지 않습니다. F # 5에서 모든 기본 제공 형식은 이제 생성 하지 못하는 조각에 대 한 빈 조각을 반환 합니다.

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

이 기능은 [F # RFC FS-1077](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-tolerant-slicing.md)을 구현 합니다.

## <a name="fixed-index-slices-for-3d-and-4d-arrays-in-fsharpcore"></a>Fsharp.core에서 3D 및 4D 배열의 고정 인덱스 조각

F # 5.0은 기본 제공 3D 및 4D 배열 형식의 고정 인덱스를 사용 하 여 조각화를 지원 합니다.

이를 설명 하기 위해 다음 3D 배열을 고려 합니다.

*z = 0*
| x\y   | 0 | 1 |
|-------|---|---|
| **0** | 0 | 1 |
| **1** | 2 | 3 |

*z = 1*
| x\y   | 0 | 1 |
|-------|---|---|
| **0** | 4 | 5 |
| **1** | 6 | 7 |

배열에서 조각을 추출 하려면 어떻게 해야 `[| 4; 5 |]` 하나요? 이제 매우 간단 합니다.

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

이 기능은 [F # RFC FS-1077b](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-3d-4d-fixed-index-slicing.md)를 구현 합니다.

## <a name="f-quotations-improvements"></a>F # 인용의 향상 된 기능

이제 F # [코드 인용구](../language-reference/code-quotations.md) 에 형식 제약 조건 정보를 유지 하는 기능이 있습니다. 다음 예제를 참조하세요.

```fsharp
open FSharp.Linq.RuntimeHelpers

let eval q = LeafExpressionConverter.EvaluateQuotation q

let inline negate x = -x
// val inline negate: x: ^a ->  ^a when  ^a : (static member ( ~- ) :  ^a ->  ^a)

<@ negate 1.0 @>  |> eval
```

함수에서 생성 된 제약 조건은 `inline` 코드 따옴표로 유지 됩니다. `negate`이제 함수의 quotated 폼을 평가할 수 있습니다.

이 기능은 [F # RFC FS-1071](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1071-witness-passing-quotations.md)을 구현 합니다.

## <a name="applicative-computation-expressions"></a>Applicative 계산 식

[CEs (계산 식)](../language-reference/computation-expressions.md) 는 오늘날 "상황별 계산"을 모델링 하는 데 사용 되거나 더 함수형 프로그래밍에 익숙한 용어 monadic 계산에 사용 됩니다.

F # 5는 다른 계산 모델을 제공 하는 applicative CEs를 소개 합니다. Applicative CEs를 사용 하면 모든 계산이 독립적이 고 그 결과가 끝에 누적 되어 제공 되는 보다 효율적인 계산을 수행할 수 있습니다. 계산도 서로 독립적 이면 일반적으로 병렬화 되어 CE 작성자가 보다 효율적인 라이브러리를 작성할 수 있습니다. 이 혜택은 제한에서 제공 되지만 이전에 계산 된 값에 의존 하는 계산은 허용 되지 않습니다.

다음 예제에서는 형식에 대 한 기본 applicative CE를 보여 줍니다 `Result` .

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

현재 라이브러리에서 CEs를 노출 하는 라이브러리 작성자 인 경우 주의 해야 할 몇 가지 추가 고려 사항이 있습니다.

이 기능은 [F # RFC FS-1063](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1063-support-letbang-andbang-for-applicative-functors.md)을 구현 합니다.

## <a name="interfaces-can-be-implemented-at-different-generic-instantiations"></a>다른 제네릭 인스턴스화에 인터페이스를 구현할 수 있습니다.

이제 서로 다른 제네릭 인스턴스화에 동일한 인터페이스를 구현할 수 있습니다.

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

이 기능은 [F # RFC FS-1031](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1031-Allow%20implementing%20the%20same%20interface%20at%20different%20generic%20instantiations%20in%20the%20same%20type.md)을 구현 합니다.

## <a name="default-interface-member-consumption"></a>기본 인터페이스 멤버 사용

F # 5를 사용 하면 [기본 구현으로 인터페이스](../../csharp/tutorials/default-interface-methods-versions.md)를 사용할 수 있습니다.

다음과 같이 c #으로 정의 된 인터페이스를 살펴보겠습니다.

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

인터페이스를 구현 하는 표준 방법 중 하나를 통해 F #에서 사용할 수 있습니다.

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

이를 통해 사용자가 기본 구현을 사용할 수 있도록 하는 최신 c #으로 작성 된 c # 코드 및 .NET 구성 요소를 안전 하 게 활용할 수 있습니다.

이 기능은 [F # RFC FS-1074](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1074-default-interface-member-consumption.md)을 구현 합니다.

## <a name="simplified-interop-with-nullable-value-types"></a>Nullable 값 형식을 사용한 간소화 된 interop

[Nullable](https://docs.microsoft.com/dotnet/api/system.nullable-1) 형식 (현재는 nullable 형식 이라고 함)은 F #에서 오래 된 것 이지만 일반적으로 이러한 형식으로 상호 작용 하는 것은 `Nullable` `Nullable<SomeType>` 값을 전달할 때마다 또는 래퍼를 생성 해야 하기 때문에 일반적으로 약간의 어려움입니다. 이제 컴파일러는 `Nullable<ThatValueType>` 대상 형식이와 일치 하는 경우 값 형식을로 암시적으로 변환 합니다. 이제 다음 코드를 사용할 수 있습니다.

```fsharp
#r "nuget: Microsoft.Data.Analysis"

open Microsoft.Data.Analysis

let dateTimes = PrimitiveDataFrameColumn<DateTime>("DateTimes")

// The following line used to fail to compile
dateTimes.Append(DateTime.Parse("2019/01/01"))

// The previous line is now equivalent to this line
dateTimes.Append(Nullable<DateTime>(DateTime.Parse("2019/01/01")))
```

이 기능은 [F # RFC FS-1075](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1075-nullable-interop.md)을 구현 합니다.

## <a name="preview-reverse-indexes"></a>미리 보기: 인덱스 반전

F # 5에는 역방향 인덱스를 허용 하기 위한 미리 보기도 도입 되었습니다. 구문은 `^idx`입니다. 목록의 끝에서 요소 1 값을 사용할 수 있는 방법은 다음과 같습니다.

```fsharp
let xs = [1..10]

// Get element 1 from the end:
xs.[^1]

// From the end slices

let lastTwoOldStyle = xs.[(xs.Length-2)..]

let lastTwoNewStyle = xs.[^1..]

lastTwoOldStyle = lastTwoNewStyle // true
```

사용자 고유의 형식에 대해 역방향 인덱스를 정의할 수도 있습니다. 이렇게 하려면 다음 메서드를 구현 해야 합니다.

```fsharp
GetReverseIndex: dimension: int -> offset: int
```

형식에 대 한 예제는 `Span<'T>` 다음과 같습니다.

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

이 기능은 [F # RFC FS-1076](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1076-from-the-end-slicing.md)을 구현 합니다.

## <a name="preview-overloads-of-custom-keywords-in-computation-expressions"></a>미리 보기: 계산 식의 사용자 지정 키워드 오버 로드

계산 식은 라이브러리 및 프레임 워크 작성자를 위한 강력한 기능입니다. 잘 알려진 멤버를 정의 하 고 작업 중인 도메인에 대해 DSL을 구성 하 여 구성 요소의 표현을을 크게 향상 시킬 수 있습니다.

F # 5는 계산 식에서 사용자 지정 작업을 오버 로드 하기 위한 미리 보기 지원을 추가 합니다. 다음 코드를 작성 하 고 사용할 수 있습니다.

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

이러한 변경을 수행 하기 전에 `InputBuilder` 형식을 형식으로 작성할 수 있지만 예제에서 사용 하는 방식으로는 사용할 수 없습니다. 오버 로드, 선택적 매개 변수 및 현재 `System.ParamArray` 형식이 허용 되므로 모든 항목은 예상한 대로 작동 합니다.

이 기능은 [F # RFC FS-1056](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1056-allow-custom-operation-overloads.md)을 구현 합니다.
