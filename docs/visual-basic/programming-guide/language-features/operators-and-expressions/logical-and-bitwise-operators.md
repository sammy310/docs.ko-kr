---
title: Visual Basic의 논리 및 비트 연산자
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: ac47b6d7fa4861d18646a23f442caccc4062852f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819309"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Visual Basic의 논리 및 비트 연산자
논리 연산자 비교 `Boolean` 식 및 반환 된 `Boolean` 결과입니다. 합니다 `And`, `Or`, `AndAlso`, `OrElse`, 및 `Xor` 연산자는 *이진* 하는 동안 두 개의 피연산자를 고려 하기 때문에 `Not` 연산자는 *단항* 단일 피연산자 걸리기 때문에 있습니다. 이러한 연산자 중 일부에 정수 계열 값의 비트 논리 연산을 수행할 수도 있습니다.  
  
## <a name="unary-logical-operator"></a>단항 논리 연산자  
 합니다 [Not 연산자](../../../../visual-basic/language-reference/operators/not-operator.md) 논리 수행 *부정* 에 `Boolean` 식입니다. 피연산자의 논리적 반대를 생성합니다. 식이 계산 되는 경우 `True`, 한 다음 `Not` 반환 `False`같으면 식의 결과가 `False`, 다음 `Not` 반환 `True`. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>이진 논리 연산자  
 합니다 [및 연산자](../../../../visual-basic/language-reference/operators/and-operator.md) 논리 수행 *함께* 두 `Boolean` 식입니다. 두 식이 모두로 평가 되 면 `True`, 한 다음 `And` 반환 `True`합니다. 로 평가 되 면 식 중 하나 이상이 `False`, 한 다음 `And` 반환 `False`합니다.  
  
 합니다 [또는 연산자](../../../../visual-basic/language-reference/operators/or-operator.md) 논리 수행 *분리* 또는 *포함* 두 `Boolean` 식입니다. 두 식 중 하나가 경우 `True`, 이거나 두 식이 `True`, 한 다음 `Or` 반환 `True`합니다. 두 식이 모두 하는 경우 `True`, `Or` 반환 `False`합니다.  
  
 합니다 [Xor 연산자](../../../../visual-basic/language-reference/operators/xor-operator.md) 논리 수행 *제외* 두 `Boolean` 식입니다. 정확히 하나의 식이 `True`, 하지만 둘 다는 아님 `Xor` 반환 `True`합니다. 두 식이 모두로 평가 되 면 `True` 이거나 두 식이 `False`를 `Xor` 반환 `False`합니다.  
  
 다음 예제는 `And`, `Or`, 및 `Xor` 연산자입니다.  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>논리 연산자를 단락 (short-circuiting)  
 [AndAlso 연산자](../../../../visual-basic/language-reference/operators/andalso-operator.md) 매우 비슷합니다는 `And` 연산자는 두 대 한 논리 결합을 수행 `Boolean` 식. 둘 사이의 주요 차이점은 `AndAlso` 보여 *단락 (short-circuiting)* 동작 합니다. 경우 첫 번째 식을 `AndAlso` 식이 `False`, 최종 결과 변경할 수 없습니다 때문에 두 번째 식은 평가 되지 됩니다 하 고 `AndAlso` 반환 `False`합니다.  
  
 마찬가지로, 합니다 [OrElse 연산자](../../../../visual-basic/language-reference/operators/orelse-operator.md) 두 논리 분리를 단락 (short-circuiting) 수행 `Boolean` 식입니다. 경우 첫 번째 식을 `OrElse` 식이 `True`, 최종 결과 변경할 수 없습니다 때문에 두 번째 식은 평가 되지 됩니다 하 고 `OrElse` 반환 `True`합니다.  
  
### <a name="short-circuiting-trade-offs"></a>장단점을 단락 (short-circuiting)  
 단락 (short-circuiting) 논리 작업의 결과 변경할 수 없는 식을 계산 하지 않아 성능을 향상 시킬 수 있습니다. 그러나 해당 식을 추가 작업을 수행 하는 경우 해당 작업을 건너뜁니다 단락 (short-circuiting). 예를 들어 식에 대 한 호출을 포함 하는 경우는 `Function` 프로시저, 식 대해서는 처리가 단축, 이며 추가 코드에 포함 하는 경우 프로시저 호출 되지 않습니다는 `Function` 실행 되지 않습니다. 따라서 함수는 가끔씩만 실행 될 수 있습니다 하 고 올바르게 테스트 되지 않을 수 있습니다. 프로그램 논리의 코드에 따라 달라질 수 있습니다 또는 `Function`합니다.  
  
 다음 예제에서는 차이점을 보여 줍니다 `And`, `Or`, 및 단락 대응 합니다.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 앞의 예제에서는 몇 가지 중요 한 코드 내에서 `checkIfValid()` 호출이 대해서는 처리가 단축 될 때 실행 되지 않습니다. 첫 번째 `If` 문 호출 `checkIfValid()` 하더라도 `12 > 45` 반환 `False`이므로 `And` 단락 (short-circuit) 하지 않습니다. 두 번째 `If` 호출 하지 않습니다 `checkIfValid()`이므로 때 `12 > 45` 반환 `False`, `AndAlso` 두 번째 식을 단락 (short-circuit). 세 번째 `If` 문 호출 `checkIfValid()` 하더라도 `12 < 45` 반환 `True`이므로 `Or` 단락 (short-circuit) 하지 않습니다. 네 번째 `If` 호출 하지 않습니다 `checkIfValid()`이므로 때 `12 < 45` 반환 `True`, `OrElse` 두 번째 식을 단락 (short-circuit).  
  
## <a name="bitwise-operations"></a>비트 연산  
 비트 연산의 이진 (밑 2) 형태로 두 정수 값을 평가합니다. 해당 위치의 비트를 비교 하 고 비교를 기반으로 하는 값을 할당 합니다. 다음 예제는 `And` 연산자입니다.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 값을 설정 하는 앞의 예제 `x` 1입니다. 다음과 같은 이유로 현상이 발생 합니다.  
  
-   값은 이진 형식으로 처리 됩니다.  
  
     이진 형식에서 3 011 =  
  
     이진 형식에서 5 101 =  
  
-   `And` 연산자는 한 번에 하나의 이진 위치 (비트)에서 이진 표현을 비교 합니다. 지정된 된 위치에 두 비트가 모두 1 이면 1 결과에 해당 위치에 배치 됩니다. 두 비트가 모두 0 인 경우 0은 결과에 해당 위치에 배치 됩니다. 앞의 예제에서이 같이 작동합니다.  
  
     011 (이진 형태로 3)  
  
     101 (이진 형식에서 5)  
  
     001 (이진 형식에서 결과)  
  
-   결과 10 진수로 처리 됩니다. 001 값은 1의 이진 표현 되므로 `x` = 1입니다.  
  
 비트 `Or` 비교 비트 중 하나 또는 모두 1 이면 결과 비트는 1이 할당 한다는 점을 제외 하면 작업은 유사 합니다. `Xor` 정확히 하나의 비교 비트 (둘 다)이 1 이면 결과 비트는 1을 할당 합니다. `Not` 단일 피연산자를 사용 하 고 비트를 부호를 포함 하 여 모든 비트를 반전 결과에 해당 값을 할당 합니다. 부호 있는 양수, 즉 `Not` 항상 음수 값을 반환 합니다 및 음수 `Not` 항상 양수 또는 0 값을 반환 합니다.  
  
 합니다 `AndAlso` 고 `OrElse` 연산자는 비트 연산을 지원 하지 않습니다.  
  
> [!NOTE]
>  비트 연산에서 정수 계열 형식 에서만 수행할 수 있습니다. 부동 소수점 값 비트 연산을 수행 하려면 먼저 정수 계열 형식으로 변환할 수 있어야 합니다.  
  
## <a name="see-also"></a>참고자료

- [논리/비트 연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [부울 식](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Visual Basic의 산술 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Visual Basic의 연결 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [연산자의 효율적 결합](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
