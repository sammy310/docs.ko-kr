---
title: '방법: 인수가 값으로 전달되도록 설정'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 047738a2cbadc6b7d72f41aade22bbeff16d1bac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347604"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>방법: 인수가 값으로 전달되도록 설정(Visual Basic)
프로시저 선언은 전달 메커니즘을 결정 합니다. 매개 변수가 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)로 선언 된 경우 Visual Basic는 해당 인수를 참조로 전달 해야 합니다. 이렇게 하면 호출 코드에서 인수를 기반으로 하는 프로그래밍 요소의 값을 변경할 수 있습니다. 이러한 변경 으로부터 기본 요소를 보호 하려는 경우 인수 이름을 괄호로 묶으면 프로시저 호출에서 `ByRef` 전달 메커니즘을 재정의할 수 있습니다. 이러한 괄호는 호출에서 인수 목록을 묶는 괄호에 추가 됩니다.  
  
 호출 코드는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 메커니즘을 재정의할 수 없습니다.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>인수가 값으로 전달 되도록 하려면  
  
- 해당 매개 변수가 프로시저에서 `ByVal` 선언 된 경우 추가 단계를 수행할 필요가 없습니다. Visual Basic는 이미 인수를 값으로 전달할 것으로 예상 합니다.  
  
- 해당 매개 변수가 프로시저에서 `ByRef` 선언 되 면 프로시저 호출에서 인수를 괄호로 묶습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 `ByRef` 매개 변수 선언을 재정의 합니다. 강제로 `ByVal`하는 호출에서 두 가지 수준의 괄호를 확인 합니다.  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 `str` 인수 목록 내에서 추가 괄호 안에 포함 되 면 `setNewString` 프로시저는 호출 코드에서 해당 값을 변경할 수 없으며, "ByVal 전달 된 경우 바꿀 수 없음"이 표시 `MsgBox`. `str` 추가 괄호 안에 포함 되지 않은 경우 프로시저에서이를 변경 하 고 `MsgBox` "This is This is new value for inString argument"를 표시 합니다.  
  
## <a name="compile-the-code"></a>코드 컴파일  
 변수를 참조로 전달 하는 경우에는 `ByRef` 키워드를 사용 하 여이 메커니즘을 지정 해야 합니다.  
  
 Visual Basic의 기본값은 인수를 값으로 전달 하는 것입니다. 그러나 선언 된 모든 매개 변수와 함께 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드를 포함 하는 것이 좋은 프로그래밍 습관입니다. 이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 프로시저에서 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)매개 변수를 선언 하는 경우 코드의 올바른 실행은 호출 코드의 기본 요소를 변경할 수 있는지 여부에 따라 달라질 수 있습니다. 호출 코드가 인수를 괄호 안에 포함 하 여이 호출 메커니즘을 재정의 하거나 수정할 수 없는 인수를 전달 하는 경우 프로시저는 내부 요소를 변경할 수 없습니다. 이렇게 하면 호출 코드에서 예기치 않은 결과가 발생할 수 있습니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 프로시저에서 호출 코드의 인수를 기반으로 하는 값을 변경 하는 것이 항상 발생할 수 있는 위험이 있습니다. 이 값을 변경 하 고이 값을 사용 하기 전에 유효성 검사를 수행할 준비를 해야 합니다.  
  
## <a name="see-also"></a>참조

- [절차](./index.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)
- [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)
- [수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [인수를 값으로 전달할 때와 참조로 전달할 때의 차이점](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [방법: 프로시저 인수의 값 변경](./how-to-change-the-value-of-a-procedure-argument.md)
- [방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)
- [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
