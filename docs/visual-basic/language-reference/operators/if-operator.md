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
ms.openlocfilehash: 28fb2afb2c4cf78ffbbb028145de647a8dc512ed
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371105"
---
# <a name="if-operator-visual-basic"></a>If 연산자(Visual Basic)

는 단락 평가를 사용 하 여 조건에 따라 두 값 중 하나를 반환 합니다. 연산자는 세 개의 인수를 사용 `If` 하거나 두 개의 인수를 사용 하 여 호출할 수 있습니다.

## <a name="syntax"></a>구문

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a>세 개의 인수를 사용 하 여 연산자를 호출한 경우

`If`세 개의 인수를 사용 하 여를 호출 하는 경우 첫 번째 인수는로 캐스팅할 수 있는 값으로 계산 되어야 합니다 `Boolean` . 이 `Boolean` 값은 평가 되 고 반환 되는 다른 두 인수를 결정 합니다. 다음 목록은 `If` 세 인수를 사용 하 여 연산자를 호출 하는 경우에만 적용 됩니다.

### <a name="parts"></a>부분

|용어|정의|
|---|---|
|`argument1`|필수 요소. `Boolean`. 평가 하 여 반환할 다른 인수를 결정 합니다.|
|`argument2`|필수 요소. `Object`. 가로 계산 되는 경우 평가 되 고 반환 `argument1` `True` 됩니다.|
|`argument3`|필수 요소. `Object`. 가로 계산 되는 경우이 계산 및 반환 되 고 `argument1` `False` , `argument1` 가 [Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` [Nothing](../nothing.md)으로 계산 되는 Nullable 변수 이면이 반환 됩니다.|

`If`세 개의 인수를 사용 하 여 호출 되는 연산자는 `IIf` 단락 계산을 사용 한다는 점을 제외 하 고 함수 처럼 작동 합니다. `IIf`함수는 항상 세 개의 인수를 모두 계산 하는 반면, `If` 세 개의 인수가 있는 연산자는 둘 중 하나만 계산 합니다. 첫 번째 `If` 인수를 계산 하 고 결과를 `Boolean` 값 또는로 캐스팅 합니다 `True` `False` . 값이 이면 `True` `argument2` 가 평가 되 고 해당 값이 반환 되지만 `argument3` 계산 되지 않습니다. 식의 값 `Boolean` 이 인 경우이 `False` `argument3` 평가 되 고 해당 값이 반환 되지만 `argument2` 계산 되지 않습니다. 다음 예에서는 세 개의 인수를 사용 하는 경우를 사용 하는 방법을 보여 줍니다 `If` .

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

다음 예에서는 단락 계산의 값을 보여 줍니다. 이 예에서는 `number` `divisor` 이 0 인 경우를 제외 하 고 변수를 변수로 나누는 두 시도를 보여 줍니다 `divisor` . 이 경우에는 0이 반환 되어야 하며, 런타임 오류가 발생 하므로 나누기를 수행 하려고 시도 하지 않습니다. 식에서 `If` 단락 계산을 사용 하기 때문에 첫 번째 인수 값에 따라 두 번째 또는 세 번째 인수를 계산 합니다. 첫 번째 인수가 true 이면 제수가 0이 아니고 두 번째 인수를 계산 하 여 나누기를 수행 하는 것이 안전 합니다. 첫 번째 인수가 false 이면 세 번째 인수만 계산 되 고 0이 반환 됩니다. 따라서 제수가 0 이면 나누기를 수행 하지 않고 오류 결과가 발생 하지 않습니다. 그러나 `IIf` 는 단락 평가를 사용 하지 않으므로 첫 번째 인수가 false 인 경우에도 두 번째 인수가 평가 됩니다. 이로 인해 런타임 0으로 나누기 오류가 발생 합니다.

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a>두 개의 인수를 사용 하 여 연산자를 호출한 경우

에 대 한 첫 번째 인수를 `If` 생략할 수 있습니다. 이렇게 하면 두 개의 인수만 사용 하 여 연산자를 호출할 수 있습니다. 다음 목록은 `If` 두 개의 인수를 사용 하 여 연산자를 호출 하는 경우에만 적용 됩니다.

### <a name="parts"></a>부분

|용어|정의|
|---|---|
|`argument2`|필수 요소. `Object`. 참조 또는 nullable 값 형식 이어야 합니다. 이 아닌 값으로 계산 되는 경우 평가 되 고 반환 `Nothing` 됩니다.|
|`argument3`|필수 요소. `Object`. 가로 계산 되는 경우 평가 되 고 반환 `argument2` `Nothing` 됩니다.|

인수를 `Boolean` 생략 하면 첫 번째 인수는 참조 또는 nullable 값 형식 이어야 합니다. 첫 번째 인수가로 계산 되는 경우 `Nothing` 두 번째 인수의 값이 반환 됩니다. 다른 모든 경우에는 첫 번째 인수의 값이 반환 됩니다. 다음 예에서는이 평가의 작동 방식을 보여 줍니다.

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Nullable 값 형식](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../nothing.md)
