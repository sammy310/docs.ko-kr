---
title: 자동 일반화
description: 에 대해 알아봅니다 하는 방법 F# 자동으로 인수 및 함수의 유형은 일반화 하 여 가능한 경우 여러 형식으로 작동 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: 15ecf8e6f07da19bb015fd028a7465ba8b837190
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937542"
---
# <a name="automatic-generalization"></a>자동 일반화

F#사용 유형 함수와 식을 평가 하는 유추를 입력 합니다. 이 항목에 설명 하는 방법 F# 자동으로 인수 및 함수의 유형은 일반화 하 여 가능한 경우 여러 형식으로 작동 합니다.

## <a name="automatic-generalization"></a>자동 일반화

F# 컴파일러에서 형식 유추는 함수에서 수행 하는 경우 지정된 된 매개 변수에 제네릭 수 있는지 여부를 결정 합니다. 컴파일러는 각 매개 변수를 검사 하 고 함수 해당 매개 변수의 특정 형식에 종속 되어 있는지 여부를 결정 합니다. 표시 되지 않는 형식은 제네릭으로 유추 됩니다.

다음 코드 예제에서는 제네릭인 것으로 컴파일러에서 유추 하는 함수를 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

형식 유추 됩니다 `'a -> 'a -> 'a`합니다.

형식을 알 수 없는 형식이 같은 두 개의 인수를 사용 하 고 동일한 형식의 값을 반환 하는 함수 임을 나타냅니다. 이전 함수 일 수 있는 이유 중 하나로 제네릭는 큼-연산자 (`>`) 제네릭인 자체입니다. 큼-서명이 연산자 보다 `'a -> 'a -> bool`합니다. 일부 연산자는 제네릭 및 제네릭이 아닌 함수 또는 연산자와 함께 매개 변수 형식을 사용 하는 함수에서 코드를 하는 경우 해당 매개 변수 형식을 일반화할 수 없습니다.

때문에 `max` 는 일반, 사용할 수 있습니다 형식과 같은 `int`, `float`등, 다음 예와에서 같이 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

그러나 두 인수가 동일한 형식 이어야 합니다. 서명이 `'a -> 'a -> 'a`이 아니라 `'a -> 'b -> 'a`합니다. 따라서 다음 코드는 형식이 일치 하지 않아 오류가 발생 합니다.

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

`max` 함수 역시 큼 지 원하는 모든 형식-than 연산자입니다. 따라서 사용할 수 있습니다도 문자열에서 다음 코드와 같이 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a>값 제한 사항

컴파일러는 명시적 인수가 있는 전체 함수 정의 및 간단한 변경할 수 없는 값에만 자동 일반화를 수행 합니다.

즉, 충분히는 특정 형식으로 제한 되지 않습니다 하지만 역시 생길 수는 코드를 컴파일할 경우 컴파일러에서 오류가 발생 하는 것을 의미 합니다. 이 문제에 대 한 오류 메시지가이 제한 값에 대 한 자동 일반화에 참조를 *제한 값*합니다.

일반적으로 값 제한 오류 제네릭으로 구문을 하는데 컴파일러는 일반화 하는 데 필요한 정보가 부족 하거나 실수로 제네릭이 아닌 구문에 충분 한 형식 정보를 생략 하면 발생 합니다. 값 제한 오류를 해결 자세히 다음 방법 중 하나에서 형식 유추 문제를 제한 하려면 보다 명시적인 정보를 제공 하는 것:

- 명시적 형식 주석의 값 또는 매개 변수를 추가 하 여 제네릭이 아닌 형식을 제한 합니다.

- 문제를 일반화할 수 없는 구문을 사용 하 여 함수 컴퍼지션 등의 일반 기능을 정의 또는 불완전 하 게 커리 된 함수 인수를 적용 하는 경우 일반 함수 정의 함수로 다시 작성 하려고 합니다.

- 문제는 너무 복잡 하 여 일반화 된 식이 함수에는 추가, 사용 되지 않는 매개 변수를 추가 하 여 확인 합니다.

- 명시적인 제네릭 형식 매개 변수를 추가 합니다. 이 옵션은 거의 사용 되었습니다.

- 다음 코드 예제에서는 이러한 각 시나리오를 보여 줍니다.

사례 1: 너무 복잡 한 식입니다. 이 예제에서는 목록 `counter` 은 `int option ref`, 간단한 변경할 수 없는 값으로 정의 하지 않았습니다.

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

사례 2: 제네릭 함수를 정의 하려면 일반화할 수 없는 구문을 사용 합니다. 이 예제에서는 구문을 함수 인수의 부분 적용 하므로 일반화할 수 없습니다.

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

사례 3: 추가, 사용 되지 않는 매개 변수를 추가합니다. 이 식은 단순 하기 일반화 되어 컴파일러 오류가 발생 합니다. 값 제한 합니다.

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

사례 4: 형식 매개 변수를 추가합니다.

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

값이 마지막 경우에서 예를 들어 다음과 같이 여러 다른 형식의 값을 만드는 데 사용할 수 있는 형식 함수를 적용 됩니다.

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a>참고자료

- [형식 유추](../type-inference.md)
- [제네릭](index.md)
- [정적으로 확인된 형식 매개 변수](statically-resolved-type-parameters.md)
- [제약 조건](constraints.md)