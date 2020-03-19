---
title: Byref
description: 낮은 수준의 프로그래밍에 사용되는 F#에서 byref 및 byref와 같은 형식에 대해 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: 527f465ee87fe153a2deae1306b6730531dc4123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187045"
---
# <a name="byrefs"></a>Byref

F# 낮은 수준의 프로그래밍의 공간에서 다루는 두 가지 주요 기능 영역이 있습니다.

* `byref` / 관리되는 `outref` 포인터인 형식입니다. `inref` / 런타임에 유효하지 않은 프로그램을 컴파일할 수 없도록 사용 제한이 있습니다.
* `byref`-like struct는 의미체계와 컴파일 타임 제한이 비슷한 [구조입니다.](structures.md) `byref<'T>` 한 가지 <xref:System.Span%601>예는 .

## <a name="syntax"></a>구문

```fsharp
// Byref types as parameters
let f (x: byref<'T>) = ()
let g (x: inref<'T>) = ()
let h (x: outref<'T>) = ()

// Calling a function with a byref parameter
let mutable x = 3
f &x

// Declaring a byref-like struct
open System.Runtime.CompilerServices

[<Struct; IsByRefLike>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

## <a name="byref-inref-and-outref"></a>바이레프, 인레프, 아웃레프

세 가지 형태가 `byref`있습니다.

* `inref<'T>`- 기본 값을 읽기 위한 관리되는 포인터입니다.
* `outref<'T>`- 기본 값에 쓰기 위한 관리되는 포인터입니다.
* `byref<'T>`- 기본 값을 읽고 쓰기 위한 관리되는 포인터입니다.

`inref<'T>` A는 `byref<'T>` 예상되는 곳에 전달할 수 있습니다. 마찬가지로 a가 `byref<'T>` 예상되는 곳에 `outref<'T>` 전달할 수 있습니다.

## <a name="using-byrefs"></a>바이레프 사용

을 `inref<'T>`사용하려면 `&`다음과 같은 포인터 값을 얻어야 합니다.

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

또는 를 사용하여 포인터에 쓰려면 `mutable`에 대한 포인터를 잡는 값도 만들어야 합니다. `byref<'T>` `outref<'T>`

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

포인터를 읽는 대신 포인터만 쓰는 경우 `outref<'T>` 을 `byref<'T>`사용하는 것이 좋습니다.

### <a name="inref-semantics"></a>인레프 의미론

다음 코드를 살펴보세요.

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

의미상, 이것은 다음을 의미합니다.

* `x` 포인터의 홀더는 값을 읽는 데만 사용할 수 있습니다.
* 내에 `struct` `SomeStruct` 중첩된 필드에 대해 획득한 `inref<_>`모든 포인터에는 형식이 지정됩니다.

다음은 마찬가지입니다.

* 다른 스레드 또는 별칭에 쓰기 액세스 권한이 없다는 `x`의미는 없습니다.
* `inref`. `SomeStruct` `x`

그러나 변경할 수 없는 **are** F# 값 형식의 경우 포인터는 `this` `inref`로 유추됩니다.

이러한 모든 규칙은 `inref` 포인터 의 소유자가 가리키는 메모리의 즉각적인 내용을 수정하지 않을 수 있음을 의미합니다.

### <a name="outref-semantics"></a>아웃레프 의미론

그 `outref<'T>` 목적은 포인터만 작성해야 함을 나타내는 것입니다. 예기치 `outref<'T>` 않게 이름에도 불구하고 기본 값을 읽을 수 있습니다. 이는 호환성을 위한 것입니다. 시상적으로, `outref<'T>` 와 다르지 `byref<'T>`않다.

### <a name="interop-with-c"></a>C와 인터롭\#

C#은 `in ref` `out ref` `ref` 반품 외에도 및 키워드를 지원합니다. 다음 표에서는 F#이 C#이 내하는 것을 해석하는 방법을 보여 주십습니다.

|C# 구문|F # 추론|
|------------|---------|
|`ref`반환 값|`outref<'T>`|
|`ref readonly`반환 값|`inref<'T>`|
|`in ref` 매개 변수|`inref<'T>`|
|`out ref` 매개 변수|`outref<'T>`|

다음 표에서는 F#이 내는지 보여 주십을 보여 주십습니다.

|F# 구문|내보낸 구문|
|------------|-----------------|
|`inref<'T>` 인수|`[In]`인수에 속성|
|`inref<'T>`반환|`modreq`값에 속성|
|`inref<'T>`추상 슬롯 또는 구현|`modreq`인수 또는 반환 시|
|`outref<'T>` 인수|`[Out]`인수에 속성|

### <a name="type-inference-and-overloading-rules"></a>형식 추론 및 오버로드 규칙

`inref<'T>` 다음과 같은 경우 형식은 F# 컴파일러에 의해 유추됩니다.

1. .NET 매개 변수 또는 특성이 있는 return 형식입니다. `IsReadOnly`
2. 변경할 `this` 수 있는 필드가 없는 구조체 형식의 포인터입니다.
3. 다른 `inref<_>` 포인터에서 파생된 메모리 위치의 주소입니다.

an의 `inref` 암시적 주소를 취할 때 형식 `SomeType` 인수가 있는 오버로드는 형식 `inref<SomeType>`인수가 있는 오버로드에 선호됩니다. 다음은 그 예입니다.

```fsharp
type C() =
    static member M(x: System.DateTime) = x.AddDays(1.0)
    static member M(x: inref<System.DateTime>) = x.AddDays(2.0)
    static member M2(x: System.DateTime, y: int) = x.AddDays(1.0)
    static member M2(x: inref<System.DateTime>, y: int) = x.AddDays(2.0)

let res = System.DateTime.Now
let v =  C.M(res)
let v2 =  C.M2(res, 4)
```

두 경우 모두 을 `System.DateTime` 받는 오버로드가 아닌 인차지 하는 오버로드가 `inref<System.DateTime>`해결됩니다.

## <a name="byref-like-structs"></a>바이레프와 같은 구조체

`byref` / `inref` / 트리오 외에도 의미와 같은 의미체계를 준수할 수 있는 `byref`고유한 구조체를 정의할 수 있습니다. `outref` 이 작업은 다음과 <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> 같은 특성으로 수행됩니다.

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike`을 의미하지는 `Struct`않습니다. 둘 다 형식에 있어야 합니다.

F#의 "-like"`byref`구조체는 스택 바인딩된 값 형식입니다. 관리되는 힙에 할당되지 않습니다. `byref`-like 구조체는 수명 및 비캡처에 대한 강력한 검사 집합으로 적용되기 때문에 고성능 프로그래밍에 유용합니다. 규칙은 다음과 같습니다.

* 함수 매개 변수, 메서드 매개 변수, 로컬 변수, 메서드 반환으로 사용할 수 있습니다.
* 정적 또는 인스턴스 멤버가 클래스 또는 일반 구조체일 수 없습니다.
* 모든 클로저 구문(메서드`async` 또는 람다 식)에 의해 캡처할 수 없습니다.
* 일반 매개 변수로 사용할 수 없습니다.

이 마지막 지점은 입력 형식을 매개변수화하는 제네릭 함수와 마찬가지로 `|>` F# 파이프라인 스타일 프로그래밍에 매우 중요합니다. 이 제한은 인라인이며 본문에 인라인되지 않은 제네릭 함수를 호출하지 않으므로 나중에 완화될 `|>` 수 있습니다.

이러한 규칙은 사용을 강력하게 제한하지만 안전한 방식으로 고성능 컴퓨팅의 약속을 이행하기 위해 그렇게 합니다.

## <a name="byref-returns"></a>바이레프 반환

Byref F# 함수 또는 멤버에서 반환 생성 하 고 사용할 수 있습니다. -returning `byref`메서드를 사용 하는 경우 값이 암시적으로 디레참조 됩니다. 다음은 그 예입니다.

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

값 byref를 반환하려면 값을 포함하는 변수가 현재 범위보다 오래 유지되어야 합니다.
또한 byref를 반환하려면 `&value` (값이 현재 범위보다 오래 사는 변수인 경우)를 사용합니다.

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

여러 개의 체인 호출을 통해 참조를 전달하는 것과 같은 `&x` 암시적 디레퍼런스를 방지하려면 (값은 어디에) `x` 사용하십시오.

반환에 `byref`직접 할당할 수도 있습니다. 다음과 같은(매우 명령적인) 프로그램을 고려하십시오.

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override _.ToString() = String.Join(' ', nums)

    member _.FindLargestSmallerThan(target: int) =
        let mutable ctr = nums.Length - 1

        while ctr > 0 && nums.[ctr] >= target do ctr <- ctr - 1

        if ctr > 0 then &nums.[ctr] else &nums.[0]

[<EntryPoint>]
let main argv =
    let c = C()
    printfn "Original sequence: %s" (c.ToString())

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn "New sequence:      %s" (c.ToString())

    0 // return an integer exit code
```

출력은 다음과 같습니다.

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a>바이레프에 대한 범위 지정

`let`-bound 값은 참조가 정의된 범위를 초과할 수 없습니다. 예를 들어 다음을 사용할 수 없습니다.

```fsharp
let test2 () =
    let x = 12
    &x // Error: 'x' exceeds its defined scope!

let test () =
    let x =
        let y = 1
        &y // Error: `y` exceeds its defined scope!
    ()
```

이렇게 하면 최적화를 통해 컴파일하는지 여부에 따라 다른 결과를 얻을 수 없습니다.
