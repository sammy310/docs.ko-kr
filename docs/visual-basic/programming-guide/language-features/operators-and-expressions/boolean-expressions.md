---
description: '자세한 정보: 부울 식 (Visual Basic)'
title: 부울 식
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: 3b752e2146755e1272b261f32931e3022e8ef354
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100465316"
---
# <a name="boolean-expressions-visual-basic"></a>부울 식(Visual Basic)

*부울 식은* [부울 데이터 형식의](../../../language-reference/data-types/boolean-data-type.md)값 (또는)으로 계산 되는 식입니다. `True` `False` `Boolean` 식은 여러 형식을 사용할 수 있습니다. 가장 간단한 방법은 `Boolean` `Boolean` 다음 예제와 같이 변수의 값을 리터럴로 직접 비교 하는 것입니다.  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a>= 연산자의 두 가지 의미  

 대입문은 `newCustomer = True` 위의 예제에서 식과 동일 하지만 다른 함수를 수행 하 고 다르게 사용 됩니다. 앞의 예제에서 식은 `newCustomer = True` 부울 값을 나타내고 `=` 부호는 비교 연산자로 해석 됩니다. 독립 실행형 문에서 `=` 부호는 대입 연산자로 해석 되 고 오른쪽의 값을 왼쪽의 변수에 할당 합니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 자세한 내용은 [값 비교](value-comparisons.md) 및 [문](../../../language-reference/statements/index.md)을 참조 하세요.  
  
## <a name="comparison-operators"></a>비교 연산자  

 ,,,, 및와 같은 비교 연산자는 `=` `<` `>` `<>` `<=` `>=` 연산자의 좌 변에 있는 식을 연산자 우변의 식과 비교 하 고 결과를 또는로 평가 하 여 부울 식을 생성 `True` `False` 합니다. 다음은 이에 대한 예입니다.  
  
 `42 < 81`  
  
 42는 81 보다 작으므로 앞의 예제에서 부울 식은로 계산 됩니다 `True` . 이러한 식 종류에 대 한 자세한 내용은 [값 비교](value-comparisons.md)를 참조 하세요.  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>논리 연산자와 결합 된 비교 연산자  

 논리 연산자를 사용 하 여 비교 식을 결합 하 여 보다 복잡 한 부울 식을 생성할 수 있습니다. 다음 예에서는 비교 연산자를 논리 연산자와 함께 사용 하는 방법을 보여 줍니다.  
  
 `x > y And x < 1000`  
  
 앞의 예제에서 전체 식의 값은 연산자의 양쪽에 있는 식의 값에 따라 달라 집니다 `And` . 두 식이 모두 이면 `True` 전체 식이로 평가 `True` 됩니다. 두 식이 모두 이면 `False` 전체 식이로 평가 `False` 됩니다.  
  
## <a name="short-circuiting-operators"></a>Short-Circuiting 연산자  

 논리 연산자 `AndAlso` 및 `OrElse` *표현 동작은 단락* 이라고 합니다. 단락 연산자는 왼쪽 피연산자를 먼저 계산 합니다. 왼쪽 피연산자가 전체 식의 값을 결정 하는 경우 오른쪽 식을 계산 하지 않고 프로그램 실행이 진행 됩니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 앞의 예제에서 연산자는 왼쪽 식를 계산 `45 < 12` 합니다. 왼쪽 식이로 계산 되기 때문에 `False` 전체 논리 식은로 계산 되어야 합니다 `False` . 따라서 프로그램 실행은 `If` 오른쪽 식를 평가 하지 않고 블록 내에서 코드 실행을 건너뜁니다 `testFunction(3)` . `testFunction()`왼쪽 식이 전체 식을 falsifies이 예에서는를 호출 하지 않습니다.  
  
 마찬가지로를 사용 하는 논리 식의 왼쪽 식이 `OrElse` 로 계산 `True` 되 면 왼쪽 식에서 전체 식의 유효성을 이미 검사 했기 때문에 오른쪽 식을 계산 하지 않고 다음 코드 줄로 실행을 진행 합니다.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>단락 이외의 연산자와 비교  

 반면 논리 연산자와는 논리 연산자를 모두 사용할 때 계산 됩니다 `And` `Or` . 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 앞의 예제에서는 `testFunction()` 왼쪽 식이로 계산 되는 경우에도를 호출 합니다 `False` .  
  
## <a name="parenthetical-expressions"></a>괄호 식  

 괄호를 사용 하 여 부울 식의 계산 순서를 제어할 수 있습니다. 괄호로 묶은 식이 먼저 계산 됩니다. 여러 중첩 수준에 대해 가장 많이 중첩 된 식에 우선 순위가 부여 됩니다. 괄호 안에 연산자 우선 순위 규칙에 따라 계산이 진행 됩니다. 자세한 내용은 [Visual Basic 연산자 우선 순위](../../../language-reference/operators/operator-precedence.md)를 참조 하세요.  
  
## <a name="see-also"></a>추가 정보

- [Visual Basic의 논리 및 비트 연산자](logical-and-bitwise-operators.md)
- [값 비교](value-comparisons.md)
- [문](../statements.md)
- [비교 연산자](../../../language-reference/operators/comparison-operators.md)
- [연산자의 효율적 결합](efficient-combination-of-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../language-reference/operators/operator-precedence.md)
- [Boolean 데이터 형식](../../../language-reference/data-types/boolean-data-type.md)
