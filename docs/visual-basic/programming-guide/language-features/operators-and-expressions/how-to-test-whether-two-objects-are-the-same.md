---
description: '자세한 정보: 방법: 두 개체가 동일한 지 여부 테스트 (Visual Basic)'
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
ms.openlocfilehash: a0136d9db487ad0ce70b9d55ff8ee014ec30b05a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435540"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>방법: 두 개체가 동일한지 테스트(Visual Basic)

개체를 참조 하는 두 개의 변수가 있는 경우 `Is` or `IsNot` 연산자 또는 둘 다를 사용 하 여 동일한 인스턴스를 참조 하는지 여부를 확인할 수 있습니다.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>두 개체가 동일한 지 여부를 테스트 하려면  
  
- 두 변수를 피연산자로 사용 하는 [Is 연산자](../../../language-reference/operators/is-operator.md) 또는 [IsNot 연산자](../../../language-reference/operators/isnot-operator.md) 를 사용 합니다.  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 두 개체가 같은 인스턴스를 참조 하는지 여부에 따라 특정 작업을 수행 하는 것이 좋습니다. 앞의 예제에서는 `c` 폼의 활성 컨트롤과 컨트롤을 비교 합니다 `f` . 활성 컨트롤이 없거나, 해당 컨트롤이 있지만와 동일한 컨트롤 인스턴스가 아닌 경우 `c` `If` 문이 실패 하 고 추가 처리 없이 프로시저가 반환 됩니다.  
  
 `Is`사용자가 또는를 사용 하는지에 `IsNot` 관계 없이 사용자가 개인적으로 편리 하 게 사용할 수 있습니다. 지정 된 식에서 다른 항목 보다 읽기가 더 쉬울 수 있습니다.  
  
## <a name="see-also"></a>추가 정보

- [Comparison Operators in Visual Basic](comparison-operators.md)
