---
title: 일치 식
description: 에 대해 알아봅니다 하는 방법을 F# 일치 식 패턴 집합을 사용 하 여 식의 비교를 기반으로 하는 분기 제어를 제공 합니다.
ms.date: 04/19/2018
ms.openlocfilehash: 8972cc012d2746cb720eeed1acee403948941425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903957"
---
# <a name="match-expressions"></a>일치 식

`match` 식 패턴 집합을 사용 하 여 식의 비교를 기반으로 하는 분기 제어를 제공 합니다.

## <a name="syntax"></a>구문

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a>설명

패턴 일치 식을 패턴 집합을 사용 하 여 테스트 식의 비교를 기반으로 복잡 한 분기를 허용 합니다. `match` 식을 *테스트 식* 차례 대로 및 해당 일치 하는 항목이 발견 되 면 각 패턴을 사용 하 여 비교 됩니다 *결과 식* 평가 되 고 결과 값은 일치 식의 값으로 반환 합니다.

이전 구문에서 표시 된 함수를 일치 하는 패턴에는 패턴 일치는 즉시 인수에 람다 식입니다. 이전 구문에서 표시 된 함수를 일치 하는 패턴은 다음과 같습니다.

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

람다 식에 대 한 자세한 내용은 참조 하세요. [람다 식: 합니다 `fun` 키워드](functions/lambda-expressions-the-fun-keyword.md)합니다.

패턴의 전체 집합 입력 변수의 가능한 모든 일치 항목을 포함 해야 합니다. 와일드 카드 패턴을 사용 하는 경우가 많습니다 (`_`) 이전에 일치 하지 않는 모든 입력된 값과 일치 하는 마지막 패턴으로 합니다.

다음 코드에서는 몇 가지는 `match` 식이 사용 됩니다. 참조 및 사용할 수 있는 모든 패턴의 예제를 참조 하세요 [패턴 일치](pattern-matching.md)합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>패턴에 가드

사용할 수는 `when` 변수 패턴과 일치 하도록 충족 해야 하는 추가 조건을 지정 하려면 절. 이와 같은 절 라고 하는 *보호*합니다. 식은 다음의 `when` 일치 하는 해당 가드와 관련 된 패턴을 하려고 하지 않는 한 키워드는 평가 되지 않습니다.

다음 예제에서는 변수 패턴에 대 한 숫자 범위를 지정 하는 가드를 사용을 하는 방법을 보여 줍니다. 부울 연산자를 사용 하 여 여러 조건이 결합 되는 참고 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

패턴의 리터럴이 아닌 값을 사용할 수 없으므로 사용 해야 합니다는 `when` 절 값에 대해 입력의 일부 비교 해야 하는 경우. 이 다음 코드에 표시 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

공용 구조체 패턴을 가드에서 검사 하는 가드를 적용 **모든** 뿐 아니라 개가 되는 패턴입니다. 예를 들어 다음 코드를 가드 `when a > 12` 모두에 적용 됩니다 `A a` 고 `B a`:

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [활성 패턴](active-patterns.md)
- [패턴 일치](pattern-matching.md)