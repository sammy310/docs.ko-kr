---
description: '자세히 알아보기: 방법: 두 개체가 동일한 지 확인 (Visual Basic)'
title: '방법: 두 개체가 동일한지 확인'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 91f431b5a7e4cf51135c060ca0aebf1b3b968b25
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481898"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>방법: 두 개체가 동일한지 확인(Visual Basic)

Visual Basic 두 변수가 동일한 경우 (즉, 두 변수가 메모리에서 동일한 클래스 인스턴스를 가리키는 경우) 두 변수 참조가 동일한 것으로 간주 됩니다. 예를 들어 Windows Forms 응용 프로그램에서는 현재 인스턴스 ( `Me` )가와 같은 특정 인스턴스와 동일한 지 여부를 확인 하기 위해 비교를 수행할 수 있습니다 `Form2` .  
  
 Visual Basic는 포인터를 비교 하는 두 개의 연산자를 제공 합니다. [Is 연산자](../../../language-reference/operators/is-operator.md) 는 `True` 개체가 동일 하면를 반환 하 고, [IsNot 연산자](../../../language-reference/operators/isnot-operator.md) 는 그렇지 않으면를 반환 합니다 `True` .  
  
## <a name="determining-if-two-objects-are-identical"></a>두 개체가 동일한 지 확인  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>두 개체가 동일한 지 확인 하려면  
  
1. `Boolean`두 개체를 테스트 하는 식을 설정 합니다.  
  
2. 테스트 식에서 `Is` 피연산자로 두 개의 개체를 사용 하 여 연산자를 사용 합니다.  
  
     `Is``True`개체가 동일한 클래스 인스턴스를 가리키면를 반환 합니다.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>두 개체가 동일 하지 않은 경우 확인  

 두 개체가 동일 하지 않을 경우 작업을 수행 하려는 경우와 예를 들어 및를 결합 하는 것이 어려울 수 있습니다 `Not` `Is` `If Not obj1 Is obj2` . 이 경우 연산자를 사용할 수 있습니다 `IsNot` .  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>두 개체가 동일한 지 확인 하려면  
  
1. `Boolean`두 개체를 테스트 하는 식을 설정 합니다.  
  
2. 테스트 식에서 `IsNot` 피연산자로 두 개의 개체를 사용 하 여 연산자를 사용 합니다.  
  
     `IsNot``True`개체가 동일한 클래스 인스턴스를 가리키지 않으면를 반환 합니다.  
  
## <a name="example"></a>예  

 다음 예제에서는 변수 쌍을 테스트 `Object` 하 여 동일한 클래스 인스턴스를 가리켜야 하는지 확인 합니다.  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 위의 예제는 다음과 같은 출력을 표시 합니다.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>추가 정보

- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [개체 변수](object-variables.md)
- [개체 변수 값](object-variable-values.md)
- [Is 연산자](../../../language-reference/operators/is-operator.md)
- [IsNot 연산자](../../../language-reference/operators/isnot-operator.md)
- [방법: 두 개체가 관련이 있는지 확인](how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase 및 MyClass](../../program-structure/me-my-mybase-and-myclass.md)
