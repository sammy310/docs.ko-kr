---
title: = 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: ad74e3ebc947af4f36022be838b69df6ce24997a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840291"
---
# <a name="-operator-visual-basic"></a>= 연산자(Visual Basic)
변수 또는 속성에 값을 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 모든 쓰기 가능한 변수 또는 속성입니다.  
  
 `value`  
 모든 리터럴, 상수 또는 식입니다.  
  
## <a name="remarks"></a>설명  
 등호의 왼쪽 요소 (`=`) 간단한 스칼라 변수, 속성 또는 배열의 요소 수입니다. 변수 또는 속성 일 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다. `=` 연산자 왼쪽의 속성 값 변수는 오른쪽에 할당 합니다.  
  
> [!NOTE]
>  `=` 연산자 비교 연산자로도 사용 됩니다. 자세한 내용은 참조 하세요 [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md)합니다.  
  
## <a name="overloading"></a>오버로딩  
 `=` 대입 연산자가 아니라 관계 비교 연산자로 연산자를 오버 로드 될 수 있습니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 대입 연산자를 보여 줍니다. 오른쪽 값을 왼쪽에 있는 변수에 할당 됩니다.  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>참고자료

- [&= 연산자](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [*= 연산자](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [+= 연산자](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [-= 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [/ = 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [\\= 연산자](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [^= 연산자](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [문(C++)](../../../visual-basic/programming-guide/language-features/statements.md)
- [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
