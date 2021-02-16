---
description: '자세한 정보: 값 비교 (Visual Basic)'
title: 값 비교
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: b5d2228b5bb6be18aecebcd0247a1e29e29df9ec
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472711"
---
# <a name="value-comparisons-visual-basic"></a>값 비교(Visual Basic)

비교 연산자를 사용 하 여 숫자 변수의 값을 비교 하는 식을 생성할 수 있습니다. 이러한 식은 `Boolean` 비교가 true 인지 false 인지에 따라 값을 반환 합니다. 이러한 식의 예는 다음과 같습니다.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 `True`45가 26 보다 크므로 첫 번째 식은로 평가 됩니다. 두 번째 예제는 `False` 26이 45 보다 크지 않기 때문에로 평가 됩니다.  
  
 이러한 방식으로 숫자 식을 비교할 수도 있습니다. 비교 하는 식은 다음 예제와 같이 복합 식일 수 있습니다.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 앞의 복합 식에는 리터럴, 변수 및 함수 호출이 포함 되어 있습니다. 비교 연산자의 양쪽에 있는 식을 계산 하 고 결과 값을 비교 연산자를 사용 하 여 비교 합니다 `>=` . 좌 변의 식의 값이 오른쪽 식의 값 보다 크거나 같으면 전체 식이로 계산 되 고 `True` , 그렇지 않으면로 계산 됩니다 `False` .  
  
 값을 비교 하는 식은 `If...Then` 다음 예제와 같이 생성에서 가장 일반적으로 사용 됩니다.  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 `=`부호는 비교 연산자 및 대입 연산자입니다. 비교 연산자로 사용 되는 경우 다음 예제와 같이 왼쪽의 값이 오른쪽의 값과 같은지 여부를 평가 합니다.  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 `Boolean`,, 또는 문과 같이 값이 필요한 경우 `If` `While` `Loop` `ElseIf` 또는 변수에 할당 하거나 값을 변수에 전달할 때 `Boolean` 비교 식을 사용할 수도 있습니다. 다음 예에서는 비교 식에서 반환 된 값이 변수에 할당 됩니다 `Boolean` .  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a>추가 정보

- [부울 식](boolean-expressions.md)
- [연산자 및 식](index.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [방법: 숫자 값 계산](how-to-calculate-numeric-values.md)
- [Visual Basic에서의 연산자 우선 순위](../../../language-reference/operators/operator-precedence.md)
