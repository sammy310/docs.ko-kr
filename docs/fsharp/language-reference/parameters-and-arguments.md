---
title: 매개 변수 및 인수
description: 매개 변수를 정의하고 함수, 메서드 및 속성에 인수를 전달하는 F# 언어 지원에 대해 알아봅니다.
ms.date: 12/04/2019
ms.openlocfilehash: b234ef939128e7cf09d35f9580d4d5010d7dc639
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401054"
---
# <a name="parameters-and-arguments"></a>매개 변수 및 인수

이 항목에서는 매개 변수를 정의하고 함수, 메서드 및 속성에 인수를 전달하는 언어 지원에 대해 설명합니다. 여기에는 참조로 전달하는 방법과 다양한 수의 인수를 사용할 수 있는 메서드를 정의하고 사용하는 방법에 대한 정보가 포함되어 있습니다.

## <a name="parameters-and-arguments"></a>매개 변수 및 인수

매개 *변수라는* 용어는 제공될 것으로 예상되는 값의 이름을 설명하는 데 사용됩니다. *인수라는* 용어는 각 매개 변수에 대해 제공된 값에 사용됩니다.

매개 변수는 튜플 또는 커리 형식으로 또는 둘 중 일부 조합으로 지정할 수 있습니다. 명시적 매개 변수 이름을 사용하여 인수를 전달할 수 있습니다. 메서드 매개 변수는 선택 사항으로 지정하고 기본값을 지정할 수 있습니다.

## <a name="parameter-patterns"></a>매개 변수 패턴

함수 및 메서드에 제공된 매개 변수는 일반적으로 공백으로 구분되는 패턴입니다. 즉, 원칙적으로 [식 일치에](match-expressions.md) 설명된 모든 패턴을 함수 또는 멤버의 매개 변수 목록에서 사용할 수 있습니다.

메서드는 일반적으로 전달 인수의 튜플 형식을 사용합니다. 튜플 양식이 .NET 메서드에서 인수가 전달되는 방식과 일치하기 때문에 다른 .NET 언어의 관점에서 더 명확한 결과를 얻을 수 있습니다.

커리 형식은 바인딩을 사용하여 `let` 만든 함수와 함께 가장 자주 사용됩니다.

다음 의사 코드는 튜플 및 커리 인수의 예를 보여 주며,

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

결합 된 양식은 일부 인수가 tuples에 있고 일부는 그렇지 않은 경우 가능합니다.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

다른 패턴도 매개 변수 목록에서 사용할 수 있지만 매개 변수 패턴이 가능한 모든 입력과 일치하지 않으면 런타임에 불완전한 일치가 있을 수 있습니다. 인수 `MatchFailureException` 값이 매개 변수 목록에 지정된 패턴과 일치하지 않을 때 예외가 생성됩니다. 컴파일러는 매개 변수 패턴이 불완전한 일치를 허용하면 경고를 발행합니다. 하나 이상의 다른 패턴은 일반적으로 매개 변수 목록에 유용하며 와일드카드 패턴입니다. 제공된 인수를 무시하려는 경우 매개 변수 목록에서 와일드카드 패턴을 사용합니다. 다음 코드는 인수 목록에서 와일드카드 패턴의 사용을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

와일드카드 패턴은 프로그램에 대한 기본 진입점에서와 같이 다음 코드와 같이 일반적으로 문자열 배열로 제공되는 명령줄 인수에 관심이 없을 때 전달된 인수를 필요로 하지 않을 때마다 유용할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

인수에 사용되는 다른 패턴은 구별된 공용 구조체 및 활성 패턴과 관련된 `as` 패턴 및 식별자 패턴입니다. 다음과 같이 단일 대/소문자 구분 공용 구조체 패턴을 사용할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

출력은 다음과 같습니다.

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

활성 패턴은 다음과 같은 예제와 같이 인수를 원하는 형식으로 변환할 때 매개 변수로 유용할 수 있습니다.

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

다음 코드 `as` 줄에 표시된 대로 패턴을 사용하여 일치하는 값을 로컬 값으로 저장할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

경우에 따라 사용되는 또 다른 패턴은 함수의 본문으로서 암시적 인수에서 패턴 일치를 즉시 수행하는 lambda 식을 제공하여 마지막 인수를 이름을 지정하지 않은 함수입니다. 이 예제는 다음과 같은 코드 줄입니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

이 코드는 제네릭 목록을 가져와 `true` 목록이 비어 있는 경우 `false` 반환하는 함수를 정의합니다. 이러한 기술을 사용하면 코드를 읽기가 더 어려워질 수 있습니다.

경우에 따라 불완전한 일치가 포함된 패턴이 유용할 수 있습니다(예: 프로그램의 목록에 요소가 세 개뿐이라는 것을 알고 있는 경우 매개 변수 목록에서 다음과 같은 패턴을 사용할 수 있습니다.)

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

불완전한 일치가 있는 패턴의 사용은 빠른 프로토타이핑 및 기타 임시 용도로 예약하는 것이 가장 좋습니다. 컴파일러는 이러한 코드에 대한 경고를 발행합니다. 이러한 패턴은 가능한 모든 입력의 일반적인 경우를 커버할 수 없으므로 구성 요소 API에는 적합하지 않습니다.

## <a name="named-arguments"></a>명명된 인수

메서드에 대한 인수는 쉼표로 구분된 인수 목록의 위치로 지정하거나 이름을 제공하여 메서드에 명시적으로 전달될 수 있으며, 그 다음에 는 동등한 부호와 전달할 값이 있습니다. 이름을 제공하여 지정하면 선언에 사용된 순서와 다른 순서로 나타날 수 있습니다.

명명된 인수를 사용하면 메서드 매개 변수의 순서를 변경하는 것과 같은 API의 특정 유형의 변경 사항에 코드를 더 읽기 쉽고 쉽게 조정할 수 있습니다.

명명된 인수는 바인딩된 함수, `let`함수 값 또는 람다 식에 대 한 메서드에 대해서만 허용 됩니다.

다음 코드 예제에서는 명명된 인수의 사용을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

클래스 생성자 호출에서 명명된 인수와 유사한 구문을 사용하여 클래스의 속성 값을 설정할 수 있습니다. 다음 예제에서는 이 구문을 보여 주며 이 구문을 보여 주습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

자세한 내용은 [생성자(F#)를](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)참조하십시오.

## <a name="optional-parameters"></a>선택적 매개 변수

매개 변수 이름 앞에 물음표를 사용하여 메서드에 대한 선택적 매개 변수를 지정할 수 있습니다. 선택적 매개 변수는 F# 옵션 유형으로 해석되므로 `match` `Some` 및 `None`을 사용하여 옵션 형식이 쿼리되는 일반 방식으로 쿼리할 수 있습니다. 선택적 매개 변수는 바인딩을 사용하여 `let` 만든 함수가 아니라 멤버에서만 허용됩니다.

또는 `?arg=None` `?arg=Some(3)` 와 `?arg=arg`같은 매개 변수 이름으로 메서드에 기존 선택적 값을 전달할 수 있습니다. 이 기능은 선택적 인수를 다른 메서드로 전달하는 메서드를 빌드할 때 유용할 수 있습니다.

선택적 인수의 기본값을 설정하는 함수를 `defaultArg`사용할 수도 있습니다. 함수는 `defaultArg` 선택적 매개 변수를 첫 번째 인수로, 기본값을 두 번째 인수로 사용합니다.

다음 예제에서는 선택적 매개 변수의 사용을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

출력은 다음과 같습니다.

```console
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

C# 및 Visual Basic interop을 위해 F#의 특성을 `[<Optional; DefaultParameterValue<(...)>]` 사용할 수 있으므로 호출자가 인수를 선택 사항으로 볼 수 있습니다. 이는 `MyMethod(int i = 3)`에서와 같이 C#에서 인수를 선택 사항으로 정의하는 것과 같습니다.

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

새 객체를 기본 매개 변수 값으로 지정할 수도 있습니다. 예를 들어 `Foo` 멤버는 대신 `CancellationToken` 입력으로 선택적 을 가질 수 있습니다.

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

인수로 제공되는 값은 매개 변수의 형식과 `DefaultParameterValue` 일치해야 합니다. 예를 들어 다음을 사용할 수 없습니다.

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

이 경우 컴파일러는 경고를 생성하고 두 특성을 모두 무시합니다. 그렇지 않으면 컴파일러가 `null` 잘못된 형식, 즉 . `[<Optional; DefaultParameterValue(null:obj)>] o:obj`

## <a name="passing-by-reference"></a>참조로 전달

참조로 F# 값을 전달하려면 관리되는 포인터 형식인 [byrefs가](byrefs.md)포함됩니다. 사용할 유형에 대한 지침은 다음과 같습니다.

- 포인터만 읽어야 하는 경우 사용합니다. `inref<'T>`
- 포인터에만 쓸 필요가 있는 경우 사용합니다. `outref<'T>`
- 포인터를 읽고 쓰는 데 필요한 경우 사용합니다. `byref<'T>`

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

let test () =
    // No need to make it mutable, since it's read-only
    let x = 1
    example1 &x

    // Needs to be mutable, since we write to it
    let mutable y = 2
    example2 &y
    example3 &y // Now 'y' is 3
```

매개 변수는 포인터이고 값은 가변가능하기 때문에 함수실행 후 값에 대한 모든 변경 내용은 유지됩니다.

튜플을 반환 값으로 사용하여 .NET `out` 라이브러리 메서드에 모든 매개 변수를 저장할 수 있습니다. 또는 매개 변수를 `out` 매개 변수로 취급할 `byref` 수 있습니다. 다음 코드 예제에서는 두 가지 방법을 모두 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>매개 변수 배열

경우에 따라 이기종 형식의 임의의 수의 매개 변수를 취하는 함수를 정의해야 합니다. 사용할 수 있는 모든 형식을 설명하기 위해 가능한 모든 오버로드 메서드를 만드는 것은 실용적이지 않습니다. .NET 구현은 매개 변수 배열 기능을 통해 이러한 메서드에 대한 지원을 제공합니다. 해당 서명에서 매개 변수 배열을 사용하는 메서드는 임의의 수의 매개 변수와 함께 제공될 수 있습니다. 매개 변수는 배열에 배치됩니다. 배열 요소의 형식에 따라 함수에 전달할 수 있는 매개 변수 형식이 결정됩니다. 요소 유형으로 `System.Object` 매개 변수 배열을 정의하는 경우 클라이언트 코드는 모든 형식의 값을 전달할 수 있습니다.

F#에서 매개 변수 배열은 메서드에서만 정의할 수 있습니다. 모듈에 정의된 독립 실행형 함수 또는 함수에서는 사용할 수 없습니다.

특성을 사용하여 매개 변수 `ParamArray` 배열을 정의합니다. 특성은 `ParamArray` 마지막 매개 변수에만 적용할 수 있습니다.

다음 코드는 매개 변수 배열을 사용하는 .NET 메서드호출과 매개 변수 배열을 사용하는 메서드가 있는 F#의 형식 정의를 모두 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

프로젝트에서 실행할 때 이전 코드의 출력은 다음과 같습니다.

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>참고 항목

- [멤버](./members/index.md)
