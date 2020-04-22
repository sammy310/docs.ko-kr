---
title: 비동기 프로그래밍
description: F#이 핵심 기능적 프로그래밍 개념에서 파생된 언어 수준 프로그래밍 모델을 기반으로 비동기에 대한 깨끗한 지원을 제공하는 방법을 알아봅니다.
ms.date: 12/17/2018
ms.openlocfilehash: 0a7d400c9778e30d6b25798239f12b7b2b0e3d82
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021525"
---
# <a name="async-programming-in-f"></a>F의 비동기 프로그래밍\#

비동기 프로그래밍은 다양한 이유로 최신 응용 프로그램에 필수적인 메커니즘입니다. 대부분의 개발자가 발생할 수 있는 두 가지 기본 사용 사례가 있습니다.

- 요청 처리가 해당 프로세스 외부의 시스템 또는 서비스의 입력을 기다리는 동안 점유된 시스템 리소스를 최소화하면서 상당수의 동시 수신 요청을 처리할 수 있는 서버 프로세스를 제공합니다.
- 백그라운드 작업을 동시에 진행하는 동안 반응형 UI 또는 기본 스레드 유지 관리

백그라운드 작업에는 여러 스레드의 사용이 포함되는 경우가 많지만 비동기 및 다중 스레딩의 개념을 별도로 고려하는 것이 중요합니다. 사실, 그들은 별개의 관심사이며, 하나는 다른 것을 의미하지 는 않습니다. 이 문서에서는 별도의 개념을 자세히 설명합니다.

## <a name="asynchrony-defined"></a>정의된 비동기

이전 점 - 비동기는 여러 스레드의 사용률과 독립적입니다 - 조금 더 설명 할 가치가있다. 때로는 서로 관련이 있지만 엄격하게 서로 독립적 인 세 가지 개념이 있습니다.

- 동시성; 겹치는 기간에서 여러 계산이 실행되는 경우
- 병렬 처리; 여러 계산 또는 단일 계산의 여러 부분이 정확히 동시에 실행되는 경우
- 비동기; 하나 이상의 계산이 주 프로그램 흐름과 별도로 실행될 수 있는 경우

세 가지 모두 직교 개념이지만, 특히 함께 사용할 때 쉽게 수축 할 수 있습니다. 예를 들어 여러 비동기 계산을 병렬로 실행해야 할 수 있습니다. 이 관계는 병렬 처리 또는 비동기가 서로를 의미하는 것은 아닙니다.

"비동기"라는 단어의 어장을 고려하면 다음과 같은 두 가지 조각이 있습니다.

- "a", "하지"를 의미합니다.
- "동기", "동시에"를 의미합니다.

이 두 용어를 함께 사용하면 "비동기"가 "동시에 아님"을 의미합니다. 정말 간단하죠. 이 정의에는 동시성 또는 병렬 처리의 의미가 없습니다. 이것은 실제로도 마찬가지입니다.

실질적으로 F#의 비동기 계산은 주 프로그램 흐름과 독립적으로 실행되도록 예약됩니다. 이 독립적인 실행은 동시성 또는 병렬성을 의미하지 않으며 백그라운드에서 항상 계산이 발생한다는 의미도 아닙니다. 실제로 비동기 계산은 계산의 특성과 계산이 실행되는 환경에 따라 동기적으로 실행될 수도 있습니다.

비동기 계산은 주 프로그램 흐름과 독립적이라는 것이 주요 테이크 아웃입니다. 비동기 계산이 실행되는 시기 또는 방법에 대한 보장은 거의 없지만 이를 오케스트레이션하고 예약하는 몇 가지 방법이 있습니다. 이 문서의 나머지 부분에서는 F# 비동기에 대한 핵심 개념과 F#에 기본 제공된 형식, 함수 및 식을 사용하는 방법을 살펴봅습니다.

## <a name="core-concepts"></a>핵심 개념

F#에서 비동기 프로그래밍은 다음 세 가지 핵심 개념을 중심으로 합니다.

- 컴포셔블 비동기 계산을 나타내는 `Async<'T>` 형식입니다.
- 비동기 작업을 예약하고 비동기 계산을 작성하고 비동기 결과를 변환할 수 있는 `Async` 모듈 함수입니다.
- `async { }` [비동기](../../language-reference/computation-expressions.md)계산을 빌드하고 제어하기 위한 편리한 구문을 제공하는 계산 식입니다.

다음 예제에서는 다음 세 가지 개념을 볼 수 있습니다.

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

이 예제에서 `printTotalFileBytes` 함수는 형식입니다. `string -> Async<unit>` 함수를 호출해도 실제로 비동기 계산이 실행되지 않습니다. 대신 비동기적으로 `Async<unit>` 실행하는 작업의 *사양역할을* 하는 을 반환합니다. 본문을 `Async.AwaitTask` 호출하여 결과를 적절한 <xref:System.IO.File.ReadAllBytesAsync%2A> 유형으로 변환합니다.

또 다른 중요한 줄은 `Async.RunSynchronously`에 대한 호출입니다. 실제로 F# 비동기 계산을 실행하려는 경우 호출해야 하는 비동기 모듈 시작 함수 중 하나입니다.

이는 C#/Visual Basic 프로그래밍 스타일과의 `async` 근본적인 차이점입니다. F#에서 비동기 계산은 **콜드 작업으로**생각할 수 있습니다. 실제로 실행하기 위해 명시적으로 시작해야 합니다. C# 또는 Visual Basic보다 비동기 작업을 훨씬 쉽게 결합하고 시퀀스할 수 있으므로 몇 가지 장점이 있습니다.

## <a name="combine-asynchronous-computations"></a>비동기 계산 결합

다음은 계산을 결합하여 이전 예제를 기반으로 하는 예제입니다.

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

보시다시피 이 `main` 함수에는 호출이 꽤 많이 있습니다. 개념적으로 다음을 수행합니다.

1. 명령줄 인수를 을 통해 `Async<unit>` `Array.map`계산으로 변환합니다.
2. 계산이 `Async<'T[]>` 실행될 때 `printTotalFileBytes` 병렬로 계산을 예약하고 실행하는 사용자를 만듭니다.
3. 병렬 `Async<unit>` 계산을 실행하고 결과를 무시하는 을 만듭니다.
4. 마지막 계산을 `Async.RunSynchronously` 명시적으로 실행하고 완료될 때까지 차단합니다.

이 프로그램이 실행되면 각 명령줄 인수에 대해 병렬로 `printTotalFileBytes` 실행됩니다. 비동기 계산은 프로그램 흐름과 독립적으로 실행되므로 정보를 인쇄하고 실행을 완료하는 순서는 없습니다. 계산은 병렬로 예약되지만 실행 순서는 보장되지 않습니다.

## <a name="sequence-asynchronous-computations"></a>시퀀스 비동기 계산

이미 `Async<'T>` 실행 중인 작업이 아니라 작업 사양이므로 보다 복잡한 변환을 쉽게 수행할 수 있습니다. 다음은 비동기 계산 집합을 시퀀싱하여 차례로 실행하도록 하는 예제입니다.

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

이렇게 하면 `printTotalFileBytes` 병렬로 예약하는 대신 `argv` 요소의 순서대로 실행하도록 예약됩니다. 마지막 계산이 실행을 완료할 때까지 다음 항목이 예약되지 않으므로 계산이 순서대로 정렬되어 실행에 겹치지 않습니다.

## <a name="important-async-module-functions"></a>중요한 비동기 모듈 기능

F#에서 비동기 코드를 작성할 때 일반적으로 계산 일정을 처리하는 프레임워크와 상호 작용합니다. 그러나 항상 그런 것은 아니므로 비동기 작업을 예약하기 위해 다양한 시작 함수를 배우는 것이 좋습니다.

F# 비동기 계산은 이미 실행 중인 작업의 표현이 아니라 작업 _사양이므로_ 시작 함수로 명시적으로 시작해야 합니다. 다른 컨텍스트에서 유용한 많은 [비동기 시작 함수가](https://msdn.microsoft.com/library/ee370232.aspx) 있습니다. 다음 섹션에서는 보다 일반적인 시작 함수 중 일부에 대해 설명합니다.

### <a name="asyncstartchild"></a>비동기.시작자

비동기 계산 내에서 자식 계산을 시작합니다. 이렇게 하면 여러 비동기 계산을 동시에 실행할 수 있습니다. 자식 계산은 부모 계산과 취소 토큰을 공유합니다. 상위 계산이 취소되면 자식 계산도 취소됩니다.

서명:

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

사용 시기:

- 한 번에 하나씩이 아니라 동시에 여러 비동기 계산을 실행하려는 경우 병렬로 예약되어 있지 않습니다.
- 하위 계산의 수명을 상위 계산의 수명과 연결하려는 경우

주의해야 할 사항:

- 여러 계산을 `Async.StartChild` 병렬로 예약하는 것과 는 다중 계산을 시작합니다. 계산을 병렬로 예약하려면 을 `Async.Parallel`사용합니다.
- 상위 계산을 취소하면 시작된 모든 자식 계산이 취소됩니다.

### <a name="asyncstartimmediate"></a>비동기.즉시 시작

현재 운영 체제 스레드에서 즉시 시작하여 비동기 계산을 실행합니다. 이 기능은 계산 중에 호출 스레드에서 무언가를 업데이트해야 하는 경우에 유용합니다. 예를 들어 비동기 계산에서 UI(예: 진행률 표시줄 업데이트)를 `Async.StartImmediate` 업데이트해야 하는 경우 사용해야 합니다.

서명:

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

사용 시기:

- 비동기 계산 중간에 호출 스레드에서 무언가를 업데이트해야 하는 경우

주의해야 할 사항:

- 비동기 계산의 코드는 예약될 스레드가 무엇이든에서 실행됩니다. 이 스레드는 UI 스레드와 같은 어떤 식으로든 중요 한 경우 문제가 될 수 있습니다. 이러한 경우 `Async.StartImmediate` 사용하기에 부적절할 수 있습니다.

### <a name="asyncstartastask"></a>비동기.시작 작업

스레드 풀에서 계산을 실행합니다. 계산이 <xref:System.Threading.Tasks.Task%601> 종료되면 해당 상태에서 완료될 a를 반환합니다(결과가 생성되거나 예외가 발생하거나 취소됨). 취소 토큰이 제공되지 않으면 기본 취소 토큰이 사용됩니다.

서명:

```fsharp
computation: Async<'T> * taskCreationOptions: ?TaskCreationOptions * cancellationToken: ?CancellationToken -> Task<'T>
```

사용 시기:

- a가 비동기 계산의 결과를 나타낼 것으로 <xref:System.Threading.Tasks.Task%601> 예상되는 .NET API를 호출해야 하는 경우

주의해야 할 사항:

- 이 호출은 추가 `Task` 개체를 할당하며, 자주 사용되는 경우 오버헤드가 증가할 수 있습니다.

### <a name="asyncparallel"></a>비동기.병렬

비동기 계산 시퀀스를 병렬로 실행하도록 예약합니다. 매개 `maxDegreesOfParallelism` 변수를 지정하여 병렬 처리 정도를 선택적으로 조정/조절할 수 있습니다.

서명:

```fsharp
computations: seq<Async<'T>> * ?maxDegreesOfParallelism: int -> Async<'T[]>
```

사용하는 시기:

- 계산 집합을 동시에 실행해야 하고 실행 순서에 의존하지 않는 경우.
- 모두 완료될 때까지 병렬로 예약된 계산의 결과가 필요하지 않은 경우

주의해야 할 사항:

- 모든 계산이 완료된 후에만 결과 값 배열에 액세스할 수 있습니다.
- 계산은 예약이 끝날 때마다 실행됩니다. 이 동작은 실행 순서에 의존할 수 없음을 의미합니다.

### <a name="asyncsequential"></a>비동기.순차적

전달되는 순서대로 실행되도록 비동기 계산 시퀀스를 예약합니다. 첫 번째 계산은 다음 계산을 실행한 다음 다음 계산됩니다. 계산은 병렬로 실행되지 않습니다.

서명:

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

사용하는 시기:

- 여러 계산을 순서대로 실행해야 하는 경우

주의해야 할 사항:

- 모든 계산이 완료된 후에만 결과 값 배열에 액세스할 수 있습니다.
- 계산은 이 함수에 전달되는 순서대로 실행되며, 이는 결과가 반환되기 전에 더 많은 시간이 경과한다는 것을 의미할 수 있습니다.

### <a name="asyncawaittask"></a>애싱크.대기 작업

주어진 <xref:System.Threading.Tasks.Task%601> 계산이 완료될 때까지 대기하고 결과를`Async<'T>`

서명:

```fsharp
task: Task<'T> -> Async<'T>
```

사용 시기:

- F# 비동기 계산 내에서 를 <xref:System.Threading.Tasks.Task%601> 반환 하는 .NET API를 사용 하는 경우.

주의해야 할 사항:

- 예외는 작업 <xref:System.AggregateException> 병렬 라이브러리의 규칙에 따라 래핑되며 이 동작은 F# 비동기가 일반적으로 예외를 표시하는 방법과 다릅니다.

### <a name="asynccatch"></a>비동기.Catch

을 반환하는 지정된 `Async<'T>`을 실행하는 비동기 계산을 `Async<Choice<'T, exn>>`만듭니다. 지정된 `Async<'T>` 값이 성공적으로 완료되면 a가 `Choice1Of2` 결과 값과 함께 반환됩니다. 완료되기 전에 예외가 throw되면 발생한 `Choice2of2` 예외와 함께 반환됩니다. 자체가 많은 계산으로 구성된 비동기 계산에 사용되고 이러한 계산 중 하나가 예외를 throw하면 포괄 계산이 완전히 중지됩니다.

서명:

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

사용 시기:

- 예외와 함께 실패할 수 있는 비동기 작업을 수행 하 고 호출자에서 해당 예외를 처리 하려는 경우.

주의해야 할 사항:

- 결합된 또는 시퀀싱된 비동기 계산을 사용하는 경우 "내부" 계산 중 하나가 예외를 throw하면 포괄 계산이 완전히 중지됩니다.

### <a name="asyncignore"></a>비동기.무시

지정된 계산을 실행하고 결과를 무시하는 비동기 계산을 만듭니다.

서명:

```fsharp
computation: Async<'T> -> Async<unit>
```

사용 시기:

- 결과가 필요하지 않은 비동기 계산이 있는 경우 이는 비동기 코드의 `ignore` 코드와 유사합니다.

주의해야 할 사항:

- 사용하려는 경우 `Async.Ignore` 또는 필요한 `Async<unit>` `Async.Start` 다른 함수를 사용하려면 결과를 삭제해도 됩니다. 형식 시그니처에 맞추기 위해 결과를 삭제하지 마십시오.

### <a name="asyncrunsynchronously"></a>비동기.실행 동기

비동기 계산을 실행 하 고 호출 스레드에서 해당 결과를 기다립니다. 이 호출이 차단중입니다.

서명:

```fsharp
computation: Async<'T> * timeout: ?int * cancellationToken: ?CancellationToken -> 'T
```

사용하는 시기:

- 필요한 경우 실행 항목의 진입점에서 응용 프로그램에서 한 번만 사용하십시오.
- 성능에 신경 쓰지 않고 다른 비동기 작업 집합을 한 번에 실행하려는 경우

주의해야 할 사항:

- 호출은 `Async.RunSynchronously` 실행이 완료될 때까지 호출 스레드를 차단합니다.

### <a name="asyncstart"></a>비동기.시작

을 반환하는 `unit`스레드 풀에서 비동기 계산을 시작합니다. 그 결과를 기다리지 않습니다. 중첩 된 계산은 `Async.Start` 그들을 호출 하는 부모 계산 독립적으로 시작 됩니다. 수명은 상위 계산에 연결되지 않습니다. 상위 계산이 취소되면 하위 계산이 취소되지 않습니다.

서명:

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

다음과 같은 경우에만 사용하십시오.

- 결과를 생성하지 않거나 하나를 처리해야 하는 비동기 계산이 있습니다.
- 비동기 계산이 완료되는 시기를 알 필요가 없습니다.
- 비동기 계산이 실행되는 스레드는 신경 쓰지 않습니다.
- 작업으로 인한 예외를 인식하거나 보고할 필요가 없습니다.

주의해야 할 사항:

- 시작된 계산으로 인해 발생하는 `Async.Start` 예외는 호출자에게 전파되지 않습니다. 호출 스택이 완전히 해제됩니다.
- 호출로 `Async.Start` 시작된 모든 `printfn`작업(예: 호출)은 프로그램 실행의 주 스레드에 영향을 주지 않습니다.

## <a name="interoperate-with-net"></a>.NET과 상호 운용

[비동기/await-style](../../../standard/async.md)프로그래밍을 사용하는 .NET 라이브러리 또는 C# 코드베이스로 작업할 수 있습니다. C# 및 대부분의 .NET 라이브러리는 <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task> 이 형식과 형식을 `Async<'T>`핵심 추상화로 사용하기 때문에 이 두 방법 사이의 경계를 비동기로 교차해야 합니다.

### <a name="how-to-work-with-net-async-and-taskt"></a>.NET 비동기 및 작업 방법`Task<T>`

.NET 비동기 라이브러리 및 사용(즉, 반환 값이 있는 비동기 계산)을 사용하는 <xref:System.Threading.Tasks.Task%601> 코드베이스로 작업하는 것은 간단하며 F#에 대한 기본 제공 지원이 있습니다.

이 함수를 `Async.AwaitTask` 사용하여 .NET 비동기 계산을 기다릴 수 있습니다.

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

이 함수를 `Async.StartAsTask` 사용하여 .NET 호출자에게 비동기 계산을 전달할 수 있습니다.

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a>.NET 비동기 및 작업 방법`Task`

값을 반환하지 않는 <xref:System.Threading.Tasks.Task> .NET 비동기 계산을 사용하는 API를 사용하여 작업하려면 다음을 `Async<'T>` 다음으로 <xref:System.Threading.Tasks.Task>변환하는 추가 함수를 추가해야 할 수 있습니다.

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

입력으로 `Async.AwaitTask` 받아들이는 이미 있습니다. <xref:System.Threading.Tasks.Task> 이 함수와 이전에 `startTaskFromAsyncUnit` 정의된 함수를 사용하면 <xref:System.Threading.Tasks.Task> F# 비동기 계산에서 형식을 시작하고 기다릴 수 있습니다.

## <a name="relationship-to-multi-threading"></a>다중 스레딩과의 관계

이 문서 전체에서 스레딩이 언급되어 있지만 기억해야 할 두 가지 중요한 사항이 있습니다.

1. 현재 스레드에서 명시적으로 시작하지 않는 한 비동기 계산과 스레드 사이에는 연관성이 없습니다.
1. F#의 비동기 프로그래밍은 멀티 스레딩에 대한 추상화가 아닙니다.

예를 들어 계산은 작업의 특성에 따라 실제로 호출자의 스레드에서 실행될 수 있습니다. 계산은 스레드 간에 "점프"하여 "대기 중"(예: 네트워크 호출이 전송 중일 때) 기간 사이에 유용한 작업을 수행하는 데 약간의 시간 동안 스레드를 대여할 수 있습니다.

F#은 현재 스레드에서 비동기 계산을 시작하는 몇 가지 기능을 제공하지만(또는 현재 스레드에 명시적으로 적용되지 않음) 일반적으로 비동기는 특정 스레딩 전략과 연결되지 않습니다.

## <a name="see-also"></a>참조

- [F# 비동기 프로그래밍 모델](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [Jet.com의 F# 비동기 가이드](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [재미와 이익의 비동기 프로그래밍 가이드에 대한 F #](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [C # 및 F #의 비동기 : C의 비동기 gotchas #](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
