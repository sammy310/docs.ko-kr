---
title: 유연한 형식
description: '매개 변수, 변수 또는 값에 지정 된 형식과 호환 되는 형식이 있음을 나타내는 F # 유연한 형식 주석을 사용 하는 방법에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 44241ad082cd7f3de9e0cc6a48b8a8946e7b33d3
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557752"
---
# <a name="flexible-types"></a>유연한 형식

*유연한 형식 주석은* 매개 변수, 변수 또는 값에 지정 된 형식과 호환 되는 형식이 있음을 나타냅니다 .이 경우 호환성은 클래스 또는 인터페이스의 개체 지향 계층 구조에 있는 위치에 따라 결정 됩니다. 유연한 형식은 형식 계층 구조에서 더 높은 형식으로의 자동 변환이 발생 하지 않는 경우 특히 유용 하지만, 계층 구조 또는 인터페이스를 구현 하는 모든 형식에 대해 기능을 사용할 수 있도록 하려는 경우에도 유용 합니다.

## <a name="syntax"></a>구문

```fsharp
#type
```

## <a name="remarks"></a>설명

이전 구문에서 *형식은* 기본 형식 또는 인터페이스를 나타냅니다.

유연한 형식은 기본 또는 인터페이스 형식과 호환 되는 형식으로 허용 되는 형식을 제한 하는 제약 조건이 있는 제네릭 형식과 동일 합니다. 즉, 다음 두 줄의 코드는 동일 합니다.

```fsharp
#SomeType

'T when 'T :> SomeType
```

유연한 형식은 여러 유형의 상황에서 유용 합니다. 예를 들어 고차 함수 (함수를 인수로 사용 하는 함수)가 있는 경우 함수에서 유연한 형식을 반환 하는 것이 유용한 경우가 많습니다. 다음 예제에서의 시퀀스 인수를 사용 하는 유연한 형식을 사용 하면 `iterate2` 고차 함수에서 시퀀스, 배열, 목록 및 기타 열거 가능한 형식을 생성 하는 함수를 사용할 수 있습니다.

다음 두 함수 중 하나는 시퀀스를 반환 하는 함수 중 하나는 유연한 형식을 반환 하는 함수입니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

또 다른 예로, [Seq. concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#concat) library 함수를 살펴보겠습니다.

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

다음의 열거 가능한 시퀀스를이 함수에 전달할 수 있습니다.

- 목록 목록
- 배열 목록
- 목록 배열
- 시퀀스의 배열입니다.
- 열거 가능한 시퀀스의 다른 조합

다음 코드에서는를 사용 하 여 `Seq.concat` 유연한 형식으로 지원할 수 있는 시나리오를 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

출력은 다음과 같습니다.

```console
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

다른 개체 지향 언어와 마찬가지로 F #의 경우 인터페이스를 구현 하는 파생 형식 또는 형식이 자동으로 기본 형식 또는 인터페이스 형식으로 변환 됩니다. 이러한 자동 변환은 직접 인수에서 발생 하지만 형식이 하위 위치에 있거나 함수 형식의 반환 형식 또는 형식 인수로 같은 보다 복잡 한 형식의 일부로 포함 된 경우에는 발생 하지 않습니다. 따라서 유연한 형식 표기법은 적용 하는 형식이 보다 복잡 한 형식의 일부일 때 주로 유용 합니다.

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
- [제네릭](./generics/index.md)
