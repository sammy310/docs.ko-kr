---
title: '재귀 함수: rec 키워드'
description: "' Let ' 키워드와 함께 F # ' rec ' 키워드를 사용 하 여 재귀 함수를 정의 하는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: c2374f90b4585327c6f5208a3d6bca75a23d0cbb
ms.sourcegitcommit: 7499bdb428d63ed0e19e97f54d3d576c41598659
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2020
ms.locfileid: "87455656"
---
# <a name="recursive-functions-the-rec-keyword"></a>재귀 함수: rec 키워드

`rec`키워드는 키워드와 함께 사용 되어 `let` 재귀 함수를 정의 합니다.

## <a name="syntax"></a>구문

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a>설명

재귀 함수, 자신을 호출 하는 함수는 F # 언어에서 명시적으로 식별 됩니다. 이렇게 하면 함수 범위에서 정의 되는 식별자를 사용할 수 있습니다.

다음 코드는 수학적 정의를 사용 하 여 *n*<sup>번째</sup> 피보나치 수를 계산 하는 재귀 함수를 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> 실제로 이전 샘플과 같은 코드는 이미 계산 된 대해 값을 unecessarily 하기 때문에 이상적이 지 않습니다. 이는이 문서의 뒷부분에서 설명 하는 tail recursive가 아니기 때문입니다.

메서드는 형식 내에서 암시적으로 재귀적입니다. 키워드를 추가할 필요가 없습니다 `rec` . 클래스 내의 바인딩이 암시적으로 재귀적이 지 않습니다.

## <a name="tail-recursion"></a>비상 재귀

일부 재귀 함수의 경우에는 더 많은 "순수" 정의를 [tail 재귀](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion)인 하나에 리팩터링 해야 합니다. 이렇게 하면 불필요 한 계산이 수행 되지 않습니다. 예를 들어 이전 피보나치 수 생성기는 다음과 같이 다시 작성할 수 있습니다.

```fsharp
let fib n =
    let rec loop acc1 acc2 n =
        match n with
        | 0 -> acc1
        | 1 -> acc2
        | _ ->
            loop acc2 (acc1 + acc2) (n - 1)
    loop 0 1 n
```

이는 보다 복잡 한 구현입니다. 피보나치 수를 생성 하는 것은 수학적으로는 좋지만 실제로 비효율적인 "naive" 알고리즘의 좋은 예입니다. 여러 가지 측면에서 F #의 효율성을 향상 하는 동시에 반복 해 서 정의 합니다.

* `loop`자연 스러운 F # 패턴 인 이라는 재귀적 내부 함수입니다.
* 재귀 호출에 누적 값을 전달 하는 두 개의 누적기 매개 변수
* 의 값을 검사 하 여 `n` 특정 누적을 반환 합니다.

루프를 사용 하 여이 예제가 반복적으로 작성 된 경우 코드는 특정 조건이 충족 될 때까지 숫자를 누적 하는 두 개의 다른 값과 유사 하 게 표시 됩니다.

이는 tail. 재귀를 수행 하는 이유는 재귀 호출이 호출 스택에 값을 저장할 필요가 없기 때문입니다. 계산 되는 모든 중간 값은 내부 함수에 대 한 입력을 통해 누적 됩니다. 이렇게 하면 F # 컴파일러가 루프와 같은 항목을 작성 한 것 처럼 코드를 최적화 하는 데에도 사용할 수 있습니다 `while` .

이전 예제에서 보여 주는 것 처럼 내부 및 외부 함수를 사용 하 여 항목을 재귀적으로 처리 하는 F # 코드를 작성 하는 것이 일반적입니다. 내부 함수는 tail 재귀를 사용 하는 반면 외부 함수는 호출자에 게 더 나은 인터페이스를 포함 합니다.

## <a name="mutually-recursive-functions"></a>상호 재귀 함수

경우에 따라 함수는 서로 *재귀적*으로 사용 됩니다. 즉, 한 함수가 다른 함수를 호출 하는 원을 형성 합니다. `let`키워드를 사용 하 여 함께 연결 하려면 하나의 바인딩에서 이러한 함수를 함께 정의 해야 합니다 `and` .

다음 예에서는 두 개의 상호 재귀 함수를 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>참조

- [함수](index.md)
