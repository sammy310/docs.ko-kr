---
title: '방법: 두 개체가 동일한지 확인'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 5deebd4ffc5b277c94f5ae36c00fd6e5010a1551
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348604"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>방법: 두 개체가 동일한지 확인(Visual Basic)
Visual Basic 두 변수가 동일한 경우 (즉, 두 변수가 메모리에서 동일한 클래스 인스턴스를 가리키는 경우) 두 변수 참조가 동일한 것으로 간주 됩니다. 예를 들어 Windows Forms 응용 프로그램에서 현재 인스턴스 (`Me`)가 `Form2`와 같은 특정 인스턴스와 동일한 지 여부를 확인 하기 위해 비교를 수행할 수 있습니다.  
  
 Visual Basic는 포인터를 비교 하는 두 개의 연산자를 제공 합니다. [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 는 개체가 동일 하면 `True`을 반환 하 고, [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md) 는 `True`를 반환 합니다 (없는 경우).  
  
## <a name="determining-if-two-objects-are-identical"></a>두 개체가 동일한 지 확인  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>두 개체가 동일한 지 확인 하려면  
  
1. 두 개체를 테스트 하는 `Boolean` 식을 설정 합니다.  
  
2. 테스트 식에서 두 개체를 피연산자로 사용 하 여 `Is` 연산자를 사용 합니다.  
  
     `Is`는 개체가 동일한 클래스 인스턴스를 가리키는 경우 `True`을 반환 합니다.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>두 개체가 동일 하지 않은 경우 확인  
 두 개체가 동일 하지 않을 경우 작업을 수행 하 고 `Not` 및 `Is`을 결합 하는 것이 어려울 수 있습니다 (예: `If Not obj1 Is obj2`). 이 경우 `IsNot` 연산자를 사용할 수 있습니다.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>두 개체가 동일한 지 확인 하려면  
  
1. 두 개체를 테스트 하는 `Boolean` 식을 설정 합니다.  
  
2. 테스트 식에서 두 개체를 피연산자로 사용 하 여 `IsNot` 연산자를 사용 합니다.  
  
     개체가 동일한 클래스 인스턴스를 가리키지 않는 경우 `IsNot` `True`를 반환 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Object` 변수의 쌍을 테스트 하 여 동일한 클래스 인스턴스를 가리켜야 하는지 확인 합니다.  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 위의 예제는 다음과 같은 출력을 표시 합니다.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>참고 항목

- [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [개체 변수 값](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [방법: 두 개체가 관련이 있는지 확인](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
