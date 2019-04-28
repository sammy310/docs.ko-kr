---
title: 매개 변수 및 인수
description: 에 대해 알아봅니다 F# 매개 변수를 정의 하 고 함수, 메서드 및 속성에 인수를 전달 하기 위한 언어 지원 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: b68b3fdd14a66a7312efa5adb709adaeceaae282
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666263"
---
# <a name="parameters-and-arguments"></a>매개 변수 및 인수

이 항목에는 매개 변수를 정의 하 고 함수, 메서드 및 속성에 인수 전달에 대 한 언어 지원을 설명 합니다. 참조로 전달 하는 방법 및 정의 하는 가변 개수의 인수를 사용할 수 있는 메서드를 사용 하는 방법에 대 한 정보를 포함 합니다.

## <a name="parameters-and-arguments"></a>매개 변수 및 인수

용어 *매개 변수* 제공 해야 하는 값의 이름을 설명 하는 데 사용 됩니다. 용어 *인수* 각 매개 변수에 대해 제공 된 값에 사용 됩니다.

튜플 또는 변환된 형식 또는 둘의 조합에서 매개 변수를 지정할 수 있습니다. 명시적 매개 변수 이름을 사용 하 여 인수를 전달할 수 있습니다. 메서드의 매개 변수 선택적으로 지정 하 고 기본 값이 지정 될 수 있습니다.

## <a name="parameter-patterns"></a>매개 변수 패턴

함수 및 메서드를 제공 하는 매개 변수는 일반적으로 공백으로 구분 하는 패턴입니다. 이 원칙적으로 된 패턴에 설명 된 것을 의미 [일치 식](match-expressions.md) 함수 또는 멤버에 대 한 매개 변수 목록에서 사용할 수 있습니다.

메서드는 일반적으로 인수 전달 튜플 형식을 사용 합니다. 튜플 형식 인수가.NET 메서드에 전달 되는 방법은 일치 하기 때문에 다른.NET 언어의 관점에서 명확 하 게 결과 얻을 수 있습니다.

커리 된 양식을 사용 하 여 만든 함수를 사용 하 여 사용할 가장 자주 `let` 바인딩.

다음 의사 코드 예제에서는 튜플 및 커리 된 인수를 보여 줍니다.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

일부 인수 튜플을에 있으며 일부 경우 결합 된 형식을 사용할 수 있습니다.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

매개 변수 목록의 다른 패턴도 사용할 수 있지만 매개 변수 패턴을 모든 사용 가능한 입력에 일치 하지 않는 경우 있을 불완전 한 일치 하는 런타임 시. 예외 `MatchFailureException` 인수의 값 매개 변수 목록에 지정 된 패턴과 일치 하지 않는 경우 생성 됩니다. 불완전 한 일치 항목에 대 한 매개 변수 패턴을 사용 하면 컴파일러가 경고 합니다. 다른 패턴은 하나 이상의 매개 변수 목록에 대 한 일반적으로 유용 하 고 와일드 카드 패턴입니다. 제공 되는 인수를 무시 하려는 경우 매개 변수 목록에서 와일드 카드 패턴을 사용 합니다. 다음 코드는 인수 목록에서 와일드 카드 패턴의 사용을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

와일드 카드 패턴은 일반적으로 다음 코드와 같이 문자열 배열로 제공 되는 명령줄 인수에 관심이 없는 경우 전달 된 인수를 수행 해야 할 때 유용 하 고, 프로그램의 주 진입점 같이 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

인수에 자주 사용 되는 다른 패턴은 `as` 구별 된 공용 구조체 및 활성 패턴을 사용 하 여 연결 된 식별자 패턴과 패턴입니다. 다음과 같이 단일 사례 구별 된 공용 구조체 패턴을 사용할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

출력은 다음과 같습니다.

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

원하는 형식으로 다음 예제와 같이 인수가 변환 하는 경우에 활성 패턴 예를 들어, 매개 변수로 유용할 수 있습니다.

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

사용할 수는 `as` 코드의 다음 줄에 표시 된 대로 로컬 값으로 일치 하는 값을 저장 하는 패턴입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

가끔씩 사용 되는 또 다른 패턴에 마지막 인수는 함수 본문으로 제공 하 여 명명 되지 않은 상태로 유지 하는 함수를 즉시 암시적 인수에 패턴 일치를 수행 하는 람다 식입니다. 이러한 예로 다음 코드 줄.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

이 코드는 제네릭 목록을 반환 하는 함수를 정의 `true` 목록이 비어 있으면 및 `false` 그렇지 않은 경우. 이러한 기술의 사용 가능 코드를 읽기가 어려울 합니다.

경우에 따라 불완전 한 일치 항목을 포함 하는 패턴은 유용, 예를 들어 프로그램에서 목록 있는 세 개의 요소를 알고 있는 경우 사용할 수 있습니다 다음과 같은 패턴을 매개 변수 목록.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

불완전 한 일치 하는 패턴도 사용 빠른 프로토타입 및 기타 임시 사용 하 여 가장 예약 되어 있습니다. 컴파일러에서 이러한 코드에 대 한 경고가 발생 합니다. 이러한 패턴은 가능한 모든 입력의 일반적인 사례를 다룰 수는 없습니다 및 Api 구성 요소에 대해 적합 하지 않습니다.

## <a name="named-arguments"></a>명명된 인수

메서드에 대 한 인수는 쉼표로 구분 된 인수 목록에서 위치에 따라 지정할 수 있습니다 또는 전달할 수는 메서드를 명시적으로 뒤에 등호와 값을 전달 해야 하는 이름을 제공 하 여 합니다. 이름을 제공 하 여 지정 하는 경우에 선언에 사용 되는 다른 순서로 나타날 수 있습니다.

명명 된 인수 가능 코드 가독성 및 보다 융통성 있는 특정 형식의 메서드 매개 변수의 순서를 바꾸는 등의 API 변경 합니다.

명명 된 인수를 사용할 수 방법에 대해서만 아니라 `let`-바인딩된 함수, 함수 값 또는 람다 식입니다.

다음 코드 예제에서는 명명 된 인수의 사용을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

클래스 생성자 호출에서 명명 된 인수는 유사한 구문을 사용 하 여 클래스의 속성 값을 설정할 수 있습니다. 다음 예제에서는이 구문을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

자세한 내용은 [생성자 (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)합니다.

## <a name="optional-parameters"></a>선택적 매개 변수

매개 변수 이름 앞에 물음표를 사용 하 여 메서드에 대 한 선택적 매개 변수를 지정할 수 있습니다. 선택적 매개 변수로 해석 됩니다는 F# 를 사용 하 여 옵션 형식 쿼리는 정상적인 방법으로 쿼리할 수 있도록 형식 옵션을 `match` 식을 `Some` 및 `None`. 선택적 매개 변수를 사용 하 여 만든 함수에 없는 멤버에 대해서만 허용 됩니다 `let` 바인딩.

값을 전달할 수 기존 선택적 메서드에 매개 변수 이름으로 같은 `?arg=None` 나 `?arg=Some(3)` 또는 `?arg=arg`합니다. 이 기능은 다른 메서드에 선택적 인수를 전달 하는 메서드를 작성 하는 경우에 유용할 수 있습니다.

함수를 사용할 수도 있습니다 `defaultArg`, 선택적 인수의 기본값을 설정 합니다. `defaultArg` 함수는 첫 번째 인수는 선택적 매개 변수와 두 번째 기본 값을 가져옵니다.

다음 예에서는 선택적 매개 변수의 사용을 하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

출력은 다음과 같습니다.

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

위해 C# 및 Visual Basic interop 특성을 사용할 수 있습니다 `[<Optional; DefaultParameterValue<(...)>]` 에서 F#호출자는 선택 사항으로 인수로 표시 되도록 합니다. 이 해당 인수에 선택적으로 정의 하는 C# 에서처럼 `MyMethod(int i = 3)`합니다.

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

또한 기본 매개 변수 값으로 새 개체를 지정할 수 있습니다. 예를 들어 합니다 `Foo` 멤버는 선택적인 있을 수 있습니다 `CancellationToken` 대신 입력으로:

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

인수로 지정 된 값 `DefaultParameterValue` 매개 변수의 형식과 일치 해야 합니다. 예를 들어, 다음은 허용 되지 않습니다.

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

이 경우 컴파일러는 경고를 생성 하 고 두 특성 모두 무시 됩니다. 기본값이 `null` 형식 주석이 지정 해야 경우 컴파일러에서 유추 잘못 된 형식, 즉 `[<Optional; DefaultParameterValue(null:obj)>] o:obj`합니다.

## <a name="passing-by-reference"></a>참조로 전달

전달는 F# 참조로 값이 포함 됩니다 [byref](byrefs.md), 관리 되는 포인터 형식은입니다. 다음과 같이 형식을 사용 하는 지침:

* 사용 하 여 `inref<'T>` 포인터를 읽을 수만 필요 합니다.
* 사용 하 여 `outref<'T>` 포인터에 대 한 작성 해야 하는 경우.
* 사용 하 여 `byref<'T>` 에서 읽기 및 포인터에 대 한 쓰기 해야 할 경우.

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

매개 변수가 포인터가 고 값은 변경할 수 있으므로 모든 값을 변경 하는 함수의 실행 한 후 유지 됩니다.

튜플을 반환 값으로 하 여 저장 `out` .NET 라이브러리 메서드의 매개 변수입니다. 처리할 수 있습니다 합니다 `out` 매개 변수는 `byref` 매개 변수입니다. 다음 코드 예제에서는 두 가지 방법을 모두 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>매개 변수 배열

임의 개수의 유형이 다른 형식의 매개 변수를 사용 하는 함수를 정의 해야 하는 경우도 있습니다. 사용할 수 있는 모든 형식에 대 한 계정에 가능한 모든 오버 로드 된 메서드를 만드는 유용 하지 것입니다. 매개 변수 배열 기능을 통해 이러한 메서드에 대 한 지원을 제공 하는.NET 구현 합니다. 임의 개수의 매개 변수를 사용 하 여 해당 시그니처에서 매개 변수 배열을 사용 하는 메서드를 제공할 수 있습니다. 매개 변수 배열에 배치 됩니다. 함수에 전달 될 수 있는 매개 변수 유형이 결정 하는 배열 요소의 형식입니다. 매개 변수 배열을 정의 하는 경우 `System.Object` 요소 형식으로 클라이언트 코드 수 전달한 모든 형식의 값입니다.

F#을 매개 변수 배열 메서드에서만에서 정의할 수 있습니다. 독립 실행형 함수 또는 모듈에 정의 된 함수에서 사용할 수 없습니다.

매개 변수 배열을 사용 하 여 정의한는 `ParamArray` 특성입니다. `ParamArray` 특성은 마지막 매개 변수에 적용할 수 있습니다.

다음 코드에서 형식 정의와 매개 변수 배열을 사용 하는.NET 메서드를 호출 하는 방법을 보여 줍니다 F# 매개 변수 배열을 사용 하는 메서드가 포함 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

프로젝트를 실행 하는 경우 이전 코드의 출력은 다음과 같습니다.

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>참고자료

- [멤버](members/index.md)
