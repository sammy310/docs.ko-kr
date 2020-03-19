---
title: F# 코딩 규칙
description: F# 코드를 작성할 때 일반적인 지침과 숙어를 배웁니다.
ms.date: 01/15/2020
ms.openlocfilehash: 7266211e501bdb52564220781e2347d1aceaf296
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401150"
---
# <a name="f-coding-conventions"></a>F# 코딩 규칙

다음 규칙은 대규모 F# 코드베이스를 사용하면 서두르는 경험에서 공식화됩니다. [좋은 F # 코드의 다섯 가지 원칙은](index.md#five-principles-of-good-f-code) 각 권장 사항의 기초입니다. F# 구성 [요소 디자인 지침과](component-design-guidelines.md)관련이 있지만 라이브러리와 같은 구성 요소뿐만 아니라 모든 F# 코드에 적용할 수 있습니다.

## <a name="organizing-code"></a>코드 구성

F#에는 모듈과 네임스페이스라는 두 가지 기본 코드가 있습니다. 이들은 비슷하지만 다음과 같은 차이점이 있습니다.

* 네임스페이스는 .NET 네임스페이스로 컴파일됩니다. 모듈은 정적 클래스로 컴파일됩니다.
* 네임스페이스는 항상 최상위 수준입니다. 모듈은 최상위 수준이며 다른 모듈 내에 중첩될 수 있습니다.
* 네임스페이스는 여러 파일에 걸쳐 있을 수 있습니다. 모듈은 할 수 없습니다.
* 모듈을 장식할 `[<RequireQualifiedAccess>]` 수 `[<AutoOpen>]`있습니다.

다음 지침은 코드를 구성하는 데 사용할 수 있습니다.

### <a name="prefer-namespaces-at-the-top-level"></a>최상위 수준에서 네임스페이스 선호

공개적으로 소모품 코드의 경우 네임스페이스는 최상위 수준의 모듈보다 우선합니다. .NET 네임스페이스로 컴파일되므로 문제 없이 C#에서 사용할 수 있습니다.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

최상위 모듈을 사용하면 F#에서만 호출할 때 다르게 나타나지 않을 수 있지만 C# 소비자의 `MyClass` 경우 `MyCode` 호출자는 모듈을 사용할 수 있어야 하므로 놀랄 수 있습니다.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>신중하게 적용`[<AutoOpen>]`

구문은 `[<AutoOpen>]` 발신자가 사용할 수 있는 범위의 범위를 오염시킬 수 있으며, 무언가의 유래에 대한 대답은 "마법"입니다. 이것은 좋은 일이 아니다. 이 규칙의 예외는 F# 코어 라이브러리 자체입니다(이 사실은 약간 논란의 여지가 있음).

그러나 공용 API와 별도로 구성하려는 공용 API에 대한 도우미 기능이 있는 경우 편리합니다.

```fsharp
module MyAPI =
    [<AutoOpen>]
    module private Helpers =
        let helper1 x y z =
            ...

    let myFunction1 x =
        let y = ...
        let z = ...

        helper1 x y z
```

이렇게 하면 호출할 때마다 도우미를 완전히 한정할 필요 없이 함수의 공용 API에서 구현 세부 정보를 완전히 분리할 수 있습니다.

또한 네임스페이스 수준에서 확장 메서드 및 식 빌더를 노출하면 을 로 `[<AutoOpen>]`깔끔하게 표현할 수 있습니다.

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>이름이 `[<RequireQualifiedAccess>]` 충돌하거나 가독성에 도움이 된다고 느낄 때마다 사용

모듈에 `[<RequireQualifiedAccess>]` 특성을 추가하면 모듈이 열리지 않을 수 있으며 모듈의 요소에 대한 참조에는 명시적 권한 있는 액세스가 필요하다는 것을 나타냅니다. 예를 들어 `Microsoft.FSharp.Collections.List` 모듈에 이 특성이 있습니다.

이 기능은 모듈의 함수와 값에 다른 모듈의 이름과 충돌할 가능성이 있는 이름이 있는 경우에 유용합니다. 자격을 갖춘 액세스가 필요하면 라이브러리의 장기적인 유지 관리 및 사용 가능성을 크게 높일 수 있습니다.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>정렬 `open` 문 토폴로지

F#에서 선언순서는 `open` 문을 포함하여 중요합니다. 이는 파일에서 해당 명령문의 `using` 순서와 는 별개의 효과가 있는 `using static` C#과는 다릅니다.

F#에서 범위로 열린 요소는 이미 존재하는 다른 요소를 숨가일 수 있습니다. 즉, 명령문을 `open` 다시 정렬하면 코드의 의미가 변경될 수 있습니다. 따라서 예상할 수 있는 다른 `open` 동작을 생성하지 않도록 모든 명령문(예: 범수치)을 임의로 정렬하는 것은 권장되지 않습니다.

대신 [위상적으로](https://en.wikipedia.org/wiki/Topological_sorting)정렬하는 것이 좋습니다. 즉, 시스템의 `open` _계층이_ 정의된 순서대로 명령문을 정렬합니다. 상이한 토폴로지 레이어 내에서 상숫자 정렬을 수행하는 것도 고려될 수 있습니다.

예를 들어 F# 컴파일러 서비스 공용 API 파일에 대한 토폴로지 정렬은 다음과 같습니다.

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
```

선 바선은 위상레이어를 구분하며, 각 레이어는 나중에 상숫자로 정렬됩니다. 이렇게 하면 실수로 값을 섀도핑하지 않고 코드를 깔끔하게 정리할 수 있습니다.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>클래스를 사용하여 부작용이 있는 값을 포함합니다.

값을 초기화하는 경우 데이터베이스 또는 기타 원격 리소스에 컨텍스트를 인스턴스화하는 등의 부작용이 있을 수 있습니다. 모듈에서 이러한 것들을 초기화하고 후속 함수에서 사용하는 것이 유혹합니다.

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

이것은 종종 몇 가지 이유로 나쁜 생각:

첫째, 응용 프로그램 구성을 `dep1` 와 `dep2`함께 코드베이스에 푸시합니다. 이 문제는 더 큰 코드베이스에서 유지 관리하기가 어렵습니다.

둘째, 정적 초기화 된 데이터는 구성 요소 자체가 여러 스레드를 사용하는 경우 스레드가 안전하지 않은 값을 포함해서는 안됩니다. 이것은 분명히 에 `dep3`의해 위반됩니다.

마지막으로 모듈 초기화는 전체 컴파일 단위에 대한 정적 생성자로 컴파일됩니다. 해당 모듈의 let-bound 값 초기화에서 오류가 발생하면 응용 `TypeInitializationException` 프로그램의 전체 수명 동안 캐시되는 것으로 나타납니다. 이것은 진단하기 어려울 수 있습니다. 일반적으로 추론을 시도할 수 있는 내부 예외가 있지만 그렇지 않은 경우 근본 원인을 알 수 없습니다.

대신 간단한 클래스를 사용하여 종속성을 유지하십시오.

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

이렇게 하면 다음을 수행할 수 있습니다.

1. API 자체 외부에서 종속 상태를 푸시합니다.
2. 이제 API 외부에서 구성을 수행할 수 있습니다.
3. 종속 값에 대한 초기화 오류는 `TypeInitializationException`로 나타나지 않을 수 있습니다.
4. 이제 API를 더 쉽게 테스트할 수 있습니다.

## <a name="error-management"></a>오류 관리

대형 시스템의 오류 관리는 복잡하고 미묘한 노력이며 시스템이 내결함성이 있고 잘 행동하도록 보장하는 실버 글머리 기호가 없습니다. 다음 지침은 이 어려운 공간을 탐색하는 데 지침을 제공해야 합니다.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>도메인에 고유한 형식의 오류 사례 및 잘못된 상태를 나타냅니다.

[구별된 공용 구조체를](../language-reference/discriminated-unions.md)사용하면 F#을 사용하여 형식 시스템에서 잘못된 프로그램 상태를 나타낼 수 있습니다. 다음은 그 예입니다.

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

이 경우 은행 계좌에서 돈을 인출하는 데 실패할 수 있는 세 가지 알려진 방법이 있습니다. 각 오류 사례는 형식에 표시되므로 프로그램 전체에서 안전하게 처리할 수 있습니다.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

일반적으로 도메인에서 **오류가 발생할** 수 있는 다양한 방법을 모델링할 수 있는 경우 오류 처리 코드는 더 이상 일반 프로그램 흐름 외에도 처리해야 하는 것으로 처리되지 않습니다. 그것은 단순히 정상적인 프로그램 흐름의 일부이며, **뛰어난**간주되지 않습니다. 이두 가지 주요 이점이 있습니다.

1. 시간이 지남에 따라 도메인이 변경됨에 따라 유지 관리가 더 쉬워집니다.
2. 오류 케이스는 단위 테스트가 더 쉽습니다.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>오류를 형식으로 나타낼 수 없는 경우 예외 사용

문제 도메인에 모든 오류를 나타낼 수 있는 것은 아닙니다. 이러한 종류의 오류는 본질적으로 *예외적이므로* F #에서 예외를 발생시키고 catch할 수 있습니다.

먼저 [예외 디자인 지침을](../../standard/design-guidelines/exceptions.md)읽는 것이 좋습니다. F#에도 적용할 수 있습니다.

예외를 발생시키기 위해 F#에서 사용할 수 있는 기본 구문은 다음과 같은 기본 설정 순서로 고려해야 합니다.

| 함수 | 구문 | 목적 |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | 지정된 `System.ArgumentNullException` 인수 이름으로 a를 발생시면 됩니다. |
| `invalidArg` | `invalidArg "argumentName" "message"` | 지정된 `System.ArgumentException` 인수 이름과 메시지를 가진 a를 발생시다. |
| `invalidOp` | `invalidOp "message"` | 지정된 `System.InvalidOperationException` 메시지와 함께 를 발생 시면 됩니다. |
|`raise`| `raise (ExceptionType("message"))` | 예외를 throw하기 위한 범용 메커니즘입니다. |
| `failwith` | `failwith "message"` | 지정된 `System.Exception` 메시지와 함께 를 발생 시면 됩니다. |
| `failwithf` | `failwithf "format string" argForFormatString` | 형식 `System.Exception` 문자열 및 해당 입력에 의해 결정된 메시지와 함께 a를 발생시다. |

을 `nullArg` `invalidArg` 던지고 `invalidOp` 적절한 `ArgumentNullException` `ArgumentException` `InvalidOperationException` 경우 메커니즘으로 사용합니다.

및 함수는 일반적으로 특정 예외가 아니라 `Exception` 기본 형식을 발생하므로 피해야 합니다. `failwithf` `failwith` [예외 디자인 지침에](../../standard/design-guidelines/exceptions.md)따라 가능한 경우 보다 구체적인 예외를 발생시킬 수 있습니다.

### <a name="using-exception-handling-syntax"></a>예외 처리 구문 사용

F#은 `try...with` 구문을 통해 예외 패턴을 지원합니다.

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

패턴을 일치시키는 예외상황에서 수행할 기능을 조정하는 것은 코드를 깨끗하게 유지하려는 경우 다소 까다로울 수 있습니다. 이를 처리하는 한 가지 방법은 활성 [패턴을](../language-reference/active-patterns.md) 예외 자체로 오류 사례와 함께 둘러싼 기능을 그룹화하는 수단으로 사용하는 것입니다. 예를 들어 예외를 throw할 때 예외 메타데이터에 중요한 정보를 둘러싸는 API를 사용할 수 있습니다. 활성 패턴 내에서 캡처된 예외본문에 유용한 값을 래핑 해제하고 해당 값을 반환하는 것은 경우에 따라 유용할 수 있습니다.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>예외를 대체하기 위해 모나드 오류 처리를 사용하지 마십시오.

예외는 함수형 프로그래밍에서 다소 금기사항으로 간주됩니다. 실제로 예외는 순도를 위반하므로 기능적이지 않다고 간주하는 것이 안전합니다. 그러나 코드가 실행되어야 하는 위치와 런타임 오류가 발생할 수 있는 현실을 무시합니다. 일반적으로 대부분의 것이 순수하거나 총체적이지 않은다는 가정하에 코드를 작성하여 불쾌한 놀라움을 최소화합니다.

.NET 런타임 및 크로스언어 생태계전체에서의 관련성 및 적합성과 관련하여 예외의 다음과 같은 핵심 강점/측면을 고려하는 것이 중요합니다.

1. 여기에는 자세한 진단 정보가 포함되어 있어 문제를 디버깅할 때 매우 유용합니다.
2. 런타임 및 기타 .NET 언어에서 잘 이해됩니다.
3. 임시로 의미 체계의 일부 하위 집합을 구현하여 예외를 *피하기* 위해 방해가 되는 코드와 비교할 때 중요한 상용구를 줄일 수 있습니다.

이 세 번째 지점은 매우 중요합니다. 사소한 복잡한 작업의 경우 예외를 사용하지 않으면 다음과 같은 구조를 처리할 수 있습니다.

```fsharp
Result<Result<MyType, string>, string list>
```

"문자열 형식"오류에 패턴 일치와 같은 깨지기 쉬운 코드로 쉽게 이어질 수 있습니다.

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

또한 "더 좋은" 형식을 반환 하는 "간단한" 함수에 대 한 욕망에서 예외를 삼 키는 유혹 수 있습니다.

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

안타깝게도 `tryReadAllText` 파일 시스템에서 발생할 수 있는 수많은 예외를 기반으로 수많은 예외를 throw할 수 있으며, 이 코드는 사용자 환경에서 실제로 잘못될 수 있는 것에 대한 정보를 삭제합니다. 이 코드를 결과 유형으로 바꾸면 "문자열 형식" 오류 메시지 구문 분석으로 돌아갑니다.

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Ok
    with e -> Error e.Message

let r = tryReadAllText "path-to-file"
match r with
| Ok text -> ...
| Error e ->
    if e.Contains "uh oh, here we go again..." then ...
    else ...
```

또한 예외 개체 자체를 `Error` 생성자에 배치하면 함수가 아닌 호출 사이트에서 예외 형식을 올바르게 처리해야 합니다. 이렇게 하면 API 호출자로 처리하는 것이 재미없는 것으로 악명 높은 검사된 예외가 효과적으로 생성됩니다.

위의 예제에 대한 좋은 대안은 *특정* 예외를 catch하고 해당 예외의 컨텍스트에서 의미 있는 값을 반환하는 것입니다. 다음과 같이 `tryReadAllText` 함수를 수정하면 더 많은 의미가 `None` 있습니다.

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

이제 이 함수는 포괄 함수로 작동하는 대신 파일이 발견되지 않은 경우 케이스를 제대로 처리하고 해당 의미를 반환에 할당합니다. 이 반환 값은 컨텍스트 정보를 삭제하거나 호출자가 코드의 해당 지점에서 관련이 없을 수 있는 경우를 처리하도록 강요하지 는 않지만 해당 오류 사례에 매핑할 수 있습니다.

중첩되지 `Result<'Success, 'Error>` 않은 기본 작업에 적합한 유형과 같은 형식과 F# 선택적 형식은 무언가 또는 *아무것도* *반환할* 수 있는 시기를 나타내는 데 적합합니다. 그러나 예외를 대체하는 것은 아니며 예외를 대체하기 위해 사용해서는 안 됩니다. 대신 예외 및 오류 관리 정책의 특정 측면을 대상으로 처리하기 위해 신중하게 적용해야 합니다.

## <a name="partial-application-and-point-free-programming"></a>부분 응용 프로그램 및 포인트 없는 프로그래밍

F#은 부분 응용 프로그램을 지원하므로 포인트 프리 스타일로 프로그래밍하는 다양한 방법을 지원합니다. 이는 모듈 내에서 코드를 다시 사용하거나 무언가를 구현하는 데 도움이 될 수 있지만 공개적으로 노출하는 것은 아닙니다. 일반적으로 포인트 프리 프로그래밍은 그 자체로 미덕이 아니며 스타일에 몰두하지 않는 사람들에게 중요한 인지 장벽을 추가 할 수 있습니다.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>공용 API에서 부분 응용 프로그램 및 카레를 사용하지 마십시오.

거의 예외가 없는 경우 공용 API에서 부분 응용 프로그램을 사용하는 것은 소비자에게 혼동을 줄 수 있습니다. 일반적으로 `let`F# 코드의 -bound 값은 **함수 값이**아닌 **값입니다.** 값과 함수 값을 함께 혼합하면 특히 함수를 구성하는 것과 같은 `>>` 연산자와 결합된 경우 인지 오버헤드가 상당히 적은 코드 줄을 절약할 수 있습니다.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>포인트 프리 프로그래밍의 툴링 의미 고려

커리 함수는 인수에 레이블을 지정하지 않습니다. 이것은 툴링 에 영향을 미칩니다. 다음 두 가지 기능을 고려하십시오.

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

둘 다 유효한 함수이지만 `funcWithApplication` 커리 함수입니다. 편집기에서 해당 형식 위로 마우스를 가져가면 다음과 같은 이 표시됩니다.

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

호출 사이트에서 Visual `string` Studio와 같은 도구 설명은 입력 유형이 `int` 실제로 무엇을 나타내는지에 대한 의미 있는 정보를 제공하지 않습니다.

공개적으로 사용할 수 있는 `funcWithApplication` 점 없는 코드가 발생하는 경우 도구링이 인수에 대한 의미 있는 이름을 선택할 수 있도록 전체 θ-expansion를 수행하는 것이 좋습니다.

또한 포인트 없는 코드를 디버깅하는 것은 불가능하지는 않더라도 어려울 수 있습니다. 디버깅 도구는 이름에 바인딩된 값(예: `let` 바인딩)에 의존하므로 실행 중간에 중간 값을 검사할 수 있습니다. 코드에 검사할 값이 없는 경우 디버깅할 필요가 없습니다. 나중에 디버깅 도구는 이전에 실행된 경로를 기반으로 이러한 값을 합성하기 위해 진화할 수 있지만 *잠재적인* 디버깅 기능에 대한 베팅을 헤지하는 것은 좋지 않습니다.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>내부 상용구를 줄이는 기술로 부분 적용을 고려하십시오.

이전 지점과 달리 부분 응용 프로그램은 응용 프로그램 내부 또는 API의 내부를 더 깊게 줄이는 훌륭한 도구입니다. 상용구가 종종 다루기 힘든 더 복잡한 API의 구현을 단위 테스트하는 데 유용할 수 있습니다. 예를 들어 다음 코드에서는 이러한 프레임워크에 대한 외부 종속성을 취하고 관련 맞춤형 API를 학습하지 않고도 대부분의 모의 프레임워크가 제공하는 작업을 수행하는 방법을 보여 줍니다.

예를 들어 다음 솔루션 지형을 고려하십시오.

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj`다음과 같은 코드가 노출될 수 있습니다.

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

단위 `Transactions.doTransaction` `ImplementationLogic.Tests.fsproj` 테스트는 간단합니다.

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

모의 컨텍스트 `doTransaction` 개체를 부분적으로 적용하면 매번 조롱된 컨텍스트를 생성할 필요 없이 모든 단위 테스트에서 함수를 호출할 수 있습니다.

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member _.TheFirstMember() = ...
        member _.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

이 기술은 전체 코드베이스에 보편적으로 적용되어서는 안 되지만 복잡한 내부 및 단위 테스트에 대한 상용구를 줄이는 좋은 방법입니다.

## <a name="access-control"></a>Access Control

F#에는 .NET 런타임에서 사용할 수 있는 [액세스 제어에](../language-reference/access-control.md)대한 여러 옵션이 있습니다. 형식에만 사용할 수 있는 것이 아니라 함수에도 사용할 수 있습니다.

* 비유형`public` 및 멤버를 공개적으로 사용할 수 있어야 할 때까지 선호합니다. 또한 소비자가 커플하는 것을 최소화합니다.
* 모든 도우미 기능을 `private`유지 하려고 합니다.
* 도우미 함수가 `[<AutoOpen>]` 많을 경우 개인 도우미 함수 모듈에서 사용하는 것을 고려하십시오.

## <a name="type-inference-and-generics"></a>형식 추론 및 제네릭

형식 추론은 상용구를 많이 입력하는 것을 줄일 수 있습니다. 또한 F# 컴파일러의 자동 일반화를 사용하면 추가 노력 없이 더 많은 제네릭 코드를 작성할 수 있습니다. 그러나 이러한 기능은 보편적으로 좋지 않습니다.

* 공용 API에서 명시적 형식을 사용하여 인수 이름에 레이블을 지정하는 것이 고려되며 이에 대한 형식 추론에 의존하지 않습니다.

    그 이유는 **컴파일러가** 아니라 API의 모양을 제어해야 하기 때문입니다. 컴파일러는 형식을 유추할 때 훌륭한 작업을 수행할 수 있지만 형식에 의존하는 내부 가 변경된 경우 API 의 모양이 변경될 수 있습니다. 이것은 당신이 원하는 것 일 수 있지만, 그것은 거의 확실히 다운 스트림 소비자가 처리해야 할 것입니다 깨는 API 변경을 초래할 것이다. 대신 공용 API의 모양을 명시적으로 제어하는 경우 이러한 주요 변경 내용을 제어할 수 있습니다. DDD 용어로, 이것은 부패 방지 계층으로 생각할 수 있습니다.

* 일반 인수에 의미 있는 이름을 지정하는 것이 좋습니다.

    특정 도메인에 국한되지 않는 진정한 일반 코드를 작성하지 않는 한 의미 있는 이름은 다른 프로그래머가 작업 중인 도메인을 이해하는 데 도움이 될 수 있습니다. 예를 들어 문서 데이터베이스와 상호 작용하는 컨텍스트에서 명명된 `'Document` 형식 매개 변수를 사용하면 작업 중인 함수 나 멤버에서 일반 문서 형식을 사용할 수 있습니다.

* PascalCase를 사용 하 여 일반 형식 매개 변수의 이름을 지정 하는 것이 좋습니다.

    이것은 .NET에서 작업을 수행하는 일반적인 방법이므로 snake_case 나 camelCase보다는 파스칼 케이스를 사용하는 것이 좋습니다.

마지막으로 자동 일반화가 F# 또는 대규모 코드베이스를 새로 접하는 사람들에게 항상 도움이 되는 것은 아닙니다. 일반적인 구성 요소를 사용 하 여 인지 오버 헤드가 있다. 또한 자동으로 일반화된 함수가 다른 입력 형식과 함께 사용되지 않는 경우(이와 같이 사용하려는 경우는 물론) 해당 시점에서 일반 함수가 되는 것은 실질적인 이점이 없습니다. 작성하는 코드가 실제로 제네릭이 되는 것이 도움이 될지 항상 고려하십시오.

## <a name="performance"></a>성능

### <a name="prefer-structs-for-small-data-types"></a>작은 데이터 유형에 대한 구조체 선호

구조체(값 유형라고도 함)를 사용하면 일반적으로 개체 할당을 피하기 때문에 일부 코드의 성능이 향상될 수 있습니다. 그러나 구조체가 항상 "더 빠르게" 단추는 아닙니다: 구조체의 데이터 크기가 16바이트를 초과하는 경우 데이터를 복사하면 참조 형식을 사용하는 것보다 CPU 시간이 더 많이 소요될 수 있습니다.

구조체를 사용해야 하는지 확인하려면 다음 조건을 고려하십시오.

- 데이터 크기가 16바이트 이하인 경우.
- 이러한 데이터 형식 중 상당수가 실행 중인 프로그램의 메모리에 상주할 가능성이 있는 경우

첫 번째 조건이 적용되는 경우 일반적으로 구조체를 사용해야 합니다. 둘 다 적용 하는 경우 거의 항상 구조체를 사용 해야 합니다. 이전 조건이 적용되는 경우도 있지만 구조체를 사용하는 것이 참조 형식을 사용하는 것보다 더 좋거나 나쁘지는 않지만 드물다. 하지만 이런 식으로 변경할 때는 항상 측정하는 것이 중요하며 가정이나 직관에 따라 작동하지 않는 것이 중요합니다.

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a>작은 값 형식을 그룹화할 때 구조체 투플 선호

다음 두 가지 기능을 고려하십시오.

```fsharp
let rec runWithTuple t offset times =
    let offsetValues x y z offset =
        (x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let (x, y, z) = t
        let r = offsetValues x y z offset
        runWithTuple r offset (times - 1)

let rec runWithStructTuple t offset times =
    let offsetValues x y z offset =
        struct(x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let struct(x, y, z) = t
        let r = offsetValues x y z offset
        runWithStructTuple r offset (times - 1)
```

[BenchmarkDotNet과](https://benchmarkdotnet.org/)같은 통계 벤치마킹 도구를 사용하여 이러한 함수를 벤치마킹하면 구조형 투플을 사용하는 `runWithStructTuple` 함수가 40% 더 빠르게 실행되고 메모리가 할당되지 않는다는 것을 알 수 있습니다.

그러나 이러한 결과가 항상 사용자 고유의 코드에서 발생하는 것은 아닙니다. 함수를 "를 `inline`으로 표시하는 경우 참조 튜플을 사용하는 코드는 몇 가지 추가 최적화를 얻을 수 있거나 할당할 코드가 단순히 최적화될 수 있습니다. 성능에 관한 때마다 항상 결과를 측정해야 하며 가정이나 직관에 따라 작동하지 않아야 합니다.

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a>데이터 형식이 작은 경우 구조체 레코드 선호

앞에서 설명한 엄지 손가락 규칙에는 [F# 레코드 형식도](../language-reference/records.md)있습니다. 이를 처리하는 다음 데이터 형식 및 함수를 고려하십시오.

```fsharp
type Point = { X: float; Y: float; Z: float }

[<Struct>]
type SPoint = { X: float; Y: float; Z: float }

let rec processPoint (p: Point) offset times =
    let inline offsetValues (p: Point) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processPoint r offset (times - 1)

let rec processStructPoint (p: SPoint) offset times =
    let inline offsetValues (p: SPoint) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processStructPoint r offset (times - 1)
```

이는 이전 튜플 코드와 유사하지만 이번에는 예제에서 레코드와 인라인된 내부 함수를 사용합니다.

[BenchmarkDotNet과](https://benchmarkdotnet.org/)같은 통계 벤치마킹 도구를 사용하여 이러한 함수를 `processStructPoint` 벤치마킹하면 거의 60 % 더 빨리 실행되고 관리되는 힙에 아무 것도 할당하지 않습니다.

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a>데이터 형식이 작은 경우 구조체 구분 공용 구조체 선호

구조체 투플 및 레코드가 있는 성능에 대한 이전 관찰은 [F# 차별 된 공용 구조체에](../language-reference/discriminated-unions.md)대해서도 보유하고 있습니다. 다음 코드를 살펴보세요.

```fsharp
    type Name = Name of string

    [<Struct>]
    type SName = SName of string

    let reverseName (Name s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> Name

    let structReverseName (SName s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> SName
```

도메인 모델링을 위해 이와 같은 단일 사례 구별 공용 구조체를 정의하는 것이 일반적입니다. [BenchmarkDotNet과](https://benchmarkdotnet.org/)같은 통계 벤치마킹 도구를 사용하여 이러한 함수를 `structReverseName` 벤치마킹하면 작은 `reverseName` 문자열보다 약 25 % 더 빨리 실행되는 것을 알 수 있습니다. 큰 문자열의 경우 둘 다 거의 동일하게 수행됩니다. 따라서 이 경우 항상 구조체를 사용하는 것이 좋습니다. 앞서 언급했듯이, 항상 가정이나 직관에 따라 측정하고 작동하지 않습니다.

이전 예제에서는 구조체 구별 된 공용 구조체가 더 나은 성능을 보여 주었지만 도메인을 모델링 할 때 더 큰 구별 공용 구조체가 있는 것이 일반적입니다. 더 많은 복사가 포함될 수 있기 때문에 이와 같은 더 큰 데이터 형식은 작업에 따라 구조체인 경우 잘 수행되지 않을 수 있습니다.

### <a name="functional-programming-and-mutation"></a>함수형 프로그래밍 및 돌연변이

F# 값은 기본적으로 변경할 수 없으며 특정 클래스의 버그(특히 동시성 및 병렬 처리와 관련된 버그)를 방지할 수 있습니다. 그러나 경우에 따라 실행 시간 또는 메모리 할당의 최적(또는 합리적인) 효율성을 달성하기 위해 작업 범위가 상태 내 돌연변이를 사용하여 구현되는 것이 가장 좋습니다. 이는 키워드와 함께 F#을 사용하면 옵트인할 수 `mutable` 있습니다.

F `mutable` #에서의 사용은 기능적 순도와 확률을 느낄 수 있습니다. 이것은 이해할 수 있지만, 모든 곳에서 기능적 순도는 성능 목표와 상충될 수 있습니다. 타협은 호출자가 함수를 호출 할 때 발생하는 일에 대해 걱정할 필요가 있도록 돌연변이를 캡슐화하는 것입니다. 이를 통해 성능에 중요한 코드에 대한 돌연변이 기반 구현을 통해 기능 인터페이스를 작성할 수 있습니다.

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a>변경할 수 없는 인터페이스에서 변경 가능한 코드 래핑

참조 투명성을 목표로 하는 경우 성능에 중요한 함수의 가변적 하복부를 노출하지 않는 코드를 작성하는 것이 중요합니다. 예를 들어 다음 코드는 `Array.contains` F# 코어 라이브러리에서 함수를 구현합니다.

```fsharp
[<CompiledName("Contains")>]
let inline contains value (array:'T[]) =
    checkNonNull "array" array
    let mutable state = false
    let mutable i = 0
    while not state && i < array.Length do
        state <- value = array.[i]
        i <- i + 1
    state
```

이 함수를 여러 번 호출해도 기본 배열이 변경되지 않으며 사용할 때 변경 가능한 상태를 유지할 필요도 없습니다. 내부의 거의 모든 코드 줄이 돌연변이를 사용하더라도 참조적으로 투명합니다.

#### <a name="consider-encapsulating-mutable-data-in-classes"></a>클래스에서 가변 데이터 캡슐화 고려

이전 예제는 단일 함수를 사용하여 가변 가능한 데이터를 사용하여 작업을 캡슐화했습니다. 이 경우 보다 복잡한 데이터 집합에 항상 충분하지는 않습니다. 다음 함수 집합을 고려하십시오.

```fsharp
open System.Collections.Generic

let addToClosureTable (key, value) (t: Dictionary<_,_>) =
    if not (t.ContainsKey(key)) then
        t.Add(key, value)
    else
        t.[key] <- value

let closureTableCount (t: Dictionary<_,_>) = t.Count

let closureTableContains (key, value) (t: Dictionary<_, HashSet<_>>) =
    match t.TryGetValue(key) with
    | (true, v) -> v.Equals(value)
    | (false, _) -> false
```

이 코드는 수행되지만 호출자가 유지 관리하는 돌연변이 기반 데이터 구조를 노출합니다. 변경할 수 있는 기본 멤버가 없는 클래스 내부에 래핑할 수 있습니다.

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member _.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member _.Count = t.Count

    member _.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

`Closure1Table`기본 돌연변이 기반 데이터 구조를 캡슐화하므로 호출자가 기본 데이터 구조를 유지 관리하도록 강요하지 않습니다. 클래스는 호출자에게 세부 정보를 노출하지 않고 돌연변이 기반의 데이터와 루틴을 캡슐화하는 강력한 방법입니다.

#### <a name="prefer-let-mutable-to-reference-cells"></a>셀 `let mutable` 참조 선호

참조 셀은 값 자체가 아닌 값에 대한 참조를 나타내는 방법입니다. 성능이 중요한 코드에 사용할 수는 있지만 권장되지는 않습니다. 다음과 같은 예제를 참조하세요.

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

참조 셀의 사용은 이제 기본 데이터를 디레참조하고 다시 참조해야하는 모든 후속 코드를 "오염"합니다. 대신 다음을 고려하십시오. `let mutable`

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

lambda 식 중간에 있는 단일 돌연변이 점을 제외하고, 접촉하는 `acc` 다른 모든 코드는 정상 `let`-바인딩된 불변값의 사용과 다르지 않은 방식으로 그렇게 할 수 있습니다. 이렇게 하면 시간이 지남에 따라 쉽게 변경할 수 있습니다.

## <a name="object-programming"></a>개체 프로그래밍

F#은 개체 및 객체 지향(OO) 개념을 완전히 지원합니다. 많은 OO 개념이 강력하고 유용하지만 모든 개념이 사용하기에 이상적인 것은 아닙니다. 다음 목록은 상위 수준에서 OO 기능 범주에 대한 지침을 제공합니다.

**여러 상황에서 이러한 기능을 사용하는 것이 좋습니다.**

* 도트 표기`x.Length`()
* 인스턴스 멤버
* 암시적 생성자
* 정적 멤버
* 인덱서 표기 ()`arr.[x]`
* 명명된 인수 및 선택적 인수
* 인터페이스 및 인터페이스 구현

**먼저 이러한 기능에 도달하지 말고 문제를 해결하는 데 편리할 때 신중하게 적용하십시오.**

* 메서드 오버로드
* 캡슐화된 변경 가능 데이터
* 형식의 연산자
* 자동 속성
* 구현 `IDisposable` 및`IEnumerable`
* 형식 확장
* 이벤트
* 구조체
* 대리자
* 열거형

**일반적으로 이러한 기능을 사용해야 하는 경우가 아니면 이러한 기능을 사용하지 마십시오.**

* 상속 기반 유형 계층 구조 및 구현 상속
* 널 및`Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>상속보다 컴포지션 선호

[상속에 대한 컴포지션은](https://en.wikipedia.org/wiki/Composition_over_inheritance) 좋은 F# 코드가 준수할 수 있는 오랜 관용구입니다. 기본 원칙은 기본 클래스를 노출하지 말고 호출자에게 해당 기본 클래스에서 상속하여 기능을 얻도록 하는 것입니다.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>클래스가 필요하지 않은 경우 개체 식을 사용하여 인터페이스를 구현합니다.

[개체 표현식을](../language-reference/object-expressions.md) 사용하면 즉시 인터페이스를 구현할 수 있으므로 클래스 내에서 인터페이스를 사용할 필요 없이 구현된 인터페이스를 값으로 바인딩할 수 있습니다. 특히 _인터페이스만_ 구현해야 하고 전체 클래스가 필요하지 않은 경우에 편리합니다.

예를 들어, `open` 다음에 대한 문이 없는 기호를 추가한 경우 [Ionide에서](http://ionide.io/) 실행되는 코드는 코드 수정 작업을 제공합니다.

```fsharp
    let private createProvider () =
        { new CodeActionProvider with
            member this.provideCodeActions(doc, range, context, ct) =
                let diagnostics = context.diagnostics
                let diagnostic = diagnostics |> Seq.tryFind (fun d -> d.message.Contains "Unused open statement")
                let res =
                    match diagnostic with
                    | None -> [||]
                    | Some d ->
                        let line = doc.lineAt d.range.start.line
                        let cmd = createEmpty<Command>
                        cmd.title <- "Remove unused open"
                        cmd.command <- "fsharp.unusedOpenFix"
                        cmd.arguments <- Some ([| doc |> unbox; line.range |> unbox; |] |> ResizeArray)
                        [|cmd |]
                res
                |> ResizeArray
                |> U2.Case1
        }
```

Visual Studio 코드 API와 상호 작용할 때 클래스가 필요하지 않으므로 개체 표현식은 이에 대한 이상적인 도구입니다. 또한 임시 방식으로 테스트 루틴이 있는 인터페이스를 스텁하려는 경우 단위 테스트에도 유용합니다.

## <a name="consider-type-abbreviations-to-shorten-signatures"></a>서명을 줄이려면 약어 를 고려하십시오.

[유형 약어는](../language-reference/type-abbreviations.md) 함수 시그니처 또는 보다 복잡한 형식과 같은 다른 형식에 레이블을 할당하는 편리한 방법입니다. 예를 들어 다음 별칭은 딥 러닝 라이브러리인 [CNTK를](https://docs.microsoft.com/cognitive-toolkit/)사용하여 계산을 정의하는 데 필요한 레이블을 할당합니다.

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

이름은 `Computation` 별칭인 서명과 일치하는 함수를 나타내는 편리한 방법입니다. 이와 같은 유형 약어를 사용하면 편리하고 간결한 코드를 사용할 수 있습니다.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>도메인을 나타내는 유형 약어를 사용하지 마십시오.

유형 약어는 함수 시그니처에 이름을 지정하는 데 편리하지만 다른 형식을 축약할 때 혼동을 줄 수 있습니다. 이 약어를 고려하십시오.

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

이는 여러 가지 방법으로 혼동될 수 있습니다.

* `BufferSize`추상화가 아닙니다. 정수의 또 다른 이름일 뿐입니다.
* 공용 `BufferSize` API에 노출되면 단순한 `int`의미 이상으로 쉽게 잘못 해석될 수 있습니다. 일반적으로 도메인 유형에는 여러 특성이 있으며 와 같은 `int`기본 형식이 아닙니다. 이 약어는 이러한 가정을 위반합니다.
* (PascalCase)의 `BufferSize` 대/소문자는 이 형식에 더 많은 데이터가 있음을 의미합니다.
* 이 별칭은 함수에 명명된 인수를 제공하는 것과 비교하여 선명도를 높이지 않습니다.
* 약어는 컴파일된 IL에서 나타나지 않습니다. 정수일 뿐이며 이 별칭은 컴파일 타임 구문입니다.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

요약하면 유형 약어의 함정은 축약하는 형식에 대한 추상화가 **아니라는** 것입니다. 이전 예제에서는 `BufferSize` 추가 데이터가 `int` 없으며 `int` 이미 있는 것 외에 형식 시스템의 이점도 없는 표지 아래에 있습니다.

도메인을 나타내는 형식 약어를 사용하는 다른 방법은 단일 대/소문자 구분 공용 구조체를 사용하는 것입니다. 이전 샘플은 다음과 같이 모델링할 수 있습니다.

```fsharp
type BufferSize = BufferSize of int
```

기본 값과 측면에서 작동하는 코드를 `BufferSize` 작성하는 경우 임의의 정수에서 전달하는 대신 하나를 생성해야 합니다.

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

이렇게 하면 호출자는 함수를 호출하기 전에 `send` 값을 래핑하는 `BufferSize` 형식을 생성해야 하기 때문에 임의의 정수를 함수에 실수로 전달할 가능성이 줄어듭니다.
