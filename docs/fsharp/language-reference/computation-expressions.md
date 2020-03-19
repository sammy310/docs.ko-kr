---
title: 계산 식
description: 컨트롤 흐름 구문 및 바인딩을 사용하여 순서를 정하고 결합할 수 있는 F#에서 계산을 작성하기 위한 편리한 구문을 만드는 방법에 대해 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: 55406cc12d9e6e890fe69d712f79486d23b84452
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401084"
---
# <a name="computation-expressions"></a>계산 식

F#의 계산 식은 컨트롤 흐름 구문 및 바인딩을 사용하여 순서를 정하고 결합할 수 있는 계산을 작성하는 데 편리한 구문을 제공합니다. 계산 표현의 종류에 따라, 그들은 monads, 모노이드, 모나드 변압기 및 응용 프로그램 functors을 표현하는 방법으로 생각할 수 있습니다. 그러나 하스켈의 *표기법 과* 같은 다른 언어와 달리 단일 추상화에 연결되지 않으며 매크로 또는 다른 형태의 메타프로그래밍에 의존하여 편리하고 상황에 맞는 구문을 구문으로 설정하지 않습니다.

## <a name="overview"></a>개요

계산은 다양한 형태를 취할 수 있습니다. 가장 일반적인 계산 형태는 이해하고 수정하기 쉬운 단일 스레드 실행입니다. 그러나 모든 형태의 계산이 단일 스레드 실행만큼 간단하지는 않습니다. 일부 사례:

- 비결정적 계산
- 비동기 계산
- 유익한 계산
- 생성 계산

일반적으로 응용 프로그램의 특정 부분에서 수행해야 하는 *상황에 맞는* 계산이 있습니다. 상황에 맞는 코드를 작성하는 것은 추상화 없이 주어진 컨텍스트 외부에서 계산을 "누설"하기 쉽기 때문에 어려울 수 있습니다. 이러한 추상화는 종종 혼자서 작성하기가 어렵기 때문에 F#에는 이렇게 계산 식을 수행하는 일반화된 방법이 **있습니다.**

계산 식은 컨텍스트에 민감한 계산을 인코딩하기 위한 균일한 구문 및 추상화 모델을 제공합니다.

모든 계산 식은 *빌더* 유형에 의해 뒷받침됩니다. 빌더 유형은 계산 식에 사용할 수 있는 작업을 정의합니다. 사용자 지정 계산 식을 만드는 방법을 보여 주므로 [새 유형의 계산 표현식](computation-expressions.md#creating-a-new-type-of-computation-expression)만들기를 참조하세요.

### <a name="syntax-overview"></a>구문 개요

모든 계산 식에는 다음과 같은 형식이 있습니다.

```fsharp
builder-expr { cexper }
```

여기서는 `builder-expr` 계산 식을 정의하는 빌더 형식의 이름이며 `cexper` 계산 식의 식 본문입니다. 예를 들어 `async` 계산 식 코드는 다음과 같을 수 있습니다.

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

이전 예제와 같이 계산 식 내에서 사용할 수 있는 특수한 추가 구문이 있습니다. 계산 식을 사용하면 다음 식 형식이 가능합니다.

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

이러한 각 키워드 및 기타 표준 F# 키워드는 백업 빌더 유형에 정의된 경우에만 계산 식에서 사용할 수 있습니다. 유일한 예외는 `match!`결과에 패턴 `let!` 일치를 다음에 사용하는 데 해당되는 구문 설탕입니다.

빌더 형식은 계산 식의 조각이 결합되는 방식을 제어하는 특수 메서드를 정의하는 개체입니다. 즉, 해당 메서드는 계산 식의 행동 방식을 제어합니다. 빌더 클래스를 설명하는 또 다른 방법은 루프 및 바인딩과 같은 많은 F# 구문의 작업을 사용자 지정할 수 있다는 것입니다.

### `let!`

키워드는 `let!` 다른 계산 식에 대한 호출의 결과를 이름에 바인딩합니다.

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

`let`을 사용하여 호출을 바인딩하면 계산 식의 결과가 생성되지 않습니다. 대신 *실현되지 않은* 호출의 값을 해당 계산 식에 바인딩합니다. 결과에 `let!` 바인딩하는 데 사용합니다.

`let!`는 빌더 `Bind(x, f)` 형식의 멤버에 의해 정의됩니다.

### `do!`

키워드는 `do!` -like 형식(빌더의 멤버에 `unit`의해 정의됨)을 `Zero` 반환하는 계산 식을 호출하기 위한 것입니다.

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

[비동기 워크플로의](asynchronous-workflows.md)경우 `Async<unit>`이 유형은 입니다. 다른 계산 식의 경우 형식이 될 `CExpType<unit>`수 있습니다.

`do!`을 `Bind(x, f)` `f` 생성하는 빌더 형식의 멤버에 의해 `unit`정의됩니다.

### `yield`

키워드는 `yield` 다음과 같이 <xref:System.Collections.Generic.IEnumerable%601>사용할 수 있도록 계산 식에서 값을 반환하기 위한 것입니다.

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

대부분의 경우 호출자는 생략할 수 있습니다. 생략하는 `yield` 가장 일반적인 방법은 `->` 연산자입니다.

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

다양한 값을 생성할 수 있는 보다 복잡한 식의 경우, 그리고 조건부로 키워드를 생략하기만 하면 됩니다.

```fsharp
let weekdays includeWeekend =
    seq {
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    }
```

[C#의 yield 키워드와](../../csharp/language-reference/keywords/yield.md)마찬가지로 계산 식의 각 요소는 반복될 때 다시 산출됩니다.

`yield`는 빌더 `Yield(x)` 형식의 멤버에 의해 `x` 정의되며, 여기서 다시 출력할 항목입니다.

### `yield!`

키워드는 `yield!` 계산 식에서 값 컬렉션을 병합하기 위한 것입니다.

```fsharp
let squares =
    seq {
        for i in 1..3 -> i * i
    }

let cubes =
    seq {
        for i in 1..3 -> i * i * i
    }

let squaresAndCubes =
    seq {
        yield! squares
        yield! cubes
    }

printfn "%A" squaresAndCubes // Prints - 1; 4; 9; 1; 8; 27
```

평가할 때 호출된 계산 `yield!` 식은 해당 항목이 하나씩 다시 생성되어 결과를 병합합니다.

`yield!`는 값 `YieldFrom(x)` 의 컬렉션인 빌더 `x` 형식의 멤버에 의해 정의됩니다.

과 `yield` `yield!` 는 달리 명시적으로 지정해야 합니다. 해당 동작은 계산 식에서 암시적이지 않습니다.

### `return`

키워드는 `return` 계산 식에 해당하는 형식의 값을 래핑합니다. 을 사용하는 `yield`계산 식 외에도 계산 식을 "완료"하는 데 사용됩니다.

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return`는 빌더 `Return(x)` 형식의 멤버에 의해 `x` 정의되며, 여기서 줄 바꿈할 항목입니다.

### `return!`

키워드는 `return!` 계산 식의 값을 인식하고 계산 식에 해당하는 형식을 만드는 wraps입니다.

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!`는 빌더 `ReturnFrom(x)` 형식의 멤버에 의해 `x` 정의되며 여기서 다른 계산 식입니다.

### `match!`

키워드를 `match!` 사용하면 다른 계산 식에 대한 호출을 인라인화하고 결과에 패턴 일치를 할 수 있습니다.

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

을 사용하는 `match!`계산 식을 호출할 때 와 같은 `let!`호출의 결과를 실현합니다. 이는 결과가 [선택 사항인](options.md)계산 식을 호출할 때 종종 사용됩니다.

## <a name="built-in-computation-expressions"></a>기본 제공 계산 식

F# 코어 라이브러리는 [시퀀스 표현식,](sequences.md) [비동기 워크플로](asynchronous-workflows.md)및 쿼리 식의 세 가지 기본 제공 계산 [식을 정의합니다.](query-expressions.md)

## <a name="creating-a-new-type-of-computation-expression"></a>새 유형의 계산 식 만들기

작성기 클래스를 만들고 클래스에서 특정 특수 메서드를 정의하여 사용자 고유의 계산 식의 특성을 정의할 수 있습니다. builder 클래스는 선택적으로 다음 표에 나열된 메서드를 정의할 수 있습니다.

다음 표에서는 워크플로 빌더 클래스에서 사용할 수 있는 메서드에 대해 설명합니다.

|**메서드**|**일반적인 서명(들)**|**설명**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|계산 `let!` 식및 `do!` 계산 식에서 호출됩니다.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|계산 식을 함수로 래핑합니다.|
|`Return`|`'T -> M<'T>`|계산 `return` 식에서 호출됩니다.|
|`ReturnFrom`|`M<'T> -> M<'T>`|계산 `return!` 식에서 호출됩니다.|
|`Run`|`M<'T> -> M<'T>` 또는<br /><br />`M<'T> -> 'T`|계산 식을 실행합니다.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` 또는<br /><br />`M<unit> * M<'T> -> M<'T>`|계산 식에서 시퀀싱을 호출했습니다.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` 또는<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|계산 `for...do` 식에서 식을 호출합니다.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|계산 `try...finally` 식에서 식을 호출합니다.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|계산 `try...with` 식에서 식을 호출합니다.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|계산 `use` 식에서 바인딩을 호출했습니다.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|계산 `while...do` 식에서 식을 호출합니다.|
|`Yield`|`'T -> M<'T>`|계산 `yield` 식에서 식을 호출합니다.|
|`YieldFrom`|`M<'T> -> M<'T>`|계산 `yield!` 식에서 식을 호출합니다.|
|`Zero`|`unit -> M<'T>`|계산 식에서 `else` `if...then` 식의 빈 분기를 호출했습니다.|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|계산 식이 멤버에 `Run` 인용으로 전달되는 것을 나타냅니다. 계산의 모든 인스턴스를 인용으로 변환합니다.|

builder 클래스의 많은 메서드는 비동기 `M<'T>` 워크플로및 `Async<'T>` `Seq<'T>` 시퀀스 워크플로에 대해 결합되는 계산의 종류를 특성화하는 별도로 정의된 형식인 구문입니다. 이러한 메서드의 서명을 사용하면 한 구문에서 반환된 워크플로 개체를 다음 구문으로 전달할 수 있도록 이러한 메서드를 결합하고 서로 중첩할 수 있습니다. 컴파일러는 계산 식을 구문 분석할 때 이전 테이블의 메서드와 계산 식의 코드를 사용하여 식을 일련의 중첩 함수 호출로 변환합니다.

중첩된 식은 다음과 같은 형식입니다.

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

위의 코드에서 계산 식 `Run` `Delay` 빌더 클래스에 정의되지 않은 경우 호출및 생략됩니다. 여기서 `{| cexpr |}`"로 표시된 계산 식의 본보기는 다음 표에 설명된 번역에 의해 빌더 클래스의 메서드와 관련된 호출로 변환됩니다. 계산 식은 `{| cexpr |}` F# 식이며 `expr` `cexpr` 계산 식인 이러한 변환에 따라 재귀적으로 정의됩니다.

|식|Translation|
|----------|-----------|
|<code>{ let binding in cexpr }</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{ let! pattern = expr in cexpr }</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ do! expr in cexpr }</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{ yield expr }</code>|`builder.Yield(expr)`|
|<code>{ yield! expr }</code>|`builder.YieldFrom(expr)`|
|<code>{ return expr }</code>|`builder.Return(expr)`|
|<code>{ return! expr }</code>|`builder.ReturnFrom(expr)`|
|<code>{ use pattern = expr in cexpr }</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ use! value = expr in cexpr }</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> { cexpr }))))</code>|
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else builder.Zero()</code>|
|<code>{ if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then { cexpr0 } else { cexpr1 }</code>|
|<code>{ match expr with &#124; pattern_i -> cexpr_i }</code>|<code>match expr with &#124; pattern_i -> { cexpr_i }</code>|
|<code>{ for pattern in expr do cexpr }</code>|<code>builder.For(enumeration, (fun pattern -> { cexpr }))</code>|
|<code>{ for identifier = expr1 to expr2 do cexpr }</code>|<code>builder.For(enumeration, (fun identifier -> { cexpr }))</code>|
|<code>{ while expr do cexpr }</code>|<code>builder.While(fun () -> expr, builder.Delay({ cexpr }))</code>|
|<code>{ try cexpr with &#124; pattern_i -> expr_i }</code>|<code>builder.TryWith(builder.Delay({ cexpr }), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{ try cexpr finally expr }</code>|<code>builder.TryFinally(builder.Delay( { cexpr }), (fun () -> expr))</code>|
|<code>{ cexpr1; cexpr2 }</code>|<code>builder.Combine({ cexpr1 }, { cexpr2 })</code>|
|<code>{ other-expr; cexpr }</code>|<code>expr; { cexpr }</code>|
|<code>{ other-expr }</code>|`expr; builder.Zero()`|

이전 표에서는 `other-expr` 테이블에 나열되지 않은 식을 설명합니다. builder 클래스는 모든 메서드를 구현할 필요가 없으며 이전 테이블에 나열된 모든 번역을 지원할 수 있습니다. 구현되지 않은 구문은 해당 형식의 계산 식에서 사용할 수 없습니다. 예를 들어 계산 식에서 키워드를 `use` 지원하지 않으려면 builder 클래스에서 `Use` 정의를 생략할 수 있습니다.

다음 코드 예제에서는 한 번에 한 단계를 평가할 수 있는 일련의 단계로 계산을 캡슐화하는 계산 식을 보여 주습니다. 구별된 공용 구조체 유형은 `OkOrException`지금까지 평가된 식의 오류 상태를 인코딩합니다. 이 코드는 일부 빌더 메서드의 상용구 구현과 같이 계산 식에서 사용할 수 있는 몇 가지 일반적인 패턴을 보여 줍니다.

```fsharp
// Computations that can be run step by step
type Eventually<'T> =
    | Done of 'T
    | NotYetDone of (unit -> Eventually<'T>)

module Eventually =
    // The bind for the computations. Append 'func' to the
    // computation.
    let rec bind func expr =
        match expr with
        | Done value -> func value
        | NotYetDone work -> NotYetDone (fun () -> bind func (work()))

    // Return the final value wrapped in the Eventually type.
    let result value = Done value

    type OkOrException<'T> =
        | Ok of 'T
        | Exception of System.Exception

    // The catch for the computations. Stitch try/with throughout
    // the computation, and return the overall result as an OkOrException.
    let rec catch expr =
        match expr with
        | Done value -> result (Ok value)
        | NotYetDone work ->
            NotYetDone (fun () ->
                let res = try Ok(work()) with | exn -> Exception exn
                match res with
                | Ok cont -> catch cont // note, a tailcall
                | Exception exn -> result (Exception exn))

    // The delay operator.
    let delay func = NotYetDone (fun () -> func())

    // The stepping action for the computations.
    let step expr =
        match expr with
        | Done _ -> expr
        | NotYetDone func -> func ()

    // The rest of the operations are boilerplate.
    // The tryFinally operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryFinally expr compensation =
        catch (expr)
        |> bind (fun res ->
            compensation();
            match res with
            | Ok value -> result value
            | Exception exn -> raise exn)

    // The tryWith operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryWith exn handler =
        catch exn
        |> bind (function Ok value -> result value | Exception exn -> handler exn)

    // The whileLoop operator.
    // This is boilerplate in terms of "result" and "bind".
    let rec whileLoop pred body =
        if pred() then body |> bind (fun _ -> whileLoop pred body)
        else result ()

    // The sequential composition operator.
    // This is boilerplate in terms of "result" and "bind".
    let combine expr1 expr2 =
        expr1 |> bind (fun () -> expr2)

    // The using operator.
    let using (resource: #System.IDisposable) func =
        tryFinally (func resource) (fun () -> resource.Dispose())

    // The forLoop operator.
    // This is boilerplate in terms of "catch", "result", and "bind".
    let forLoop (collection:seq<_>) func =
        let ie = collection.GetEnumerator()
        tryFinally
            (whileLoop
                (fun () -> ie.MoveNext())
                (delay (fun () -> let value = ie.Current in func value)))
            (fun () -> ie.Dispose())

// The builder class.
type EventuallyBuilder() =
    member x.Bind(comp, func) = Eventually.bind func comp
    member x.Return(value) = Eventually.result value
    member x.ReturnFrom(value) = value
    member x.Combine(expr1, expr2) = Eventually.combine expr1 expr2
    member x.Delay(func) = Eventually.delay func
    member x.Zero() = Eventually.result ()
    member x.TryWith(expr, handler) = Eventually.tryWith expr handler
    member x.TryFinally(expr, compensation) = Eventually.tryFinally expr compensation
    member x.For(coll:seq<_>, func) = Eventually.forLoop coll func
    member x.Using(resource, expr) = Eventually.using resource expr

let eventually = new EventuallyBuilder()

let comp = eventually {
    for x in 1..2 do
        printfn " x = %d" x
    return 3 + 4 }

// Try the remaining lines in F# interactive to see how this
// computation expression works in practice.
let step x = Eventually.step x

// returns "NotYetDone <closure>"
comp |> step

// prints "x = 1"
// returns "NotYetDone <closure>"
comp |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step
```

계산 식에는 식이 반환되는 기본 형식이 있습니다. 기본 형식은 계산된 결과 또는 수행할 수 있는 지연된 계산을 나타낼 수 있거나 일부 유형의 컬렉션을 반복하는 방법을 제공할 수 있습니다. 이전 예제에서 기본 형식은 **결국**. 시퀀스 식의 경우 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>기본 형식은 . 쿼리 식의 경우 기본 <xref:System.Linq.IQueryable?displayProperty=nameWithType>형식은 입니다. 비동기 워크플로의 경우 기본 형식은 입니다. [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) 개체는 `Async` 결과를 계산하기 위해 수행할 작업을 나타냅니다. 예를 들어 계산을 실행하고 결과를 반환하기 위해 호출합니다. [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)

## <a name="custom-operations"></a>사용자 지정 작업

계산 식에서 사용자 지정 작업을 정의하고 계산 식에서 사용자 지정 연산을 연산자로 사용할 수 있습니다. 예를 들어 쿼리 식에 쿼리 연산자를 포함할 수 있습니다. 사용자 지정 작업을 정의할 때 계산 식에서 Yield 및 For 메서드를 정의해야 합니다. 사용자 지정 작업을 정의하려면 계산 식에 대한 작성기 클래스에 [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)배치한 다음 을 적용합니다. 이 특성은 문자열을 사용자 지정 작업에 사용할 이름인 인수로 사용합니다. 이 이름은 계산 식의 여비 교정기 시작 시 범위에 들어갑니다. 따라서 이 블록의 사용자 지정 작업과 이름이 같은 식별자를 사용하면 안 됩니다. 예를 들어 쿼리 식과 같은 `all` 식별자를 `last` 사용하지 마십시오.

### <a name="extending-existing-builders-with-new-custom-operations"></a>새로운 사용자 지정 작업으로 기존 빌더 확장

이미 빌더 클래스가 있는 경우 이 빌더 클래스 외부에서 사용자 지정 작업을 확장할 수 있습니다. 확장은 모듈에서 선언되어야 합니다. 네임스페이스는 형식이 정의된 동일한 파일과 동일한 네임스페이스 선언 그룹을 제외하고는 확장 멤버를 포함할 수 없습니다.

다음 예제에서는 기존 `Microsoft.FSharp.Linq.QueryBuilder` 클래스의 확장을 보여 주며 있습니다.

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>참고 항목

- [F # 언어 참조](index.md)
- [비동기 워크플로](asynchronous-workflows.md)
- [시퀀스](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [쿼리 표현식](query-expressions.md)
