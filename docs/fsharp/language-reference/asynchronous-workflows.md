---
title: 비동기 워크플로
description: '다른 작업의 실행을 차단 하지 않고 실행 되는 비동기적 계산을 수행 하기 위한 F # 프로그래밍 언어 지원에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: ac727fc630f13db01da964131ab39dc242a12cd1
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557713"
---
# <a name="asynchronous-workflows"></a>비동기 워크플로

이 문서에서는 다른 작업의 실행을 차단 하지 않고 비동기적으로 계산을 수행 하기 위한 F #의 지원을 설명 합니다. 예를 들어 비동기 계산은 응용 프로그램에서 다른 작업을 수행할 때 사용자에 게 응답성이 유지 되는 Ui가 있는 응용 프로그램을 작성 하는 데 사용할 수 있습니다.

## <a name="syntax"></a>구문

```fsharp
async { expression }
```

## <a name="remarks"></a>설명

이전 구문에서로 표시 되는 계산은 `expression` 비동기 절전 모드 작업, i/o 및 기타 비동기 작업을 수행할 때 현재 계산 스레드를 차단 하지 않고 비동기적으로 실행 되도록 설정 됩니다. 비동기 계산은 종종 현재 스레드에서 실행을 계속 하는 동안 백그라운드 스레드에서 시작 됩니다. 식의 형식은입니다 `Async<'T>` `'T` . 여기서는 키워드가 사용 될 때 식에서 반환 되는 형식입니다 `return` . 이러한 식의 코드는 *비동기*블록 또는 비동기 *블록*이라고 합니다.

프로그래밍에는 여러 가지 방법이 있으며, [`Async`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html) 클래스는 여러 시나리오를 지 원하는 메서드를 제공 합니다. 일반적인 방법은 비동기 방식으로 `Async` 실행 하려는 계산 또는 계산을 나타내는 개체를 만든 다음 트리거 함수 중 하나를 사용 하 여 이러한 계산을 시작 하는 것입니다. 여러 트리거 함수는 비동기 계산을 실행 하는 다양 한 방법을 제공 하 고, 사용 하는 함수는 현재 스레드, 백그라운드 스레드 또는 .NET Framework 작업 개체 중 무엇을 사용할지 여부와 계산이 완료 될 때 실행 되어야 하는 연속 함수가 있는지 여부에 따라 달라 집니다. 예를 들어 현재 스레드에서 비동기 계산을 시작 하려면를 사용할 수 있습니다 [`Async.StartImmediate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#StartImmediate) . UI 스레드에서 비동기 계산을 시작할 때 키 입력 및 마우스 작업과 같은 사용자 동작을 처리 하는 주 이벤트 루프를 차단 하지 않으므로 응용 프로그램의 응답성이 향상 됩니다.

## <a name="asynchronous-binding-by-using-let"></a>Let을 사용 하 여 비동기 바인딩

비동기 워크플로에서 일부 식과 작업은 동기적으로 수행 되며, 일부는 비동기 결과를 반환 하도록 디자인 된 계산 보다 깁니다. 일반 바인딩 대신 비동기 방식으로 메서드를 호출 하는 경우에는를 `let` 사용 `let!` 합니다. 의 효과는 `let!` 계산이 수행 되는 동안 다른 계산 또는 스레드에서 실행을 계속할 수 있도록 하는 것입니다. 바인딩의 오른쪽이 반환 된 후 `let!` 비동기 워크플로의 나머지 부분이 실행을 다시 시작 합니다.

다음 코드에서는와의 차이점을 보여 줍니다 `let` `let!` . 를 사용 하는 코드 줄은 나중에 또는와 같이 `let` 를 사용 하 여 나중에 실행할 수 있는 개체로 비동기 계산을 `Async.StartImmediate` 만듭니다 [`Async.RunSynchronously`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#RunSynchronously) . 에서 사용 하는 코드 줄은 `let!` 계산을 시작 하 고, 결과를 사용할 수 있을 때까지 스레드를 일시 중단 하 여 지점 실행이 계속 됩니다.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

외에도를 `let!` 사용 하 여 `use!` 비동기 바인딩을 수행할 수 있습니다. 과 간의 차이는와의 차이와 `let!` `use!` 동일 합니다 `let` `use` . 의 경우 `use!` 개체는 현재 범위를 닫을 때 삭제 됩니다. F # 언어의 현재 릴리스에서는 `use!` 가 인 경우에도 값을 null로 초기화 하는 것을 허용 하지 않습니다 `use` .

## <a name="asynchronous-primitives"></a>비동기 기본 형식

단일 비동기 작업을 수행 하 고 결과를 반환 하는 메서드를 *비동기 기본 형식*이라고 하며,이 메서드는에서 사용할 수 있도록 특별히 설계 되었습니다 `let!` . F # 핵심 라이브러리에는 몇 가지 비동기 기본 형식이 정의 되어 있습니다. 웹 응용 프로그램에 대 한 이러한 두 메서드는 및 모듈에서 정의 됩니다. [`FSharp.Control.WebExtensions`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html) [`WebRequest.AsyncGetResponse`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncGetResponse) [`WebClient.AsyncDownloadString`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncDownloadString) 두 기본 형식은 URL을 지정 하 여 웹 페이지에서 데이터를 다운로드 합니다. `AsyncGetResponse` 개체를 생성 하 `System.Net.WebResponse` 고 `AsyncDownloadString` 웹 페이지에 대 한 HTML을 나타내는 문자열을 생성 합니다.

비동기 i/o 작업에 대 한 여러 가지 기본 형식이 모듈에 포함 됩니다 [`FSharp.Control.CommonExtensions`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html) . 클래스의 이러한 확장 메서드 `System.IO.Stream` 는 [`Stream.AsyncRead`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html#AsyncRead) 및 [`Stream.AsyncWrite`](hhttps://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html#AsyncWrite) 입니다.

전체 본문이 비동기 블록으로 묶여 있는 함수를 정의 하 여 고유한 비동기 기본 형식을 작성할 수도 있습니다.

F # 비동기 프로그래밍 모델을 사용 하 여 다른 비동기 모델에 대해 디자인 된 .NET Framework에서 비동기 메서드를 사용 하려면 F # 개체를 반환 하는 함수를 만듭니다 `Async` . F # 라이브러리에는이 작업을 쉽게 수행할 수 있도록 하는 함수가 있습니다.

비동기 워크플로를 사용 하는 한 가지 예는 여기에 포함 되어 있습니다. [비동기 클래스](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html)의 메서드에 대 한 설명서에는 다른 여러 가지가 있습니다.

이 예제에서는 비동기 워크플로를 사용 하 여 계산을 병렬로 수행 하는 방법을 보여 줍니다.

다음 코드 예제에서 함수는 `fetchAsync` 웹 요청에서 반환 된 HTML 텍스트를 가져옵니다. 함수에는 `fetchAsync` 비동기 코드 블록이 포함 되어 있습니다. 비동기 기본 형식의 결과에 대 한 바인딩이 수행 되는 경우이 경우 [`AsyncDownloadString`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncDownloadString) `let!` 가 대신 사용 됩니다 `let` .

함수를 사용 하 여 [`Async.RunSynchronously`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#RunSynchronously) 비동기 작업을 실행 하 고 그 결과를 기다립니다. 예를 들어 함수와 함께 함수를 사용 하 여 여러 비동기 작업을 병렬로 실행할 수 있습니다 [`Async.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#Parallel) `Async.RunSynchronously` . `Async.Parallel`함수는 개체 목록을 가져오고 `Async` , 각 작업 개체에 대해 병렬로 실행 되도록 코드를 설정 하 `Async` 고, `Async` 병렬 계산을 나타내는 개체를 반환 합니다. 단일 작업의 경우와 마찬가지로 `Async.RunSynchronously` 를 호출 하 여 실행을 시작 합니다.

`runAll`함수는 세 개의 비동기 워크플로를 병렬로 시작 하 고 모든 작업이 완료 될 때까지 대기 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
- [계산 식](computation-expressions.md)
- [컨트롤. Async 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
