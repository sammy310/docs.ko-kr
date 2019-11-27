---
title: '방법: 두 개체가 동일한지 테스트'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 22e8e1e688d9e3bc3804899103ee78814aac235b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343627"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>방법: 두 개체가 동일한지 테스트(Visual Basic)
개체를 참조 하는 두 개의 변수가 있는 경우 `Is` 또는 `IsNot` 연산자 중 하나를 사용 하거나 둘 다를 사용 하 여 동일한 인스턴스를 참조 하는지 여부를 확인할 수 있습니다.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>두 개체가 동일한 지 여부를 테스트 하려면  
  
- 두 변수를 피연산자로 사용 하는 [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 또는 [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md) 를 사용 합니다.  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 두 개체가 같은 인스턴스를 참조 하는지 여부에 따라 특정 작업을 수행 하는 것이 좋습니다. 앞의 예제에서는 컨트롤 `c`를 폼 `f`의 활성 컨트롤과 비교 합니다. 활성 컨트롤이 없거나, 하나 있지만 `c`와 동일한 컨트롤 인스턴스가 아닌 경우에는 `If` 문이 실패 하 고 프로시저가 추가 처리 없이 반환 됩니다.  
  
 `Is` 또는 `IsNot`를 사용 하는 것은 개인적인 편의를 위해 사용 됩니다. 지정 된 식에서 다른 항목 보다 읽기가 더 쉬울 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
