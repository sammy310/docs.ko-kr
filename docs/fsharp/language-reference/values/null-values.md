---
title: Null 값
description: 'F # 프로그래밍 언어에서 null 값이 사용 되는 방법에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 3b2c7ebe7b8eff08f7c3e76b9715ccab1bbd5d36
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558350"
---
# <a name="null-values"></a>Null 값

이 항목에서는 F #에서 null 값이 사용 되는 방법에 대해 설명 합니다.

## <a name="null-value"></a>Null 값

Null 값은 일반적으로 값 또는 변수에 대 한 F #에서 사용 되지 않습니다. 그러나 null은 특정 상황에서 비정상 값으로 나타납니다. 형식이 F #에서 정의 되는 경우 [Allownullliteral](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-allownullliteralattribute.html#Value) 특성이 형식에 적용 되지 않는 한 null은 일반 값으로 허용 되지 않습니다. 형식이 다른 .NET 언어에서 정의 되는 경우 null은 가능한 값 이며, 이러한 형식과 상호 운용할 경우 F # 코드에서 null 값이 발생할 수 있습니다.

F #에 정의 되 고 F #에서 엄격 하 게 사용 되는 형식의 경우 F # 라이브러리를 사용 하 여 null 값을 직접 만드는 유일한 방법은 Unchecked를 사용 하는 것입니다. 또는 [array.zerocreate](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate) [의 defaultof](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators-unchecked.html#defaultof) 합니다. 그러나 다른 .NET 언어에서 사용 되는 F # 형식의 경우 또는 .NET Framework와 같이 F #으로 작성 되지 않은 API에서 해당 형식을 사용 하는 경우 null 값이 발생할 수 있습니다.

`option`다른 .net 언어에서 가능한 null 값을 가진 참조 변수를 사용할 수 있는 경우 F #에서 형식을 사용할 수 있습니다. Null 대신 F # 형식을 사용 하는 `option` 경우에는 개체가 없는 경우 옵션 값을 사용 합니다 `None` . 개체를 사용 하는 경우 옵션 값을 `Some(obj)` 개체와 함께 사용 합니다 `obj` . 자세한 내용은 [옵션](../options.md)을 참조하세요. 의 경우에는 값을 옵션으로 압축할 수 있습니다 `null` `Some x` `x` `null` . 따라서 값이 일 때를 사용 하는 것이 중요 `None` `null` 합니다.

`null`키워드는 F # 언어의 유효한 키워드 이며 다른 .net 언어로 작성 된 .NET Framework api 또는 다른 api로 작업할 때 사용 해야 합니다. Null 값이 필요할 수 있는 두 가지 경우는 .NET API를 호출 하 고, null 값을 인수로 전달 하 고, 반환 값 또는 .NET 메서드 호출에서 출력 매개 변수를 해석할 때입니다.

Null 값을 .NET 메서드에 전달 하려면 `null` 호출 코드에서 키워드를 사용 하면 됩니다. 다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

.NET 메서드에서 얻은 null 값을 해석 하려면 가능 하면 패턴 일치를 사용 합니다. 다음 코드 예제에서는 패턴 일치를 사용 하 여 `ReadLine` 입력 스트림의 끝을 지나서 읽으려고 할 때에서 반환 되는 null 값을 해석 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

를 사용 하는 경우를 호출 하는 등의 다른 방법으로 F # 형식에 대 한 Null 값을 생성할 수도 있습니다 `Array.zeroCreate` `Unchecked.defaultof` . Null 값을 캡슐화 된 상태로 유지 하려면 이러한 코드를 주의 해 서 사용 해야 합니다. F #에만 사용 되는 라이브러리에서는 모든 함수에서 null 값을 확인 하지 않아도 됩니다. 다른 .NET 언어와의 상호 운용을 위한 라이브러리를 작성 하는 경우 `ArgumentNullException` c # 또는 Visual Basic 코드와 마찬가지로 null 입력 매개 변수에 대 한 검사를 추가 하 고을 throw 해야 할 수 있습니다.

다음 코드를 사용 하 여 임의의 값이 null 인지 확인할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>참조

- [값](index.md)
- [일치 식](../match-expressions.md)
