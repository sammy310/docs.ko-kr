---
title: If 연산자(Visual Basic)
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
ms.openlocfilehash: 9ab01755d75c91ce87acf83e7f406b26c466aef6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663507"
---
# <a name="if-operator-visual-basic"></a>If 연산자(Visual Basic)
사용 조건에 따라 두 값 중 하나를 반환 하는 평가 단락 (short-circuit). `If` 세 개의 인수를 사용 하 여 또는 두 개의 인수를 사용 하 여 연산자를 호출할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a>세 개의 인수를 사용 하 여 호출 연산자  
 때 `If` 라고 세 개의 인수를 사용 하 여 첫 번째 인수도 캐스팅 될 수 있는 값으로 계산 되어야 합니다는 `Boolean`합니다. `Boolean` 계산 되어 반환 되는 다른 두 인수의 값이 결정 됩니다. 다음과 같은 경우에만 적용 되는 `If` 세 개의 인수를 사용 하 여 연산자 라고 합니다.  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`argument1`|필수 요소. `Boolean`. 다른 인수는 평가 및 반환할 결정 합니다.|  
|`argument2`|필수 요소. `Object`. 평가 되 고 반환 된 경우 `argument1` 로 `True`합니다.|  
|`argument3`|필수 요소. `Object`. 평가 되 고 반환 된 경우 `argument1` 로 `False` 이거나 `argument1` 은 [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` 계산 되는 변수 [Nothing](../../../visual-basic/language-reference/nothing.md)합니다.|  
  
 `If` 처럼 작동 하는 세 개의 인수를 사용 하 여 호출 되는 연산자는 `IIf` 함수를 사용 한다는 점을 제외 하 고 단락 (short-circuit) 계산 합니다. `IIf` 함수는 항상 해당 인수의 모든 세를 계산 하지만 `If` 세 개의 인수가 있는 연산자 중 두 개만 계산 합니다. 첫 번째 `If` 인수가 계산 되 고로 캐스팅 결과 `Boolean` 값을 `True` 또는 `False`합니다. 값이 `True`, `argument2` 가 평가 하 고 해당 값이 반환 하지만 `argument3` 평가 되지 않습니다. 경우 값을 `Boolean` 식이 `False`, `argument3` 는 평가 하 고 해당 값이 반환 하지만 `argument2` 평가 되지 않습니다. 다음 예제에서는 사용법을 보여 줍니다. `If` 세 개의 인수를 사용 하는 경우:  
  
 [!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]  
  
 값을 보여 주는 다음 예제에서는 평가 단락 (short-circuit). 이 예제에서는 변수를 나누는 데 두 시도 보여 줍니다 `number` 변수로 `divisor` 경우를 제외 하 고 `divisor` 0입니다. 이런 경우 0이 반환 되어야 합니다 및 하지 수행 되도록 하면 런타임 오류가 발생 하 게 됩니다 나누기를 수행 합니다. 때문에 `If` 사용 되는 식 평가 단락 (short-circuit), 두 번째 또는 첫 번째 인수의 값에 따라 세 번째 인수를 평가 합니다. 첫 번째 인수가 true 이면 제 수 0이 아니면 및 두 번째 인수를 평가 하 고 나누기를 수행 해도 됩니다. 첫 번째 인수가 false 이면 세 번째 인수에만 평가 되 고 0이 반환 됩니다. 따라서 제 수 0 인 경우 하지 나누기 하지 않으며 오류가 발생 하는 데 이루어집니다. 그러나 때문에 `IIf` 사용 하지 않는 평가 단락 (short-circuit), 두 번째 인수는 첫 번째 인수가 false 인 경우에 계산 됩니다. 이 런타임에 0으로 나누기 오류가 발생합니다.  
  
 [!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]  
  
## <a name="if-operator-called-with-two-arguments"></a>연산자는 두 개의 인수를 사용 하 여 호출 하는 경우  
 첫 번째 인수 `If` 생략할 수 있습니다. 이 연산자를를 두 개의 인수를 사용 하 여 호출할 수 있습니다. 다음과 같은 경우에만 적용 되는 `If` 연산자는 두 개의 인수를 사용 하 여 호출 됩니다.  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`argument2`|필수 요소. `Object`. 참조 또는 nullable 형식 이어야 합니다. 계산 되 고 이외의 값으로 계산 될 때 반환 `Nothing`합니다.|  
|`argument3`|필수 요소. `Object`. 평가 되 고 반환 된 경우 `argument2` 로 `Nothing`합니다.|  
  
 경우는 `Boolean` 인수를 생략 하면, 첫 번째 인수는 참조 또는 nullable 형식 이어야 합니다. 첫 번째 인수를 평가 하는 경우 `Nothing`, 두 번째 인수의 값이 반환 됩니다. 다른 모든 경우에 첫 번째 인수의 값이 반환 됩니다. 다음 예제에서는이 평가 작동 원리를 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Nullable 값 형식](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
