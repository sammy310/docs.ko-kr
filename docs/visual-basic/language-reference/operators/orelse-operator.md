---
title: OrElse 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 28d1481b71979936bb16a2ecfb1140d85a674ef7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816397"
---
# <a name="orelse-operator-visual-basic"></a>OrElse 연산자(Visual Basic)
두 식에 포함 논리합을 단락 (short-circuiting)를 수행 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 임의의 `Boolean` 식입니다.  
  
 `expression1`  
 필수. 임의의 `Boolean` 식입니다.  
  
 `expression2`  
 필수. 임의의 `Boolean` 식입니다.  
  
## <a name="remarks"></a>설명  
 논리 연산 이라고 *단락 (short-circuiting)* 컴파일된 코드를 다른 식의 결과 따라 하나의 식의 평가 건너뛸 수 있는 경우. 작업의 최종 결과 결정 하는 계산 되는 첫 번째 식의 결과 경우 두 번째 식을 평가 하지 않아도 최종 결과 변경할 수 없습니다 때문입니다. 단락 (short-circuiting) 바이패스 된 식이 복잡 한 경우 또는 프로시저 호출이 포함 되는 경우 성능을 향상 시킬 수 있습니다.  
  
 식 중 하나 또는 둘 다로 평가 되 면 `True`, `result` 는 `True`합니다. 다음 표에서 설명 하는 방법을 `result` 결정 됩니다.  
  
|경우 `expression1` 됩니다|및 `expression2` 됩니다|변수의 `result` 는|  
|-------------------------|--------------------------|------------------------------|  
|`True`|(평가 되지 않음)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>데이터 형식  
 `OrElse` 연산자에 대해서만 정의 되는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)합니다. Visual Basic 변환 필요에 따라 각 피연산자 `Boolean` 완전히 작업을 수행 하 고 `Boolean`입니다. Visual Basic에서 변환 하는 숫자 형식으로 결과 할당 하는 경우 `Boolean` 해당 형식에 있습니다. 이 예기치 않은 동작이 발생할 수 있습니다. 예를 들어 `5 OrElse 12` 발생 `–1` 변환할 때 `Integer`합니다.  
  
## <a name="overloading"></a>오버로딩  
 [또는 연산자](../../../visual-basic/language-reference/operators/or-operator.md) 하며 [IsTrue 연산자](../../../visual-basic/language-reference/operators/istrue-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할 해당 동작에 해당 클래스의 형식 또는 구조입니다. 오버 로드는 `Or` 하 고 `IsTrue` 연산자의 동작에 영향을 줍니다는 `OrElse` 연산자입니다. 코드를 사용 하는 경우 `OrElse` 클래스 또는 구조체에 오버 로드에서 `Or` 및 `IsTrue`, 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `OrElse` 두 식에 논리 분리를 수행 하는 연산자입니다. 결과 `Boolean` 나타내는 두 식 중 하나가 true 인지 여부를 합니다. 첫 번째 식이 `True`, 두 번째는 평가 되지 않습니다.  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 이전 예제의 결과는 `True`하십시오 `True`, 및 `False` 각각. 계산에서 `firstCheck`, 첫 번째는 이미 이므로는 두 번째 식은 계산 되지 않습니다 `True`합니다. 그러나 두 번째 식 계산에서 계산 됩니다 `secondCheck`합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `If`... `Then` 두 프로시저 호출을 포함 하는 문이 있습니다. 첫 번째 호출에서 반환 하는 경우 `True`, 두 번째 절차는 호출 되지 않습니다. 두 번째 절차는 코드의이 섹션에서는 실행 될 때 항상 수행 해야 하는 중요 한 작업을 수행 하는 경우 예기치 않은 결과가 발생할 수 있습니다이 있습니다.  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a>참고자료

- [논리/비트 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Or 연산자](../../../visual-basic/language-reference/operators/or-operator.md)
- [IsTrue 연산자](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Visual Basic의 논리 및 비트 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
