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
ms.openlocfilehash: 6d25519dac31dc91f8560fd3252ba3e2622de370
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331010"
---
# <a name="if-operator-visual-basic"></a>If 연산자(Visual Basic)

는 단락 평가를 사용 하 여 조건에 따라 두 값 중 하나를 반환 합니다. `If` 연산자는 세 개의 인수를 사용 하거나 두 개의 인수를 사용 하 여 호출할 수 있습니다.

## <a name="syntax"></a>구문

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a>세 개의 인수를 사용 하 여 연산자를 호출한 경우

세 개의 인수를 사용 하 여 `If`를 호출 하는 경우 첫 번째 인수는 `Boolean`으로 캐스팅할 수 있는 값으로 계산 되어야 합니다. 이 `Boolean` 값은 평가 되 고 반환 되는 다른 두 인수를 결정 합니다. 다음 목록은 세 인수를 사용 하 여 `If` 연산자를 호출한 경우에만 적용 됩니다.

### <a name="parts"></a>요소

|용어|정의|
|---|---|
|`argument1`|필수 요소. `Boolean`. 평가 하 여 반환할 다른 인수를 결정 합니다.|
|`argument2`|필수 요소. `Object`. `argument1`이 `True`으로 계산 되는 경우 평가 되 고 반환 됩니다.|
|`argument3`|필수 요소. `Object`. `argument1` `False` 계산 되는 경우를 계산 하 고 반환 [됩니다. `argument1`](../../../visual-basic/language-reference/nothing.md)null로 계산 되는 [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` 변수인 경우|

세 개의 인수를 사용 하 여 호출 되는 `If` 연산자는 단락 계산을 사용 한다는 점을 제외 하 고는 `IIf` 함수 처럼 작동 합니다. `IIf` 함수는 항상 세 개의 인수를 모두 계산 하는 반면, 세 개의 인수가 있는 `If` 연산자는 둘 중 하나만 계산 합니다. 첫 번째 `If` 인수를 계산 하 고 결과를 `Boolean` 값 `True` 또는 `False`로 캐스팅 합니다. 값이 `True`이면 `argument2` 평가 되 고 해당 값이 반환 되지만 `argument3`는 계산 되지 않습니다. `Boolean` 식의 값이 `False`경우 `argument3` 계산 되 고 해당 값이 반환 되지만 `argument2`는 계산 되지 않습니다. 다음 예에서는 세 개의 인수를 사용 하는 경우 `If`를 사용 하는 방법을 보여 줍니다.

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

다음 예에서는 단락 계산의 값을 보여 줍니다. 이 예에서는 `divisor` 0 인 경우를 제외 하 고 변수 `divisor` 변수 `number`를 나누는 두 시도를 보여 줍니다. 이 경우에는 0이 반환 되어야 하며, 런타임 오류가 발생 하므로 나누기를 수행 하려고 시도 하지 않습니다. `If` 식은 단락 계산을 사용 하기 때문에 첫 번째 인수 값에 따라 두 번째 또는 세 번째 인수를 계산 합니다. 첫 번째 인수가 true 이면 제수가 0이 아니고 두 번째 인수를 계산 하 여 나누기를 수행 하는 것이 안전 합니다. 첫 번째 인수가 false 이면 세 번째 인수만 계산 되 고 0이 반환 됩니다. 따라서 제수가 0 이면 나누기를 수행 하지 않고 오류 결과가 발생 하지 않습니다. 그러나 `IIf`는 단락 계산을 사용 하지 않으므로 첫 번째 인수가 false 인 경우에도 두 번째 인수가 평가 됩니다. 이로 인해 런타임 0으로 나누기 오류가 발생 합니다.

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a>두 개의 인수를 사용 하 여 연산자를 호출한 경우

`If`에 대 한 첫 번째 인수는 생략할 수 있습니다. 이렇게 하면 두 개의 인수만 사용 하 여 연산자를 호출할 수 있습니다. 다음 목록은 두 개의 인수를 사용 하 여 `If` 연산자를 호출한 경우에만 적용 됩니다.

### <a name="parts"></a>요소

|용어|정의|
|---|---|
|`argument2`|필수 요소. `Object`. 참조 또는 nullable 형식 이어야 합니다. `Nothing`이외의 값으로 계산 되는 경우 평가 되 고 반환 됩니다.|
|`argument3`|필수 요소. `Object`. `argument2`이 `Nothing`으로 계산 되는 경우 평가 되 고 반환 됩니다.|

`Boolean` 인수를 생략 하는 경우 첫 번째 인수는 참조 또는 nullable 형식 이어야 합니다. 첫 번째 인수가 `Nothing`로 계산 되는 경우 두 번째 인수의 값이 반환 됩니다. 다른 모든 경우에는 첫 번째 인수의 값이 반환 됩니다. 다음 예에서는이 평가의 작동 방식을 보여 줍니다.

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Nullable 값 형식](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../nothing.md)
