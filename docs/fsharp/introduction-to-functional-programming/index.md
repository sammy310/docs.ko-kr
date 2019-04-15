---
title: F# 함수형 프로그래밍 소개
description: F# 함수형 프로그래밍의 기본 사항에 알아봅니다.
ms.date: 10/29/2018
ms.openlocfilehash: d4a9bb0cd826b41aca96e12e2bcb5aab80c18eb4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2018
ms.locfileid: "25724480"
---
# <a name="introduction-to-functional-programming-in-f"></a>F# 함수형 프로그래밍 소개 #

함수형 프로그래밍은 함수와 변경할 수 없는 데이터의 사용을 강조하는 프로그래밍 스타일입니다. 형식화된 함수형 프로그래밍은 함수형 프로그래밍이 F#과 같은 정적 형식과 결합 된 경우 입니다. 일반적으로 함수형 프로그래밍에서는 다음과 같은 개념이 강조 됩니다.

* 사용하는 기본 구문으로서의 함수
* 명령문 대신 표현식
* 변수에 대한 변경할 수 없는 값
* 명령형 프로그래밍에 대한 선언적 프로그래밍

이 시리즈 전체에서 F#을 사용한 함수 프로그래밍의 개념과 패턴을 살펴 보겠습니다. 따라서 진행하다 보면 F#도 배우게 됩니다.

## <a name="terminology"></a>용어

다른 프로그래밍 패러다임과 마찬가지로 함수형 프로그래밍을 배우기 위해 필요한 어휘가 있습니다. 다음은 흔히 볼수 있는 몇 가지 일반적인 용어입니다.

* **함수** -함수는 입력이 주어지면 출력을 생성하는 구문입니다. 어떤 항목을 하나의 집합에서 다른 집합으로 _맵핑_ 하는 형식입니다. 이러한 형식은 다양한 방식, 특히 데이터 컬렉션에 대해 작동하는 함수를 사용할때 구체화 됩니다. 이는 함수 프로그래밍에서 가장 기본적이고 중요한 개념입니다.
* **표현식** -표현식은 값을 생성하는 코드의 구문입니다. F#에서는 이 값을 바인딩하거나 명시적으로 무시해야 합니다. 표현식은 간한히 함수 호출로 대체할 수 있습니다.
* **순도** -순도는 함수의 속성으로, 동일한 인수에 대해 반환 값이 항상 동일하고 해당 평가에는 부작용이 없어야 합니다. 순수 함수는 전적으로 인수에 따라 달라 집니다.
* **참조 투명성** -참조 투명성은 표현식의 속성으로, 프로그램의 동작에 영향을 주지 않고 해당 출력을 사용하여 대체할 수 있습니다.
* **불변성** -불변성은 값을 변경할 수 없음을 의미합니다. 이는 변경할 수 있는 변수와 대조 됩니다.

## <a name="examples"></a>예제

다음 예제에서는 이러한 핵심 개념을 보여 줍니다.

### <a name="functions"></a>함수

함수형 프로그래밍에서 가장 일반적이고 기본적인 구조의 함수입니다. 다음은 정수 1을 추가 하는 간단한 함수 입니다.

```fsharp
let addOne x = x + 1
```

형식 시그니처는 다음과 같습니다.

```fsharp
val addOne: x:int -> int
```

이 시그니처는 "`addOne`은 `int`라는 `x`를 받아서 `int`를 생성합니다"라고 읽을 수 있습니다. `addOne`은 어떤 값을 정수 집합에서 정수 집합으로 _매핑_ 하는 형식입니다. `->` 토큰이 이 매핑을 나타냅니다. F#에서는 일반적으로 함수 시그니처를 보고 어떤 작업을 수행하는지 알 수 있습니다.

따라서 서명이 중요 한 이유는? 형식화 된 함수형 프로그래밍에서는 함수의 구현은 종종 작은 실제 형식 시그니처 보다 중요 한! 팩트는 `addOne` 는 정수 값 1은 런타임 시 흥미로운 추가 수락 하 고 반환 하는 프로그램을 생성할 때 있지만 `int` 어떤 알립니다 실제로 사용법에이 함수는 합니다. 또한 올바르게 (관련 하 여 해당 형식 시그니처)이이 함수를 사용 하면 문제 진단 가능의 본문 내 에서만 `addOne` 함수입니다. 형식화 된 함수형 프로그래밍 원동력이입니다.

### <a name="expressions"></a>식

식에는 값으로 계산 되는 구문입니다. 작업을 수행 하는 문 달리 식 값을 제공 하는 작업을 수행 하는 생각할 수 있습니다. 식 문 함수형 프로그래밍에서을 위해 거의 항상 사용 됩니다.

이전 함수를 살펴보세요 `addOne`합니다. 본문 `addOne` 식:

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

결과 형식을 정의 하는이 식의 결과 `addOne` 함수입니다. 이 함수를 구성 하는 식과 같은 다른 형식으로 변경 될 수 예를 들어, 한 `string`:

```fsharp
let addOne x = x.ToString() + "1"
```

함수의 서명이 되었습니다.

```fsharp
val addOne: x:'a -> string
```

모든 형식에 이후 F# 있을 수 있습니다 `ToString()` 호출의 형식 `x` 제네릭 만들어졌습니다 (호출 [자동 일반화](../language-reference/generics/automatic-generalization.md)), 고의 결과 형식이 `string`.

식은 함수의 본문에만 않습니다. 다른 곳에서 사용할 값을 생성 하는 식을 사용할 수 있습니다. 하나는 일반적인 `if`:

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result
```

합니다 `if` 이라고 하는 값을 생성 하는 식 `result`합니다. 생략할 수 있습니다 `result` 완전히 수행 합니다 `if` 식 본문의는 `addOneIfOdd` 함수입니다. 식에 대 한 기억해 야 할 주요 사항은 이러한 값을 생성 하는 경우

특수 형식이 `unit`를 반환 하는 것이 없을 때 사용 되는 합니다. 예를 들어이 간단한 함수를 살펴보세요.

```fsharp
let printString (str: string) =
    printfn "String is: %s" s
```

시그니처는 다음과 같습니다.

```fsharp
val printString: str:string -> unit
```

`unit` 실제 값을 반환 하는 형식을 나타냅니다. 해야 하는 루틴을 해야 하는 경우에 유용 "수행" 작동 불구 하 고 해당 작업의 결과로 반환할 값입니다.

이 명령형 프로그래밍에 대조에서 위치에 해당 하는 `if` 구문은 문 및 값을 생성 합니다. 주로 사용 하 여 변수를 변경 합니다. 예를 들어, C#에 다음과 같은 코드를 작성할 수 있습니다.

```csharp
bool IsOdd(int x) => x % 2 != 0;

int AddOneIfOdd(int input)
{
    var result = input;

    if (IsOdd(input))
    {
        result = input + 1;
    }

    return result;
}
```

주목할 만한 가치가 C# 다른 C 스타일 언어를 지원할 합니다 [삼진 식은](../../csharp/language-reference/operators/conditional-operator.md), 조건부 식 기반 프로그래밍을 수행할 수 있는 합니다.

함수형 프로그래밍 문 사용 하 여 값을 변경할 드문 것입니다. 일부 함수형 언어 문 및 변형을 지원 하지만 일반적으로 함수형 프로그래밍에서 이러한 개념을 사용 하는 없습니다.

### <a name="pure-functions"></a>순수 함수

앞에서 언급 한 순수 함수는 함수:

* 항상 동일한 입력에 동일한 값으로 평가 합니다.
* 부작용 없음.

이 컨텍스트에서 수치 연산 함수 생각 하는 것이 유용 합니다. 수학에서 함수는 해당 인수에만 의존 하 고 부작용이 없는 합니다. 수치 연산 함수가 `f(x) = x + 1`, 값 `f(x)` 의 값에만 의존 `x`합니다. 함수형 프로그래밍의 순수 함수는 동일한 방법입니다.

순수 함수를 작성할 때 함수 인수에만 의존 하 고 부작용에는 아무 작업도 수행 하지 해야 합니다.

전역, 변경할 수 있는 상태에 종속 되어 있으므로 비 순수 함수의 예제는 다음과 같습니다.

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

합니다 `addOneToValue` 명확 하 게 순수 함수가 아닙니다. 때문에 `value` 언제 든 지 다른 값이 1 보다 변경 될 수 있습니다. 이 패턴을 전역 값에 따라 함수형 프로그래밍에서 사용 하지 않아야 하는 것입니다.

파생 작업을 수행 하므로 비 순수 함수의 또 다른 예로 다음과 같습니다.

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

값을 씁니다이 함수는 전역 값에 종속 되지 않습니다, 하지만 `x` 프로그램의 출력입니다. 근본적으로 이렇게 잘못 된 항목이 없는, 하지만 순수 함수가 아닙니다 의미가 있습니다.

제거 된 `printfn` 문이 마지막으로 사용 하면 함수가 순수:

```fsharp
let addOneToValue x = x + 1
```

아니지만이 함수 기본적으로 _더 나은_ 사용 하 여 이전 버전 보다는 `printfn` 문에서 반드시이 함수는 반환 하는 값입니다. 이 호출 함수를 한 번 또는 1 십억 번은 동일한 작업에서 여전히 결과:만 값을 생성 합니다. 이 예측 유용 함수형 프로그래밍에서는 순수 함수는 참조로 투명 하 게 되었음을 의미 합니다.

### <a name="referential-transparency"></a>참조 투명성

참조 투명성은 식과 함수의 속성입니다. 참조로 투명 하 게 식에 대 한 프로그램의 동작을 변경 하지 않고 해당 결과 값으로 바꿔야 할 수 있어야 합니다. 모든 순수 함수는 참조로 투명 하 게 합니다.

순수 함수에서와 마찬가지로 참조 투명성 수학 관점에서 생각 하면 도움이 수 있습니다. 수치 연산 식에서 `y = f(x)`, `f(x)` 함수의 결과로 바꿀 수 있습니다와 같게 됩니다 및 `y`합니다. 이것이 함수형 프로그래밍에서 참조 투명성에 대해서도 마찬가지입니다.

이전에 정의 된 호출 하는 것이 좋습니다. `addOneIfOdd` 두 번 작동 합니다.

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result

let res1 = addOneIffOdd 1 // Produces 2
let res2 = addOneIffOdd 2 // Produces 2
```

인수를 대체 하 고 함수 본문을 사용 하 여 각 함수 호출을 대체할 수에서는 `input` 각 값을 사용 하 여:

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result

let res1 =
    let result =
        if isOdd 1 then
            1 + 1
        else
            1

    result
let res2 =
    let result =
        if isOdd 2 then
            2 + 1
        else
            2

    result
```

둘 다 `res1` 하 고 `res2` 나타내는 함수가 호출 된 것 처럼 동일한 값을 가질 `addOneIfOdd` 참조가 이루어집니다!

또한 함수를 순수 투명 하 게도 참조가 없습니다. 이전 정의 것이 좋습니다 `addOneTovalue`:

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

이 함수를 호출할 때 해당 본문으로 대체 될 수도 있습니다 및 들 될 때마다 발생 합니다.

* 출력에 추가 되기 전에 값을이 출력
* 값이 1에 추가

프로그래밍할 때 F#를 참조 투명성 순도 아니라 목표를 달성 하는 경우가 많습니다. 그러나 여전히 좋습니다 가능한 경우에 순수 함수를 작성 하는 것.

### <a name="immutability"></a>불변성

마지막으로, 불변성은 형식화 된 함수형 프로그래밍의 가장 기본적인 개념 중 하나입니다. F#에서 모든 값은 기본적으로 변경할 수 없습니다. 즉, 변경할 수 있는 것으로 명시적으로 표시 하지 않는 한 내부적으로 일 수 없습니다.

실제로 변경할 수 없는 값으로 작업 하는 "I need 무언가 변경 하려면"에서 프로그래밍 하는 접근 방식을 변경한에 "I need 새 값을 생성 하기 위해"를 의미 합니다.

예를 들어, 기존 항목을 변경 하지 새 값을 생성 값으로 추가 1을 의미 합니다.

```fsharp
let value = 1
let secondValue = value + 1
```

F#, 다음 코드에서는 **되지** 변경할 합니다 `value` 함수, 같음 검사를 수행 하십시오:

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

일부 함수형 프로그래밍 언어 변형을 전혀 지원 하지 않습니다. F#는 지원 되지만 값에 대 한 기본 동작은 아닙니다.

이 개념은 데이터 구조까지 확장합니다. 함수형 프로그래밍을 변경할 수 없는 데이터 구조 집합 (및 더 많은)가 다른 구현을 처음 수 보다 같은 예상 됩니다. 개념적으로 집합에 항목을 추가 집합은 변경 되지 않으면 같은 생성 된 _새_ 추가 값으로 설정 합니다. 내부적으로이 하는 경우가 많습니다 적절 한 데이터 표현의 결과적으로 지정할 수 있도록 값을 효율적으로 추적을 허용 하는 다른 데이터 구조입니다.

값 및 데이터 구조를 사용 하는이 스타일은 새 버전을 만드는 경우에 따라 항목을 수정 하는 모든 작업을 처리 해야 하는 대로 중요 합니다. 따라서 프로그램에서 일관 되도록 같음 및 작음 비교 가능 등.

## <a name="next-steps"></a>다음 단계

다음 섹션에서는 함수형 프로그래밍에 사용할 수 있는 다른 방법을 탐색 하는 함수를 철저 하 게 설명 합니다.

[첫 번째 클래스 함수](first-class-functions.md) 함수 사용 하 여 다양 한 컨텍스트에서 하는 방법을 보여 주는 깊이 탐색 합니다.

## <a name="further-reading"></a>추가 정보

합니다 [기능적으로 생각](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) 시리즈를 사용한 함수형 프로그래밍에 대해 자세히 알아보려면 또 다른 유용한 리소스는 F#합니다. Pragmatic 및 보다 읽기 쉬운 방식으로 함수형 프로그래밍의 기본적인 사항을 다룹니다를 사용 하 여 F# 개념을 설명 하는 기능입니다.
