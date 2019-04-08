---
title: -= 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: be1ff4f10f6b30d8448d2441ee3ad2c1e2f80e2d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815903"
---
# <a name="--operator-visual-basic"></a>-= 연산자(Visual Basic)
변수 또는 속성의 값에서 식의 값을 빼고 변수 또는 속성에 결과 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 필수 요소. 숫자 변수 또는 속성입니다.  
  
 `expression`  
 필수 요소. 임의의 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 왼쪽된에 있는 요소는 `-=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 수입니다. 변수 또는 속성 일 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.  
  
 `-=` 먼저 연산자는 변수 또는 속성 (연산자의 왼쪽)의 값에서 식 (연산자의 오른쪽에 있는) 값을 뺍니다. 연산자는 다음 변수 또는 속성에 해당 작업의 결과 할당합니다.  
  
## <a name="overloading"></a>오버로딩  
 합니다 [-연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 오버 로드 된 `-` 연산자의 동작에 영향을 줍니다는 `-=` 연산자입니다. 코드를 사용 하는 경우 `-=` 클래스나 구조체에 오버 로드에서 `-`, 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 합니다 `-=` 하나를 뺄 연산자 `Integer` 다른 변수 및 결과 두 번째 변수에 할당 합니다.  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>참고자료

- [-연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [문(C++)](../../../visual-basic/programming-guide/language-features/statements.md)
