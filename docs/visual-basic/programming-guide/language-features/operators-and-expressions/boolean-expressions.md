---
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
ms.openlocfilehash: 1000ec6e4b35d0cb2c6232b50f9a9551cb0dfdcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350807"
---
# <a name="boolean-expressions-visual-basic"></a>부울 식(Visual Basic)
*부울 식은* `True` 또는 `False`[부울 데이터 형식의](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)값으로 계산 되는 식입니다. `Boolean` 식에는 여러 가지 형식이 사용 될 수 있습니다. 가장 간단한 방법은 다음 예제와 같이 `Boolean` 변수의 값을 `Boolean` 리터럴로 직접 비교 하는 것입니다.  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a>= 연산자의 두 가지 의미  
 대입문은 앞의 예제에서 식과 동일한 것으로 보이지만 다른 함수를 수행 하 고 다르게 사용 됩니다 `newCustomer = True`. 앞의 예제에서 식 `newCustomer = True`은 부울 값을 나타내고 `=` 부호는 비교 연산자로 해석 됩니다. 독립형 문에서 `=` 부호는 할당 연산자로 해석 되 고 오른쪽의 값을 왼쪽의 변수에 할당 합니다. 다음 예제에서는 이것을 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 자세한 내용은 [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) 및 [문](../../../../visual-basic/language-reference/statements/index.md)을 참조 하세요.  
  
## <a name="comparison-operators"></a>비교 연산자  
 `=`, `<`, `>`, `<>`, `<=`, `>=` 등의 비교 연산자는 연산자의 좌 변에 있는 식을 연산자의 오른쪽에 있는 식과 비교 하 고 결과를 `True` 또는 `False`으로 계산 하 여 부울 식을 생성 합니다. 다음 예제에서는 이것을 보여 줍니다.  
  
 `42 < 81`  
  
 42는 81 보다 작으므로 앞의 예제에서 부울 식은 `True`로 계산 됩니다. 이러한 식 종류에 대 한 자세한 내용은 [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)를 참조 하세요.  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>논리 연산자와 결합 된 비교 연산자  
 논리 연산자를 사용 하 여 비교 식을 결합 하 여 보다 복잡 한 부울 식을 생성할 수 있습니다. 다음 예에서는 비교 연산자를 논리 연산자와 함께 사용 하는 방법을 보여 줍니다.  
  
 `x > y And x < 1000`  
  
 앞의 예제에서 전체 식의 값은 `And` 연산자의 양쪽에 있는 식의 값에 따라 달라 집니다. 두 식이 모두 `True`되는 경우 전체 식이 `True`으로 평가 됩니다. 두 식 중 하나가 `False`되 면 전체 식이 `False`으로 평가 됩니다.  
  
## <a name="short-circuiting-operators"></a>단락 연산자  
 논리 연산자 `AndAlso` 및 `OrElse` *는 단락 이라는 동작을 나타냅니다.* 단락 연산자는 왼쪽 피연산자를 먼저 계산 합니다. 왼쪽 피연산자가 전체 식의 값을 결정 하는 경우 오른쪽 식을 계산 하지 않고 프로그램 실행이 진행 됩니다. 다음 예제에서는 이것을 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 앞의 예제에서 연산자는 왼쪽 식 `45 < 12`를 계산 합니다. 왼쪽 식이 `False`로 계산 되기 때문에 전체 논리 식은 `False`로 계산 되어야 합니다. 따라서 프로그램을 실행 하면 `testFunction(3)`오른쪽 식을 계산 하지 않고 `If` 블록 내에서 코드 실행을 건너뜁니다. 이 예에서는 왼쪽 식이 전체 식을 falsifies 때문에 `testFunction()`를 호출 하지 않습니다.  
  
 마찬가지로, `OrElse`를 사용 하는 논리 식의 왼쪽 식이 `True`로 계산 되 면 왼쪽 식의 유효성은 이미 전체 식의 유효성을 검사 했기 때문에 오른쪽 식을 계산 하지 않고 다음 코드 줄로 실행이 진행 됩니다.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>단락 이외의 연산자와 비교  
 이와 대조적으로 논리 연산자의 양쪽은 논리 연산자 `And` 및 `Or`를 사용할 때 계산 됩니다. 다음 예제에서는 이것을 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 앞의 예제에서는 왼쪽 식이 `False`로 평가 되는 경우에도 `testFunction()`를 호출 합니다.  
  
## <a name="parenthetical-expressions"></a>괄호 식  
 괄호를 사용 하 여 부울 식의 계산 순서를 제어할 수 있습니다. 괄호로 묶은 식이 먼저 계산 됩니다. 여러 중첩 수준에 대해 가장 많이 중첩 된 식에 우선 순위가 부여 됩니다. 괄호 안에 연산자 우선 순위 규칙에 따라 계산이 진행 됩니다. 자세한 내용은 [Visual Basic 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic 논리 및 비트 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [문](../../../../visual-basic/programming-guide/language-features/statements.md)
- [비교 연산자](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [연산자의 효율적 결합](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
