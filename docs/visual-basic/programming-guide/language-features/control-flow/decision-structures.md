---
title: 판단 구조(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: 20b60fb425278dacb56ee5f888967554a1f76aeb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825380"
---
# <a name="decision-structures-visual-basic"></a>판단 구조(Visual Basic)
Visual Basic을 사용 하 여 조건을 테스트 하 고 해당 테스트의 결과 따라 다른 작업을 수행할 수 있습니다. True 또는 false 이면 식의 다양 한 값 또는 일련의 문 실행할 때 생성 되는 다양 한 예외에 대 한 조건을 테스트할 수 있습니다.  
  
 다음 그림에서는 조건이 true 인지 테스트 하 고 true 또는 false 인지에 따라 다른 작업을 수행 하는 의사 결정 구조를 보여 줍니다.  
  
 ![If의 순서도 중... 다음 중... 다른 생성](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
조건이 true 및 false 하는 경우 다른 작업을 수행 합니다.  
  
## <a name="ifthenelse-construction"></a>다음과 같은 경우... 다음 중... 다른 생성  
 `If...Then...Else` 생성을 사용 하 여 하나 이상의 조건을 테스트 하 고 각 조건에 따라 하나 이상의 문을 실행할 수 있습니다. 조건을 테스트 하 고 다음과 같은 방법으로 작업을 수행할 수 있습니다.  
  
-   조건이 인 경우 하나 이상의 문 실행 `True`  
  
-   조건이 인 경우 하나 이상의 문 실행 `False`  
  
-   조건이 인 경우 일부 문은 실행 `True` 와 다른 경우 `False`  
  
-   이전 조건이 인 경우 추가 조건을 테스트 합니다. `False`  
  
 이러한 모든 가능성을 제공 하는 제어 구조를 [경우... 다음 중... Else 문](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)합니다. 하나의 테스트 및 실행 하기 위한 하나의 문 있는 경우 줄 버전을 사용할 수 있습니다. 조건 및 작업의 더 복잡 한 집합에 있는 경우에 여러 행 버전을 사용할 수 있습니다.  
  
## <a name="selectcase-construction"></a>선택... 사례 생성  
 `Select...Case` 생성을 사용 하면 식을 한 번 계산 하 고 다양 한 다른 가능한 값을 기반으로 하는 문을 실행할 수 있습니다. 자세한 내용은 참조 하세요. [선택... Case 문](../../../../visual-basic/language-reference/statements/select-case-statement.md)합니다.  
  
## <a name="trycatchfinally-construction"></a>시도 중... Catch 하는 중... 마지막 생성  
 `Try...Catch...Finally` 구문을 사용 하 여 문 중 하나는 예외가 발생 하는 경우 제어를 유지 하는 환경에서 문 집합을 실행할 수 있습니다. 다른 예외에 대 한 다양 한 작업을 수행할 수 있습니다. 전체를 종료 하기 전에 실행 되는 코드 블록을 지정할 수도 있습니다 `Try...Catch...Finally` 어떤 일이 발생 하는 것에 관계 없이 생성 합니다. 자세한 내용은 [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.  
  
> [!NOTE]
>  많은 컨트롤 구조체에 대 한 키워드를 클릭 하면 모든 구조의 키워드 강조 표시 됩니다. 예를 들어 클릭 하면 `If` 에 `If...Then...Else` 생성, 모든 인스턴스의 `If`, `Then`, `ElseIf`, `Else`, 및 `End If` 생성에서의 강조 표시 됩니다. 다음 또는 이전 강조 표시 된 키워드를 이동 하려면 CTRL + SHIFT + 아래쪽 화살표 또는 CTRL + SHIFT + 위쪽 화살표를 누릅니다.  
  
## <a name="see-also"></a>참고자료

- [제어 흐름](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [기타 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [중첩 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [If 연산자](../../../../visual-basic/language-reference/operators/if-operator.md)
