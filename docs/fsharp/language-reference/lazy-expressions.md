---
title: Lazy 식
description: 'F # 지연 식으로 앱과 라이브러리의 성능을 향상 시킬 수 있는 방법을 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 0b8496467295ce6793f80c341af88bb1819f4a47
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425505"
---
# <a name="lazy-expressions"></a>Lazy 식

*지연 식은* 즉시 계산 되지 않고 결과가 필요할 때 계산 되는 식입니다. 이를 통해 코드의 성능을 향상 시킬 수 있습니다.

## <a name="syntax"></a>구문

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>설명

이전 구문에서 *expression* 은 결과가 필요한 경우에만 평가 되는 코드이 고, *identifier* 는 결과를 저장 하는 값입니다. 값은 형식입니다 `Lazy<'T>` . 여기서에 사용 되는 실제 형식은 `'T` 식의 결과에서 결정 됩니다.

지연 식은 결과가 필요한 상황 으로만 식의 실행을 제한 하 여 성능을 향상 시킬 수 있습니다.

식을 강제로 수행 하려면 메서드를 호출 `Force` 합니다. `Force` 실행이 한 번만 수행 되도록 합니다. 에 대 한 후속 호출은 `Force` 동일한 결과를 반환 하지만 코드를 실행 하지는 않습니다.

다음 코드는 지연 식의 사용 및 사용을 보여 줍니다 `Force` . 이 코드에서의 형식은 `result` 이 `Lazy<int>` 고, 메서드는을 `Force` 반환 `int` 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

지연 계산은 `Lazy` 형식이 아니라 시퀀스에도 사용 됩니다. 자세한 내용은 [시퀀스](sequences.md)를 참조 하세요.

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
- [Lazyextensions.createfromvalue 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-lazyextensions.html)
