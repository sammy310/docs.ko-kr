---
title: 인라인 함수
description: 사용 하는 방법을 알아봅니다 F# 호출 코드에 직접 통합 되는 인라인 함수입니다.
ms.date: 05/16/2016
ms.openlocfilehash: d1c3fb3d2721024febc95b3c5e01e06cd547f81e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642063"
---
# <a name="inline-functions"></a>인라인 함수

*인라인 함수* 는 호출 코드에 직접 통합 되는 함수입니다.

## <a name="using-inline-functions"></a>인라인 함수를 사용 하 여

정적 형식 매개 변수를 사용 하면 형식 매개 변수로 매개 변수화 되는 모든 함수는 인라인 이어야 합니다. 이렇게 하면 컴파일러가 이러한 형식 매개 변수를 확인할 수 있습니다. 일반적인 제네릭 형식 매개 변수를 사용 하는 경우에 이러한 제한이 없습니다.

이외의 멤버 제약 조건 사용 하도록 설정, 인라인 함수 코드 최적화에서 유용할 수 있습니다. 그러나 인라인 함수 남용 되지 않도록 컴파일러 최적화 및 라이브러리 함수의 구현 형태가 변화에 덜 정보 훼손에 강하도록 코드를 발생할 수 있습니다. 따라서 다른 모든 최적화 기술을 시도 하지 않는 한 최적화를 위해 인라인 함수를 사용 하지 마십시오. 함수 또는 메서드 인라인 만들기 성능이 향상 될 수 있습니다 하지만 하는 경우가 아니라면 항상 있습니다. 따라서 특정된 함수를 인라인으로 만드는 긍정적인 영향을 미칠 실제로 확인 하려면 성능 측정을도 사용 해야 합니다.

`inline` 최상위 수준에서 모듈 수준에서 또는 클래스에서 메서드 수준에서 함수에 한정자를 적용 될 수 있습니다.

다음 코드 예제에서는 최상위 수준, 인라인 인스턴스 메서드 및 인라인 정적 메서드는 인라인 함수를 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a>인라인 함수 및 형식 유추

현재 상태 `inline` 형식 유추에 영향을 줍니다. 반면 인라인이 아닌 함수에 사용할 수 없습니다 인라인 함수 수 있는 정적으로 확인 된 형식 매개 변수 때문입니다. 경우 다음 코드 예제를 보여 줍니다 위치 `inline` 는 정적으로 확인 된 형식 매개 변수가 있는 함수를 사용 하 고 있으므로 유용 합니다 `float` 변환 연산자.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

없이 합니다 `inline` 한정자를 형식 유추는 함수가 특정 형식,이 경우 강제로 `int`입니다. 하지만 `inline` 한정자에 함수를 정적으로 확인 된 형식 매개 변수를 유추 합니다. 사용 하 여는 `inline` 다음 한정자를 형식 유추 됩니다.

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

즉, 함수를 변환할 수 있는 모든 형식을 허용 하는지 **float**합니다.

## <a name="see-also"></a>참고자료

- [함수](index.md)
- [제약 조건](../generics/constraints.md)
- [정적으로 확인된 형식 매개 변수](../generics/statically-resolved-type-parameters.md)
