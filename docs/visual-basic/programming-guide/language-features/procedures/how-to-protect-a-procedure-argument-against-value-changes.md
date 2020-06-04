---
title: '방법: 값 변경으로부터 프로시저 인수 보호'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
ms.openlocfilehash: b0504d9f7a8862274d5d71dc6a9c1570551629a5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414365"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>방법: 값 변경에 대해 프로시저 인수 보호(Visual Basic)
프로시저에서 매개 변수를 [ByRef](../../../language-reference/modifiers/byref.md)로 선언 하는 경우 Visual Basic은 호출 코드에서 인수를 기반으로 하는 프로그래밍 요소에 대 한 직접 참조를 프로시저 코드에 제공 합니다. 이렇게 하면 프로시저에서 호출 코드의 내부 인수 값을 변경할 수 있습니다. 경우에 따라 호출 코드가 이러한 변경을 방지 하는 것이 좋습니다.  
  
 프로시저에서 해당 하는 매개 변수 [ByVal](../../../language-reference/modifiers/byval.md) 을 선언 하 여 인수를 변경 으로부터 항상 보호할 수 있습니다. 일부 경우에는 지정 된 인수를 변경할 수 있지만 다른 경우에는 변경할 수 없는 경우에는 해당 인수를 선언 `ByRef` 하 고 호출 코드가 각 호출에서 전달 메커니즘을 결정 하도록 할 수 있습니다. 이를 위해 해당 인수를 괄호로 묶어 값으로 전달 하거나, 참조로 전달 하기 위해 괄호로 묶지 않습니다. 자세한 내용은 [방법: 인수를 값으로 전달](./how-to-force-an-argument-to-be-passed-by-value.md)하는 방법을 참조 하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 배열 변수를 사용 하 고 해당 요소에 대해 작동 하는 두 개의 프로시저를 보여 줍니다. `increase`프로시저는 각 요소에 하나씩만 추가 합니다. `replace`프로시저는 매개 변수에 새 배열을 할당 한 `a()` 다음 각 요소에 하나를 추가 합니다. 그러나 다시 할당 해도 호출 코드의 기본 배열 변수에는 영향을 주지 않습니다.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 첫 번째 `MsgBox` 호출은 "증가 (n): 11, 21, 31, 41"를 표시 합니다. 배열은 `n` 참조 형식 이므로는 `increase` 전달 메커니즘이 인 경우에도 해당 멤버를 변경할 수 있습니다 `ByVal` .  
  
 두 번째 `MsgBox` 호출은 "Replace After (n): 11, 21, 31, 41"를 표시 합니다. 가 전달 되기 때문에는 `n` `ByVal` `replace` `n` 새 배열을 할당 하 여 호출 코드에서 변수를 수정할 수 없습니다. 에서 `replace` 새 배열 인스턴스를 만들고 `k` 지역 변수에 할당 하면 `a` 호출 코드에서 전달 하는 참조가 손실 `n` 됩니다. 의 멤버를 변경 하면 `a` 로컬 배열에만 영향을 `k` 줍니다. 따라서은 `replace` 호출 코드에서 배열 값을 증가 `n` 시 지 않습니다.  
  
## <a name="compile-the-code"></a>코드 컴파일  
 Visual Basic의 기본값은 인수를 값으로 전달 하는 것입니다. 그러나 선언 된 모든 매개 변수와 함께 [ByVal](../../../language-reference/modifiers/byval.md) 또는 [ByRef](../../../language-reference/modifiers/byref.md) 키워드를 포함 하는 것이 좋은 프로그래밍 습관입니다. 이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [절차](./index.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)
- [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)
- [수정할 수 있는 인수와 수정할 수 없는 인수의 차이점](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [인수를 값으로 전달할 때와 참조로 전달할 때의 차이점](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [방법: 프로시저 인수의 값 변경](./how-to-change-the-value-of-a-procedure-argument.md)
- [방법: 인수가 값으로 전달되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)
- [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../data-types/value-types-and-reference-types.md)
