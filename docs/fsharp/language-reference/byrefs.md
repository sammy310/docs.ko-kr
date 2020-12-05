---
title: Byref
description: '낮은 수준의 프로그래밍에 사용 되는 F #의 byref 및 byref와 유사한 형식에 대해 알아봅니다.'
ms.date: 11/04/2019
ms.openlocfilehash: ff2c06d8940f7341d5d8b1d942be264bfac586c5
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740317"
---
# <a name="byrefs"></a>Byref

F #에는 하위 수준 프로그래밍의 공간을 처리 하는 두 가지 주요 기능 영역이 있습니다.

* 관리 되는 `byref` / `inref` / `outref` 포인터인 형식입니다. 런타임에 잘못 된 프로그램을 컴파일할 수 없도록 사용에 대 한 제한 사항이 있습니다.
* 와 `byref` 유사한 의미 체계와 동일한 컴파일 시간 제한이 있는 [구조인](structures.md) 와 유사한 구조체입니다 `byref<'T>` . 한 가지 예는 <xref:System.Span%601> 입니다.

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

다음의 세 가지 형식이 있습니다 `byref` .

* `inref<'T>`-내부 값을 읽기 위한 관리 되는 포인터입니다.
* `outref<'T>`-내부 값에 쓰기 위한 관리 되는 포인터입니다.
* `byref<'T>`-내부 값을 읽고 쓰기 위한 관리 되는 포인터입니다.

가 `byref<'T>` 필요한 위치에를 전달할 수 있습니다 `inref<'T>` . 마찬가지로,가 `byref<'T>` 필요한 위치에를 전달할 수 있습니다 `outref<'T>` .

## <a name="using-byrefs"></a>Byref 배열과 같은 사용

을 사용 하려면 `inref<'T>` 다음을 사용 하 여 포인터 값을 가져와야 합니다 `&` .

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn $"Now: %O{dt}"

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

또는를 사용 하 여 포인터에 쓰려면 `outref<'T>` `byref<'T>` 포인터를 가져오는 값도 설정 해야 합니다 `mutable` .

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn $"Now: %O{dt}"
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

포인터를 읽는 대신만 쓰려면를 사용 하는 것이 좋습니다 `outref<'T>` `byref<'T>` .

### <a name="inref-semantics"></a>Inref 의미 체계

다음 코드를 생각해 봅시다.

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

의미 체계가 며,이는 다음을 의미 합니다.

* 포인터의 소유자는 `x` 이 값만 사용 하 여 값을 읽을 수 있습니다.
* 내에 중첩 된 필드에 대해 획득 한 모든 포인터에 `struct` `SomeStruct` 는 지정 된 형식이 `inref<_>` 있습니다.

다음도 마찬가지입니다.

* 다른 스레드나 별칭에는에 대 한 쓰기 권한이 없다는 의미는 없습니다 `x` .
* 인 경우에는 변경할 수 없는 의미는 없습니다 `SomeStruct` `x` `inref` .

그러나 **변경할 수 없는 F** # 값 형식의 경우 `this` 포인터는로 유추 됩니다 `inref` .

이러한 모든 규칙은 포인터의 소유자가 `inref` 가리키는 메모리의 즉시 콘텐츠를 수정할 수 없음을 의미 합니다.

### <a name="outref-semantics"></a>Outref 의미 체계

의 목적은 `outref<'T>` 포인터를에만 써야 함을 나타내는 것입니다. 예기치 않게에서는 `outref<'T>` 이름에도 불구 하 고 기본 값을 읽을 수 있습니다. 이는 호환성을 위해 제공 됩니다. 의미 체계가 `outref<'T>` 며와는 다릅니다 `byref<'T>` .

### <a name="interop-with-c"></a>C와의 상호 운용성\#

C #에서는 `in ref` `out ref` 를 반환 하는 것 외에도 및 키워드를 지원 합니다 `ref` . 다음 표에서는 F #에서 c #에서 내보내는 항목을 해석 하는 방법을 보여 줍니다.

|C # 구문|F # 유추|
|------------|---------|
|`ref` 반환 값|`outref<'T>`|
|`ref readonly` 반환 값|`inref<'T>`|
|`in ref` 매개 변수|`inref<'T>`|
|`out ref` 매개 변수|`outref<'T>`|

다음 표에서는 F #에서 내보내는 기능을 보여 줍니다.

|F # 구문|내보낸 구문|
|------------|-----------------|
|`inref<'T>` 인수|`[In]` 인수의 특성|
|`inref<'T>` 돌려|`modreq` value의 특성|
|`inref<'T>` 추상 슬롯 또는 구현|`modreq` on 인수 또는 return|
|`outref<'T>` 인수|`[Out]` 인수의 특성|

### <a name="type-inference-and-overloading-rules"></a>형식 유추 및 오버 로드 규칙

`inref<'T>`다음 경우에 F # 컴파일러에서 형식을 유추 합니다.

1. 특성이 있는 .NET 매개 변수 또는 반환 형식 `IsReadOnly` 입니다.
2. `this`변경할 필드가 없는 구조체 형식의 포인터입니다.
3. 다른 포인터에서 파생 된 메모리 위치의 주소입니다 `inref<_>` .

의 암시적 주소를 사용 하는 경우 형식의 인수를 사용 `inref` 하는 오버 로드 `SomeType` 를 형식의 인수를 사용 하는 오버 로드에 사용 하는 것이 좋습니다 `inref<SomeType>` . 예를 들면 다음과 같습니다.

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

두 경우 모두를 수행 하는 오버 로드는 `System.DateTime` 오버 로드가 아니라 확인 됩니다 `inref<System.DateTime>` .

## <a name="byref-like-structs"></a>Byref와 유사한 구조체

3 개 숫자 외에도 `byref` / `inref` / `outref` 유사한 의미 체계를 따를 수 있는 고유한 구조체를 정의할 수 있습니다 `byref` . 이 작업은 특성을 사용 하 여 수행 됩니다 <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> .

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` 는를 의미 하지 않습니다 `Struct` . 둘 다 형식에 있어야 합니다.

`byref`F #의 "like" 구조체는 스택 바인딩된 값 형식입니다. 이는 관리 되는 힙에 할당 되지 않습니다. `byref`이와 비슷한 구조체는 수명 및 비 캡처에 대 한 강력한 검사 집합으로 적용 되므로 고성능 프로그래밍에 유용 합니다. 규칙은 다음과 같습니다.

* 함수 매개 변수, 메서드 매개 변수, 지역 변수, 메서드 반환으로 사용할 수 있습니다.
* 클래스 또는 일반 구조체의 정적 또는 인스턴스 멤버일 수 없습니다.
* 이러한 메서드는 클로저 구문 ( `async` 메서드 또는 람다 식)에서 캡처할 수 없습니다.
* 제네릭 매개 변수로 사용할 수 없습니다.

이 마지막 지점은 `|>` 입력 형식을 매개 변수화 하는 제네릭 함수 처럼 F # 파이프라인 스타일 프로그래밍에 중요 합니다. 이 제한 사항은 `|>` 인라인 이며 본문에서 인라인 되지 않은 제네릭 함수를 호출 하지 않으므로 나중에 완화 될 수 있습니다.

이러한 규칙은 사용을 강력 하 게 제한 하지만 안전 하 게 고성능 컴퓨팅의 약속을 달성 하는 데 필요 합니다.

## <a name="byref-returns"></a>Byref 반환

F # 함수에서 Byref를 반환 하거나 멤버를 생성 하 고 사용할 수 있습니다. 반환 하는 `byref` 메서드를 사용 하는 경우이 값은 암시적으로 역참조 됩니다. 예를 들면 다음과 같습니다.

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn $"%d{squared}"
```

Byref 값을 반환 하려면 값을 포함 하는 변수가 현재 범위 보다 오래 지속 되어야 합니다.
또한 byref를 반환 하려면를 사용 `&value` 합니다. 여기서 value는 현재 범위 보다 오래 지속 되는 변수입니다.

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

여러 연결 된 호출을 통해 참조를 전달 하는 것과 같이 암시적 역참조를 방지 하려면를 사용 `&x` `x` 합니다. 여기서은 값입니다.

또한 반환에 직접 할당할 수 있습니다 `byref` . 다음 (매우 명령적) 프로그램을 고려 합니다.

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
    printfn $"Original sequence: %O{c}"

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn $"New sequence:      %O{c}"

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

이렇게 하면 최적화를 사용 하 여 컴파일하는 경우에 따라 다른 결과를 얻을 수 없습니다.
