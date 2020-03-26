---
title: If 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 3b45a5afe331bd00c2b92f8c305351b77bc319cf
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249489"
---
# <a name="if-operator-visual-basic"></a>If 연산자(Visual Basic)

단락 평가를 사용하여 두 값 중 하나를 조건부로 반환합니다. 연산자는 `If` 세 개의 인수 또는 두 개의 인수로 호출할 수 있습니다.

## <a name="syntax"></a>구문

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a>연산자가 세 개의 인수로 호출된 경우

세 `If` 개의 인수를 사용하여 호출되는 경우 첫 번째 인수는 `Boolean`로 캐스팅할 수 있는 값으로 평가해야 합니다. 이 `Boolean` 값은 다른 두 인수 중 평가 및 반환을 결정합니다. 다음 목록은 세 개의 `If` 인수를 사용하여 연산자가 호출된 경우에만 적용됩니다.

### <a name="parts"></a>부분

|용어|정의|
|---|---|
|`argument1`|필수 사항입니다. `Boolean`. 평가하고 반환할 다른 인수를 결정합니다.|
|`argument2`|필수 사항입니다. `Object`. 를 평가하는 `argument1` 경우 평가 `True`및 반환됩니다.|
|`argument3`|필수 사항입니다. `Object`. 평가하거나 `argument1` `False` [Nothing으로](../../../visual-basic/language-reference/nothing.md)평가하는 `argument1` [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` 변수인 경우 평가 및 반환됩니다.|

세 `If` 개의 인수로 호출되는 연산자는 단락 평가를 사용한다는 점을 제외하면 `IIf` 함수처럼 작동합니다. 함수는 `IIf` 항상 세 개의 인수를 모두 평가하는 `If` 반면 세 개의 인수가 있는 연산자는 그 중 두 개만 평가합니다. 첫 `If` 번째 인수가 평가되고 결과가 `Boolean` 값 `True` 또는 `False`으로 캐스팅됩니다. 값이 `True`으로 평가되고 `argument2` 해당 값이 반환되지만 `argument3` 평가되지 는 않습니다. `Boolean` 식의 값이 `False`"을 `argument3` 평가하고 해당 값이 반환되지만 `argument2` 평가되지 않습니다. 다음 예제에서는 세 개의 `If` 인수를 사용할 때의 사용을 보여 줍니다.

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

다음 예제에서는 단락 평가의 값을 보여 줍니다. 이 예제에서는 0을 `number` 제외하고 `divisor` 변수를 `divisor` 변수로 나누려는 두 가지 시도를 보여 주십니다. 이 경우 0을 반환해야 하며 런타임 오류가 발생하므로 분할을 수행하려고 시도해서는 안 됩니다. 식은 `If` 단락 계산을 사용하기 때문에 첫 번째 인수의 값에 따라 두 번째 또는 세 번째 인수를 평가합니다. 첫 번째 인수가 true이면 제수는 0이 아니며 두 번째 인수를 평가하고 분할을 수행하는 것이 안전합니다. 첫 번째 인수가 false이면 세 번째 인수만 평가되고 0이 반환됩니다. 따라서 제수0이면 분할을 수행하려고 시도하지 않고 오류 결과가 없습니다. 그러나 단락 `IIf` 평가를 사용하지 않으므로 첫 번째 인수가 false인 경우에도 두 번째 인수가 평가됩니다. 이렇게 하면 런타임을 0으로 나누는 오류가 발생합니다.

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a>연산자가 두 개의 인수로 호출된 경우

첫 번째 `If` 인수를 생략할 수 있습니다. 이렇게 하면 두 개의 인수만 사용하여 연산을 호출할 수 있습니다. 다음 목록은 연산자가 `If` 두 개의 인수로 호출될 때만 적용됩니다.

### <a name="parts"></a>부분

|용어|정의|
|---|---|
|`argument2`|필수 사항입니다. `Object`. 참조 또는 nullable 값 형식이어야 합니다. 평가되고 반환될 때 다른 것으로 `Nothing`평가됩니다.|
|`argument3`|필수 사항입니다. `Object`. 를 평가하는 `argument2` 경우 평가 `Nothing`및 반환됩니다.|

`Boolean` 인수를 생략하면 첫 번째 인수는 참조 또는 nullable 값 형식이어야 합니다. 첫 번째 인수가 `Nothing`를 평가하는 경우 두 번째 인수의 값이 반환됩니다. 다른 모든 경우에는 첫 번째 인수의 값이 반환됩니다. 다음 예제에서는 이 평가의 작동 방식을 보여 줍니다.

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Nullable 값 형식](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../nothing.md)
