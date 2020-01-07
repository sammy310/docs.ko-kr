---
title: Byref
description: 하위 수준 프로그래밍에 사용 되는의 F#byref 및 byref와 유사한 형식에 대해 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: a6d3d69c4a163be9ecef7e33c284c4a73e800405
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545126"
---
# <a name="byrefs"></a>Byref

F#에는 하위 수준 프로그래밍의 공간을 처리 하는 두 가지 주요 기능 영역이 있습니다.

* `byref`/는 관리 되는 포인터인 `inref`/`outref` 형식입니다. 런타임에 잘못 된 프로그램을 컴파일할 수 없도록 사용에 대 한 제한 사항이 있습니다.
* 의미 체계가 비슷하며 `byref<'T>`와 동일한 컴파일 시간 제한이 있는 [구조인](structures.md) `byref`같은 구조체입니다. 한 가지 예는 <xref:System.Span%601>입니다.

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

## <a name="byref-inref-and-outref"></a>Byref, inref 및 outref

다음과 같은 세 가지 형식의 `byref`있습니다.

* `inref<'T>`내부 값을 읽기 위한 관리 되는 포인터입니다.
* `outref<'T>`기본 값에 쓰기 위한 관리 되는 포인터입니다.
* 기본 값을 읽고 쓰기 위한 관리 되는 포인터인 `byref<'T>`입니다.

`byref<'T>` `inref<'T>` 필요한 위치에 전달할 수 있습니다. 마찬가지로 `outref<'T>` 필요한 위치에 `byref<'T>`를 전달할 수도 있습니다.

## <a name="using-byrefs"></a>Byref 배열과 같은 사용

`inref<'T>`을 사용 하려면 `&`를 사용 하 여 포인터 값을 가져와야 합니다.

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

`outref<'T>` 또는 `byref<'T>`를 사용 하 여 포인터에 쓰려면 `mutable`포인터를 가져오는 값도 설정 해야 합니다.

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

포인터를 읽는 대신만 작성 하는 경우에는 `byref<'T>`대신 `outref<'T>`를 사용 하는 것이 좋습니다.

### <a name="inref-semantics"></a>Inref 의미 체계

다음 코드를 살펴보세요.

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

의미 체계가 며,이는 다음을 의미 합니다.

* `x` 포인터의 소유자는이 값만 사용 하 여 값을 읽을 수 있습니다.
* `SomeStruct` 내에 중첩 된 `struct` 필드를 가져오는 모든 포인터에는 `inref<_>`형식이 지정 됩니다.

다음도 마찬가지입니다.

* 다른 스레드나 별칭에는 `x`에 대 한 쓰기 권한이 없다는 의미는 없습니다.
* `inref``x` 덕분에 `SomeStruct`를 변경할 수 없다는 의미는 없습니다.

그러나 변경할 수 F# **없는 값** 형식의 경우 `this` 포인터는 `inref`으로 유추 됩니다.

이러한 모든 규칙은 `inref` 포인터의 소유자가 가리키는 메모리의 즉시 콘텐츠를 수정할 수 없음을 의미 합니다.

### <a name="outref-semantics"></a>Outref 의미 체계

`outref<'T>` 목적은 포인터를에만 써야 함을 나타내는 것입니다. 예기치 않게 `outref<'T>`는 이름에도 불구 하 고 기본 값을 읽을 수 있습니다. 이는 호환성을 위해 제공 됩니다. 의미 체계가 `outref<'T>` `byref<'T>`와 다릅니다.

### <a name="interop-with-c"></a>C\# 상호 운용성

C#`ref` 반환 하는 것 외에도 `in ref` 및 `out ref` 키워드를 지원 합니다. 다음 표에서는에서 내보내는 F# 항목 C# 을 해석 하는 방법을 보여 줍니다.

|C#구축|F#어떻게|
|------------|---------|
|반환 값 `ref`|`outref<'T>`|
|반환 값 `ref readonly`|`inref<'T>`|
|`in ref` 매개 변수|`inref<'T>`|
|`out ref` 매개 변수|`outref<'T>`|

다음 표에서는 내보내는 항목 F# 을 보여 줍니다.

|F#구축|내보낸 구문|
|------------|-----------------|
|`inref<'T>` 인수|인수의 `[In]` 특성|
|반환 `inref<'T>`|값의 `modreq` 특성|
|추상 슬롯 또는 구현에서 `inref<'T>`|인수에 `modreq` 또는 반환|
|`outref<'T>` 인수|인수의 `[Out]` 특성|

### <a name="type-inference-and-overloading-rules"></a>형식 유추 및 오버 로드 규칙

다음 경우에는 F# 컴파일러에서 `inref<'T>` 형식을 유추 합니다.

1. `IsReadOnly` 특성이 있는 .NET 매개 변수 또는 반환 형식입니다.
2. 변경할 필드가 없는 구조체 형식의 `this` 포인터입니다.
3. 다른 `inref<_>` 포인터에서 파생 된 메모리 위치의 주소입니다.

`inref`의 암시적 주소를 사용 하는 경우 `inref<SomeType>`형식의 인수를 사용 하는 오버 로드에 `SomeType` 형식의 인수를 사용 하는 오버 로드를 사용 하는 것이 좋습니다. 예를 들면 다음과 같습니다.:

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

두 경우 모두 `System.DateTime`를 수행 하는 오버 로드는 `inref<System.DateTime>`를 수행 하는 오버 로드가 아니라 확인 됩니다.

## <a name="byref-like-structs"></a>Byref와 유사한 구조체

`outref` 3 개 숫자 /`inref``byref`/외에도 `byref`와 유사한 의미 체계를 따를 수 있는 고유한 구조체를 정의할 수 있습니다. <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> 특성을 사용 하 여 수행 됩니다.

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike`은 `Struct`을 의미 하지 않습니다. 둘 다 형식에 있어야 합니다.

의 F# "`byref`유사" 구조체는 스택 바인딩된 값 형식입니다. 이는 관리 되는 힙에 할당 되지 않습니다. `byref`같은 구조체는 수명 및 비 캡처에 대 한 강력한 검사 집합으로 적용 되므로 고성능 프로그래밍에 유용 합니다. 여기에 적용되는 규칙은 다음과 같습니다.

* 함수 매개 변수, 메서드 매개 변수, 지역 변수, 메서드 반환으로 사용할 수 있습니다.
* 클래스 또는 일반 구조체의 정적 또는 인스턴스 멤버일 수 없습니다.
* 이러한 메서드는 클로저 구문 (`async` 메서드 또는 람다 식)에서 캡처할 수 없습니다.
* 제네릭 매개 변수로 사용할 수 없습니다.

이 마지막 지점은 `|>`가 입력 F# 형식을 매개 변수화 하는 제네릭 함수 이기 때문에 파이프라인 스타일 프로그래밍에 중요 합니다. 이 제한은 인라인으로 `|>` 나중에 완화 될 수 있으며 본문에서 인라인 되지 않은 제네릭 함수를 호출 하지 않습니다.

이러한 규칙은 사용을 매우 강력 하 게 제한 하지만 안전 하 게 고성능 컴퓨팅의 약속을 달성 하는 데 필요 합니다.

## <a name="byref-returns"></a>Byref 반환

Byref는 함수 F# 또는 멤버를 생성 하 고 사용할 수 있습니다. `byref`반환 메서드를 사용 하는 경우이 값은 암시적으로 역참조 됩니다. 예를 들면 다음과 같습니다.:

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

여러 개의 연결 된 호출을 통해 참조를 전달 하는 것과 같이 암시적 역참조를 방지 하려면 `&x`을 사용 합니다. 여기서 `x`는 값입니다.

반환 `byref`에 직접 할당할 수도 있습니다. 다음 (매우 명령적) 프로그램을 고려 합니다.

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

## <a name="scoping-for-byrefs"></a>Byref 배열과 같은에 대 한 범위 지정

`let`바인딩된 값은 해당 참조가 정의 된 범위를 초과할 수 없습니다. 예를 들어 다음은 허용 되지 않습니다.

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

이렇게 하면 최적화를 설정 하거나 해제 하 여 컴파일하는 경우에 따라 다른 결과를 얻을 수 없습니다.
