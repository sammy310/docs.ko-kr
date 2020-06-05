---
title: '방법: 다른 프로시저에 프로시저 전달'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 36f623068372614ae034a8a7b31bffb7496f98b1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410697"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>방법: Visual Basic에서 프로시저에 다른 프로시저 전달
이 예제에서는 대리자를 사용 하 여 프로시저를 다른 프로시저에 전달 하는 방법을 보여 줍니다.  
  
 대리자는 Visual Basic의 다른 형식 처럼 사용할 수 있는 형식입니다. `AddressOf`연산자는 프로시저 이름에 적용 될 때 대리자 개체를 반환 합니다.  
  
 이 예제에는 연산자를 사용 하 여 얻은 다른 프로시저에 대 한 참조를 사용할 수 있는 대리자 매개 변수를 포함 하는 프로시저가 있습니다 `AddressOf` .  
  
### <a name="create-the-delegate-and-matching-procedures"></a>대리자 및 일치 프로시저 만들기  
  
1. 이라는 대리자를 만듭니다 `MathOperator` .  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. `AddNumbers`서명이 일치 하도록와 일치 하는 매개 변수 및 반환 값을 사용 하 여 라는 프로시저를 만듭니다 `MathOperator` .  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. `SubtractNumbers`와 일치 하는 서명을 사용 하 여 라는 이름의 프로시저를 만듭니다 `MathOperator` .  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. `DelegateTest`대리자를 매개 변수로 사용 하는 라는 프로시저를 만듭니다.  
  
     이 프로시저는 서명이 `AddNumbers` `SubtractNumbers` 시그니처와 일치 하기 때문에 또는에 대 한 참조를 수락할 수 있습니다 `MathOperator` .  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. 대리자를 매개 변수로 사용 하 여 한 `Test` 번 호출 하 `DelegateTest` `AddNumbers` 고에 대 한 대리자를 매개 변수로 사용 하 여를 한 번 호출 하는 라는 프로시저를 만듭니다 `SubtractNumbers` .  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     `Test`가 호출 되 면 먼저 `AddNumbers` 및에 대 한 작동 결과 `5` `3` (8)를 표시 합니다. 그런 다음 및에 대해 작동 하는 결과가 6 인 것으로 `SubtractNumbers` `9` `3` 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목

- [대리자](index.md)
- [AddressOf 연산자](../../../language-reference/operators/addressof-operator.md)
- [Delegate 문](../../../language-reference/statements/delegate-statement.md)
- [방법: 대리자 메서드 호출](how-to-invoke-a-delegate-method.md)
