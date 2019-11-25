---
title: F# 코딩 규칙
description: 코드를 작성할 F# 때 일반적인 지침과 관용구에 대해 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: 60eff6392d71caa54eeb438f2f6ba9db910f1bc1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978221"
---
# <a name="f-coding-conventions"></a>F# 코딩 규칙

다음 규칙은 많은 F# 코드 베이스를 사용 하 여 작업 하는 환경에서 공식화 됩니다. [좋은 F# 코드의 5 가지 원칙은](index.md#five-principles-of-good-f-code) 각 권장 사항의 기초가 됩니다. 이러한 요소는 [ F# 구성 요소 디자인 지침](component-design-guidelines.md)과 관련이 있지만 라이브러리와 같은 구성 F# 요소 뿐 아니라 모든 코드에 적용 됩니다.

## <a name="organizing-code"></a>코드 구성

F#는 코드를 구성 하는 두 가지 기본 방법인 모듈 및 네임 스페이스를 제공 합니다. 이와 유사 하지만 다음과 같은 차이점이 있습니다.

* 네임 스페이스는 .NET 네임 스페이스로 컴파일됩니다. 모듈은 정적 클래스로 컴파일됩니다.
* 네임 스페이스는 항상 최상위 수준입니다. 모듈은 최상위 수준 이며 다른 모듈 내에 중첩 될 수 있습니다.
* 네임 스페이스는 여러 파일에 걸쳐 있을 수 있습니다. 모듈은 사용할 수 없습니다.
* 모듈은 `[<RequireQualifiedAccess>]` 및 `[<AutoOpen>]`으로 데코레이팅 할 수 있습니다.

다음 지침은이를 사용 하 여 코드를 구성 하는 데 도움이 됩니다.

### <a name="prefer-namespaces-at-the-top-level"></a>최상위 수준에서 네임 스페이스 선호

공개적으로 사용할 수 있는 코드의 경우 네임 스페이스는 최상위 수준의 모듈에 우선적으로 사용할 수 있습니다. .NET 네임 스페이스로 컴파일되기 때문에 문제가 없는에서 C# 사용 가능 합니다.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

에서 F#유일 하 게 호출 하는 경우에만 최상위 모듈을 사용할 수 있습니다. C# 그러나 소비자의 경우에는`MyCode`모듈을 사용 하 여`MyClass`를 한정 해야 할 수 있습니다.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>신중 하 게 적용 `[<AutoOpen>]`

`[<AutoOpen>]` 구문은 호출자가 사용할 수 있는 항목의 범위를 pollute 수 있으며, 무언가가 제공 되는 위치에 대 한 답은 "매직"입니다. 일반적으로 좋은 방법은 아닙니다. 이 규칙에 대 한 예외는 F# 핵심 라이브러리 자체 이지만이 사실은 약간의 논쟁 이기도 합니다.

그러나 공용 api와 별도로 구성 하려는 공용 API에 대 한 도우미 기능이 있는 경우 편리 합니다.

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

이렇게 하면 호출할 때마다 도우미를 완전히 정규화 하지 않고도 함수의 공용 API에서 구현 세부 정보를 완전히 구분할 수 있습니다.

또한 네임 스페이스 수준에서 확장 메서드와 식 작성기를 표시 하는 것은 `[<AutoOpen>]`로 깔끔하게 표현할 수 있습니다.

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>이름이 충돌 하거나 가독성에 도움이 될 때마다 `[<RequireQualifiedAccess>]`를 사용 합니다.

모듈에 `[<RequireQualifiedAccess>]` 특성을 추가 하면 모듈이 열리지 않을 수 있으며 모듈의 요소에 대 한 참조에 명시적으로 정규화 된 액세스가 필요 함을 나타냅니다. 예를 들어 `Microsoft.FSharp.Collections.List` 모듈에는이 특성이 있습니다.

이는 모듈의 함수 및 값에 다른 모듈의 이름과 충돌할 가능성이 있는 이름이 있는 경우에 유용 합니다. 정규화 된 액세스를 요구 하면 라이브러리의 장기 유지 관리 및 진화 크게 증가 합니다.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>`open` 문 정렬 토폴로지 방식으로

에서 F#선언 순서는 `open`문을 포함 하 여 중요 합니다. 이는와 C#는 달리`using`및`using static`의 효과는 파일에서 해당 문의 순서와는 독립적입니다.

에서 F#범위로 열린 요소는 이미 존재 하는 다른 요소를 숨길 수 있습니다. 즉, `open` 문을 다시 정렬 하 여 코드의 의미를 변경할 수 있습니다. 따라서 사전순으로와 같은 모든 `open` 문을 임의로 정렬 하는 것은 일반적으로 권장 되지 않습니다. 목록 다른 동작을 생성할 수 있습니다.

대신 [토폴로지 방식으로](https://en.wikipedia.org/wiki/Topological_sorting)를 정렬 하는 것이 좋습니다. 즉, 시스템 _계층이_ 정의 된 순서에 따라 `open` 문을 정렬 합니다. 다른 토폴로지 계층 내에서 영숫자 정렬을 수행 하는 것도 고려할 수 있습니다.

예를 들어 F# 컴파일러 서비스 공용 API 파일에 대 한 토폴로지 정렬은 다음과 같습니다.

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

줄 바꿈으로 인해 토폴로지 계층이 분리 되며, 각 계층은 나중에 사전순으로 정렬 됩니다. 이렇게 하면 값을 실수로 숨기는 대신 코드가 완전히 구성 됩니다.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>파생 작업이 있는 값을 포함 하는 클래스 사용

값을 초기화 하는 경우에는 데이터베이스 또는 다른 원격 리소스에 대 한 컨텍스트 인스턴스화와 같은 부작용이 발생할 수 있습니다. 모듈에서 이러한 항목을 초기화 하 고 이후 함수에서 사용 하는 것이 좋습니다.

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

이는 다음과 같은 몇 가지 이유로 인해 종종 잘못 된 개념입니다.

먼저 `dep1` 및 `dep2`를 사용 하 여 응용 프로그램 구성이 코드 베이스에 푸시됩니다. 이는 더 큰 코드 베이스에서 유지 관리 하기가 어렵습니다.

두 번째로, 구성 요소가 여러 스레드를 사용 하는 경우 정적으로 초기화 된 데이터에는 스레드로부터 안전 하지 않은 값을 포함 하면 안 됩니다. `dep3`에서이를 명확 하 게 위반 합니다.

마지막으로, 모듈 초기화는 전체 컴파일 단위에 대 한 정적 생성자로 컴파일됩니다. 해당 모듈의 let 바인딩 값 초기화에 오류가 발생 하는 경우 응용 프로그램의 전체 수명 동안 캐시 된 `TypeInitializationException`으로 매니페스트 됩니다. 이는 진단 하기 어려울 수 있습니다. 일반적으로 원인을 확인할 수 있는 내부 예외가 있지만, 그렇지 않은 경우 근본 원인을 알려 주지 않습니다.

대신 간단한 클래스를 사용 하 여 종속성을 유지 하면 됩니다.

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

이렇게 하면 다음을 수행할 수 있습니다.

1. API 자체 외부에서 모든 종속 상태를 푸시합니다.
2. 이제 API 외부에서 구성을 수행할 수 있습니다.
3. 종속 값을 초기화 하는 동안 발생 하는 오류는 `TypeInitializationException`로 매니페스트가 될 수 없습니다.
4. 이제 API를 더 쉽게 테스트할 수 있습니다.

## <a name="error-management"></a>오류 관리

대량 시스템에서 오류를 관리 하는 것은 복잡 하 고 미묘한 시스템을 내결함성이 있는지 확인 하는 실버 글머리 기호가 없습니다. 다음 지침에서는이 까다로운 공간을 탐색 하는 지침을 제공 합니다.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>도메인의 내장 형식에서 오류 사례 및 잘못 된 상태를 나타냅니다.

[구별 된 공용 구조체](../language-reference/discriminated-unions.md)를 F# 사용 하면 형식 시스템에서 잘못 된 프로그램 상태를 나타내는 기능을 제공 합니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

이 경우 은행 계좌에서 입출금 계좌 money가 실패할 수 있는 알려진 세 가지 방법이 있습니다. 각 오류 사례는 형식으로 표시 되므로 프로그램 전체에서 안전 하 게 처리할 수 있습니다.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

일반적으로 도메인에서 어떤 작업을 **수행할 수 있는지에 대** 한 다양 한 방법을 모델링할 수 있는 경우 오류 처리 코드는 일반 프로그램 흐름 외에도 처리 해야 하는 것으로 처리 되지 않습니다. 단순히 일반적인 프로그램 흐름의 일부 이며 **예외적인**것으로 간주 되지 않습니다. 이에는 다음과 같은 두 가지 주요 이점이 있습니다.

1. 시간이 지남에 따라 도메인을 변경 하면 더 쉽게 유지 관리할 수 있습니다.
2. 오류 사례는 단위 테스트를 용이 하 게 합니다.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>형식을 사용 하 여 오류를 나타낼 수 없는 경우 예외를 사용 합니다.

모든 오류가 문제 도메인에 표시 되는 것은 아닙니다. 이러한 종류의 *오류는 본질적* 으로 예외 이므로에서 F#예외를 발생 시키고 catch 할 수 있습니다.

먼저 [예외 디자인 지침](../../standard/design-guidelines/exceptions.md)을 읽는 것이 좋습니다. 이러한 항목은에 F#도 적용 됩니다.

예외를 발생 시키기 위해 F# 에서 사용할 수 있는 기본 구문은 다음과 같은 기본 설정 순서로 고려 되어야 합니다.

| 기능 | 구문 | 용도 |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | 지정 된 인수 이름을 사용 하 여 `System.ArgumentNullException`을 발생 시킵니다. |
| `invalidArg` | `invalidArg "argumentName" "message"` | 지정 된 인수 이름 및 메시지를 사용 하 여 `System.ArgumentException`을 발생 시킵니다. |
| `invalidOp` | `invalidOp "message"` | 지정 된 메시지를 사용 하 여 `System.InvalidOperationException`을 발생 시킵니다. |
|`raise`| `raise (ExceptionType("message"))` | 예외를 throw 하는 일반적인 용도의 메커니즘입니다. |
| `failwith` | `failwith "message"` | 지정 된 메시지를 사용 하 여 `System.Exception`을 발생 시킵니다. |
| `failwithf` | `failwithf "format string" argForFormatString` | 형식 문자열과 해당 입력에 의해 결정 되는 메시지를 사용 하 여 `System.Exception`을 발생 시킵니다. |

`nullArg`, `invalidArg` 및 `invalidOp`를 사용 하 여 해당 하는 경우 `ArgumentNullException`, `ArgumentException` 및 `InvalidOperationException`을 throw 합니다.

`failwith` 및 `failwithf` 함수는 특정 예외가 아닌 기본 `Exception` 형식을 발생 시키기 때문에 일반적으로 피해 야 합니다. [예외 디자인 지침](../../standard/design-guidelines/exceptions.md)에 따라 가능 하면 더 구체적인 예외를 발생 시킬 수 있습니다.

### <a name="using-exception-handling-syntax"></a>예외 처리 구문 사용

F#에서는`try...with`구문을 통해 예외 패턴을 지원 합니다.

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

패턴 일치를 사용 하 여 예외 발생 시 수행할 기능을 조정 하는 것은 코드를 깨끗 하 게 유지 하려는 경우 다소 복잡할 수 있습니다. 이를 처리 하는 방법 중 하나는 오류 사례를 제외 하 고 예외 자체를 사용 하 여 기능을 그룹화 하는 수단으로 [활성 패턴](../language-reference/active-patterns.md) 을 사용 하는 것입니다. 예를 들어, 예외를 throw 하는 경우 예외 메타 데이터에 중요 한 정보를 포함 하는 API를 사용할 수 있습니다. 활성 패턴 내에서 캡처된 예외의 본문에 유용한 값을 래핑 해제 하 고이 값을 반환 하면 몇 가지 상황에서 유용할 수 있습니다.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>Monadic 오류 처리를 사용 하 여 예외 바꾸기

예외는 함수형 프로그래밍에서 약간의 금기시 표시 됩니다. 실제로 예외는 순도를 위반 하므로 매우 작동 하지 않는 것을 고려 하는 것이 안전 합니다. 그러나이 경우 코드를 실행 해야 하는 현실을 무시 하 고 런타임 오류가 발생할 수 있습니다. 일반적으로 불쾌 예상치를 최소화 하기 위해 대부분의 항목이 순수 또는 합계는 아닌 것으로 가정 하 여 코드를 작성 합니다.

.NET 런타임 및 언어 간 에코 시스템의 관련성 및 적합성과 관련 하 여 다음과 같은 핵심 장점/측면을 고려해 야 합니다.

1. 여기에는 문제를 디버깅할 때 매우 유용한 자세한 진단 정보가 포함 되어 있습니다.
2. 런타임 및 기타 .NET 언어에서 잘 이해할 수 있습니다.
3. 이를 통해 의미 체계의 일부 하위 집합을 임시 기반으로 구현 하 여 예외를 *방지* 하는 코드와 비교할 때 중요 한 상용구를 줄일 수 있습니다.

이 세 번째 지점은 중요 합니다. 복잡 한 복잡 한 작업의 경우 예외를 사용 하지 못하면 다음과 같은 구조를 처리할 수 있습니다.

```fsharp
Result<Result<MyType, string>, string list>
```

"Stringly 형식" 오류에 대 한 패턴 일치와 같은 손상 된 코드를 쉽게 일으킬 수 있습니다.

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

또한 "더 좋은" 형식을 반환 하는 "simple" 함수를 원하는 경우 예외를 무시 할 수 있습니다.

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

불행 하 게도 파일 시스템에서 발생할 수 있는 많은 작업을 기반으로 많은 예외를 throw 할 수 있으며 `tryReadAllText`,이 코드는 실제로 사용자 환경에서 발생할 수 있는 문제에 대 한 정보를 모두 삭제 합니다. 이 코드를 결과 형식으로 바꾸면 "stringly" 오류 메시지 구문 분석으로 돌아갑니다.

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

예외 개체 자체를 `Error` 생성자에 배치 하면 함수 대신 호출 사이트에서 예외 형식을 올바르게 처리 하는 것이 좋습니다. 이렇게 하면 확인 된 예외가 생성 되며이는 API의 호출자로 처리 하지 어렵습니다 않습니다.

위의 예제에 대 한 좋은 대안은 *특정* 예외를 catch 하 고 해당 예외의 컨텍스트에서 의미 있는 값을 반환 하는 것입니다. `tryReadAllText` 함수를 다음과 같이 수정 하는 경우 `None`는 보다 의미 있는 것입니다.

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

이 함수는 모두 catch로 작동 하는 대신, 파일을 찾을 수 없는 경우를 적절 하 게 처리 하 고 해당 의미를 반환에 할당 합니다. 이 반환 값은 컨텍스트 정보를 삭제 하거나 호출자가 코드의 해당 지점에서 관련이 없을 수 있는 사례를 처리 하도록 강제 하는 동시에 해당 오류 사례에 매핑될 수 있습니다.

`Result<'Success, 'Error>`와 같은 형식은 중첩 되지 않은 기본 작업에 적합 하며 F# , 선택적 형식은 어떤 항목이 *어떤 항목* 을 반환 하거나 *아무 것도*반환 하지 않는 경우를 나타내는 데 적합 합니다. 그러나 예외를 대체 하지는 않지만 예외를 대체 하려는 시도에서 사용 하면 안 됩니다. 대신, 예외 및 오류 관리 정책의 특정 측면을 대상 방식으로 처리 하기 위해 신중 하 게 적용 해야 합니다.

## <a name="partial-application-and-point-free-programming"></a>부분 응용 프로그램 및 지점 없는 프로그래밍

F#에서는 부분 응용 프로그램을 지원 하므로 특정 시점 스타일로 프로그래밍 하는 다양 한 방법을 사용할 수 있습니다. 이는 모듈 내에서 코드를 다시 사용 하거나 항목을 구현 하는 데 도움이 될 수 있지만 일반적으로 공개적으로 노출 하는 것은 아닙니다. 일반적으로 지점 없는 프로그래밍은 그 자체로는 적합 하지 않으며 스타일에 사용 되지 않은 사용자에 게 상당한 인식 장벽을 추가할 수 있습니다.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>공용 Api에서 부분 응용 프로그램 및 currying 사용 안 함

거의 예외를 제외 하 고 공용 Api에서 부분 응용 프로그램을 사용 하는 것은 소비자에 게 혼란 스 러 울 수 있습니다. 일반적으로 코드의 F# `let`바인딩된 값은 **함수 값**이 아닌 **값**입니다. 값과 함수 값을 함께 사용 하면 특히 함수를 작성 하는 `>>`와 같은 연산자와 함께 사용 하는 경우 exchange에서 적은 수의 코드 줄을 저장할 수 있습니다.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>지점 없는 프로그래밍에 대 한 도구 의미 고려

커리 함수는 인수에 레이블을 나타내지 않습니다. 이는 도구에 영향을 미칩니다. 다음 두 가지 함수를 고려 하세요.

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

둘 다 유효한 함수 이지만 `funcWithApplication`은 커리 된 함수입니다. 편집기에서 해당 유형을 가리키면 다음과 같이 표시 됩니다.

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

호출 사이트에서 Visual Studio와 같은 도구 설명에서는 `string` 및 `int` 입력 형식이 실제로 나타내는 것과 같은 의미 있는 정보를 제공 하지 않습니다.

공개적으로 사용할 수 있는 `funcWithApplication`와 같은 지점 없는 코드가 발생 하는 경우 도구에서 인수에 대해 의미 있는 이름을 선택할 수 있도록 전체 η 확장을 수행 하는 것이 좋습니다.

또한 디버깅 지점-무료 코드는 불가능 한 경우 어려울 수 있습니다. 디버깅 도구는 이름에 바인딩된 값 (예: `let` 바인딩)을 사용 하므로 중간 값을 실행을 통해 중간 값을 검사할 수 있습니다. 코드에 검사할 값이 없는 경우에는 디버그할 항목이 없습니다. 나중에 디버깅 도구는 이전에 실행 된 경로를 기반으로 이러한 값을 합성 하기 위해 발전 했을 수 있지만 *잠재적* 디버깅 기능에 대 한 사용자의 수를 추가 하지 않는 것이 좋습니다.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>부분 응용 프로그램을 내부 상용구를 줄이기 위한 기술로 고려

이전 지점과는 달리 부분 응용 프로그램은 응용 프로그램 내에서 상용구를 줄이는 데 사용할 수 있는 훌륭한 도구 또는 API의 심층적 내부 도구입니다. 이러한 Api는 자주 사용 하는 것이 어려운 Api의 구현을 단위 테스트 하는 데 유용 하 게 사용할 수 있습니다. 예를 들어 다음 코드는 이러한 프레임 워크에 대 한 외부 종속성을 사용 하지 않고 관련 맞춤식 API를 배워야 하는 대부분의 모의 프레임 워크에서 제공 하는 작업을 수행 하는 방법을 보여 줍니다.

예를 들어 다음 솔루션 토폴로지를 살펴보세요.

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj` 다음과 같은 코드를 노출할 수 있습니다.

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

`ImplementationLogic.Tests.fsproj`의 단위 테스트 `Transactions.doTransaction`은 쉽습니다.

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

모의 컨텍스트 개체를 사용 하 여 `doTransaction`을 부분적으로 적용 하면 매번 모의 컨텍스트를 생성할 필요 없이 모든 단위 테스트에서 함수를 호출할 수 있습니다.

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

이 기법은 전체 코드 베이스에 전체적으로 적용 되는 것은 아니지만, 복잡 한 내부 및 이러한 내부 단위 테스트를 위해 상용구를 줄이는 것이 좋은 방법입니다.

## <a name="access-control"></a>액세스 제어

F#에는 .NET 런타임에서 사용할 수 있는 것으로 상속 되는 [Access control](../language-reference/access-control.md)에 대 한 여러 옵션이 있습니다. 이러한 형식은 형식에만 사용할 수 있으며 함수에도 사용할 수 있습니다.

* 공개적으로 사용할 수 있어야 할 때까지`public` 되지 않는 형식 및 멤버를 선호 합니다. 이를 통해 소비자가 두 가지를 최소화 합니다.
* 모든 도우미 기능 `private`유지 하기 위해 노력 합니다.
* 도우미 함수의 전용 모듈에 `[<AutoOpen>]`를 사용 하는 것이 좋습니다.

## <a name="type-inference-and-generics"></a>형식 유추 및 제네릭

형식 유추를 통해 여러 상용구를 입력 하는 것을 줄일 수 있습니다. F# 컴파일러의 자동 일반화를 통해 사용자의 추가 노력 없이 보다 일반적인 코드를 작성할 수 있습니다. 그러나 이러한 기능은 보편적이 지 않습니다.

* 공용 Api에서 명시적 형식의 인수 이름을 지정 하 고이에 대 한 형식 유추를 사용 하지 않는 것이 좋습니다.

    그 이유는 컴파일러가 아니라 API의 모양을 **제어 하는 것입니다.** 컴파일러는 형식을 유추 하는 데 적절 한 작업을 수행할 수 있지만, 사용 하는 내부에 변경 된 형식이 있는 경우 API의 모양을 변경할 수 있습니다. 이는 원하는 대로 지정할 수 있지만 다운스트림 소비자가 처리 해야 하는 API 변경이 거의 발생 하지 않습니다. 대신 공용 API의 셰이프를 명시적으로 제어 하는 경우 이러한 주요 변경 사항을 제어할 수 있습니다. DDD 용어로는이를 손상 방지 계층으로 간주할 수 있습니다.

* 제네릭 인수에 의미 있는 이름을 지정 하는 것이 좋습니다.

    특정 도메인에 한정 되지 않는 진정한 제네릭 코드를 작성 하지 않는 한 의미 있는 이름을 사용 하면 다른 프로그래머가 작업 중인 도메인을 이해 하는 데 도움이 될 수 있습니다. 예를 들어 문서 데이터베이스와 상호 작용 하는 컨텍스트에서 `'Document` 라는 형식 매개 변수를 사용 하면 작업 중인 함수 또는 멤버가 일반 문서 형식을 허용할 수 있습니다.

* 제네릭 형식 매개 변수의 이름을 지정 하는 것이 좋습니다.

    이것은 .NET에서 작업을 수행 하는 일반적인 방법 이므로 snake_case 또는 camelCase이 아닌 다른 사용자를 사용 하는 것이 좋습니다.

마지막으로, 자동 일반화는 항상 또는 규모가 많은 코드 베이스를 처음 접하는 F# 사용자에 게는 유용 하지 않습니다. 일반적으로 사용 되는 구성 요소를 사용 하는 경우 인지 오버 헤드가 발생 합니다. 또한 자동으로 일반화 된 함수를 다른 입력 형식으로 사용 하지 않는 경우 (예를 들어 사용 하려는 경우에만) 해당 시점에서 제네릭이 될 수 있습니다. 작성 하는 코드의 경우에는 항상 제네릭을 활용 하는 것이 좋습니다.

## <a name="performance"></a>성능

F#기본적으로 값은 변경할 수 없습니다 .이를 통해 특정 버그 클래스 (특히 동시성 및 병렬 처리와 관련 된 클래스)를 피할 수 있습니다. 그러나 특정 한 경우에는 실행 시간이 나 메모리 할당의 최적 또는 적절 한 효율성을 얻기 위해 상태의 내부 변형을 사용 하 여 작업 범위를 가장 잘 구현할 수 있습니다. 이는`mutable`키워드를 사용 하 여 옵트인 F# 할 때 사용할 수 있습니다.

그러나의 F# `mutable` 사용 하는 것은 함수 순도와는 다를 수 있습니다. 이는 순도에서 [참조 투명도](https://en.wikipedia.org/wiki/Referential_transparency)로 기대치를 조정 하는 경우에 유용 합니다. 참조 투명도-비 순도-함수를 작성할 F# 때의 끝 목표입니다. 이렇게 하면 성능에 중요 한 코드를 위해 변형 기반 구현에 대해 함수형 인터페이스를 작성할 수 있습니다.

### <a name="wrap-mutable-code-in-immutable-interfaces"></a>변경할 수 없는 인터페이스에서 변경 가능한 코드 줄 바꿈

참조 투명성을 목표로 하는 경우 성능에 중요 한 함수의 변경 가능한 underbelly을 노출 하지 않는 코드를 작성 하는 것이 중요 합니다. 예를 들어 다음 코드는 F# 핵심 라이브러리에서 `Array.contains` 함수를 구현 합니다.

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

이 함수를 여러 번 호출 하면 기본 배열이 변경 되지 않으며,이 함수를 사용 하 여 변경 가능한 상태를 유지 관리 하지 않아도 됩니다. 거의 모든 코드 줄에서 변형을 사용 하는 경우에도 투명 하 게 엔터티와.

### <a name="consider-encapsulating-mutable-data-in-classes"></a>변경 가능한 데이터를 클래스에 캡슐화 하는 것이 좋습니다.

이전 예제에서는 단일 함수를 사용 하 여 변경 가능한 데이터를 사용 하는 작업을 캡슐화 했습니다. 이는 더 복잡 한 데이터 집합에는 항상 충분 하지 않습니다. 다음 함수 집합을 고려 하십시오.

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

이 코드는 성능이 우수 하지만 호출자가 유지 관리 해야 하는 변형 기반 데이터 구조를 노출 합니다. 변경할 수 있는 기본 멤버가 없는 클래스 내부에이를 래핑할 수 있습니다.

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

`Closure1Table`는 기본 변형 기반 데이터 구조를 캡슐화 하 여 호출자가 내부 데이터 구조를 유지 하지 않도록 합니다. 클래스는 세부 정보를 호출자에 게 노출 하지 않고 변형 기반 데이터 및 루틴을 캡슐화 하는 강력한 방법입니다.

### <a name="prefer-let-mutable-to-reference-cells"></a>셀을 참조 하는 `let mutable` 선호

참조 셀은 값 자체가 아닌 값에 대 한 참조를 표시 하는 방법입니다. 성능이 중요 한 코드에는 사용 될 수 있지만 일반적으로 권장 되지는 않습니다. 다음 예제를 참조하세요.

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

이제 참조 셀을 사용 하 여 기본 데이터를 역참조 하 고 다시 참조 해야 하는 모든 후속 코드를 "pollutes" 합니다. 대신 `let mutable`을 고려 하십시오.

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

람다 식의 중간에 있는 단일 변형 지점 외에도 `acc`에 해당 하는 다른 모든 코드는 일반적인 `let`바인딩된 변경 불가능 값의 사용량과 다른 방식으로이 작업을 수행할 수 있습니다. 이렇게 하면 시간이 지남에 따라 더 쉽게 변경할 수 있습니다.

## <a name="object-programming"></a>개체 프로그래밍

F#개체 및 개체 지향 (OO) 개념을 완벽 하 게 지원 합니다. 대부분의 OO 개념은 강력 하 고 유용 하지만 모두 사용 하기에 적합 한 것은 아닙니다. 다음 목록에서는 상위 수준에서의 OO 기능 범주에 대 한 지침을 제공 합니다.

**다음과 같은 다양 한 상황에서 이러한 기능을 사용 하는 것이 좋습니다.**

* 점 표기법 (`x.Length`)
* 인스턴스 멤버
* 암시적 생성자
* 정적 멤버
* 인덱서 표기법 (`arr.[x]`)
* 명명 된 인수 및 선택적 인수
* 인터페이스 및 인터페이스 구현

**이러한 기능에 대해 먼저 도달 하지 말고 문제를 해결 하는 데 편리한 경우에는 신중 하 게 적용 해야 합니다.**

* 메서드 오버로드
* 캡슐화 된 변경 가능한 데이터
* 형식에 대 한 연산자
* 자동 속성
* `IDisposable` 및 `IEnumerable` 구현
* 형식 확장
* 이벤트
* Structs
* 대리자
* 열거형

**일반적으로 이러한 기능을 사용 해야 하는 경우를 방지 합니다.**

* 상속 기반 형식 계층 구조 및 구현 상속
* Null 및 `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>상속 보다 컴퍼지션 선호

[상속을 통한 컴퍼지션](https://en.wikipedia.org/wiki/Composition_over_inheritance) 은 좋은 F# 코드가 준수 하는 긴 방법입니다. 기본 원칙은 기본 클래스를 노출 하지 않고 해당 기본 클래스에서 호출자가 강제로 상속 하 여 기능을 가져와야 한다는 것입니다.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>클래스가 필요 하지 않은 경우 개체 식을 사용 하 여 인터페이스 구현

[개체 식을](../language-reference/object-expressions.md) 사용 하면 인터페이스를 즉석에서 구현 하 고 구현 된 인터페이스를 클래스 내부에서 수행할 필요 없이 값에 바인딩할 수 있습니다. 특히 인터페이스를 구현 하기만 하면 전체 _클래스가 필요 하지_ 않은 경우 편리 합니다.

예를 들어,에 대 한 `open` 문이 없는 기호를 추가한 경우 코드 수정 [작업을 제공 하기 위해](http://ionide.io/) 다음 코드를 사용할 때 코드를 수정 해야 합니다.

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

Visual Studio Code API와 상호 작용할 때 클래스가 필요 하지 않기 때문에 개체 식이이에 적합 한 도구입니다. 또한 테스트 루틴이 포함 된 인터페이스를 임시 방식으로 스텁 하려는 경우 단위 테스트에도 유용 합니다.

## <a name="consider-type-abbreviations-to-shorten-signatures"></a>서명을 줄이려면 형식 약어를 고려 하십시오.

[형식 약어](../language-reference/type-abbreviations.md) 는 함수 시그니처 또는 보다 복잡 한 형식과 같은 다른 형식에 레이블을 할당 하는 편리한 방법입니다. 예를 들어 다음 별칭은 심층 학습 라이브러리인 [CNTK](https://docs.microsoft.com/cognitive-toolkit/)를 사용 하 여 계산을 정의 하는 데 필요한 항목에 레이블을 할당 합니다.

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

`Computation` 이름은 별칭을 추가할 시그니처와 일치 하는 함수를 나타내는 편리한 방법입니다. 이와 같은 형식 약어를 사용 하면 편리 하며 더 간결한 코드를 사용할 수 있습니다.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>도메인을 나타내기 위해 형식 약어를 사용 하지 마십시오.

형식 약어는 함수 시그니처에 이름을 제공 하는 데 편리 하지만 다른 형식을 abbreviating 때 혼동 될 수 있습니다. 다음 약어를 살펴보세요.

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

이는 여러 가지 방법으로 혼동 될 수 있습니다.

* `BufferSize`는 추상이 아닙니다. 단지 정수에 대 한 다른 이름입니다.
* `BufferSize` 공용 API에 노출 되는 경우 `int`만을 의미 하는 것으로 쉽게 잘못 해석 될 수 있습니다. 일반적으로 도메인 형식은 여러 특성을 가지 며 `int`와 같은 기본 형식이 아닙니다. 이 약어는 이러한 가정을 위반 합니다.
* `BufferSize` (고 대/소문자)의 대/소문자 구분은이 형식에 더 많은 데이터가 포함 되어 있음을 의미 합니다.
* 이 별칭은 함수에 명명 된 인수를 제공 하는 것과 비교 하 여 향상 된 명확성을 제공 하지 않습니다.
* 약어는 컴파일된 IL에서 매니페스트 되지 않습니다. 단지 정수 이며이 별칭은 컴파일 타임 구문입니다.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

요약 하자면, 형식 약어의 단점은 abbreviating 된 형식에 대 한 추상화가 **아니라** 는 것입니다. 앞의 예제에서 `BufferSize`는 추가 데이터를 포함 하지 않는 커버 아래에 있는 `int` 뿐만 아니라 이미 있는 `int` 외에도 유형 시스템의 이점도 있습니다.

형식 약어를 사용 하 여 도메인을 나타내는 다른 방법은 단일 대/소문자 구분 공용 구조체를 사용 하는 것입니다. 이전 샘플은 다음과 같이 모델링할 수 있습니다.

```fsharp
type BufferSize = BufferSize of int
```

`BufferSize`와 해당 내부 값을 기준으로 작동 하는 코드를 작성 하는 경우 임의의 정수를 전달 하는 대신 하나를 생성 해야 합니다.

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

이렇게 하면 호출자가 함수를 호출 하기 전에 값을 래핑하는 `BufferSize` 형식을 생성 해야 하기 때문에 임의의 정수를 `send` 함수에 잘못 전달할 가능성이 줄어듭니다.
