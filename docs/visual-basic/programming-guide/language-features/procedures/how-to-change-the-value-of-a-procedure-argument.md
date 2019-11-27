---
title: '방법: 프로시저 인수의 값 변경'
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
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: e562c0f5ec01380c792b4dc064554171cfb007e7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74339952"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>방법: 프로시저 인수의 값 변경(Visual Basic)
프로시저를 호출할 때 사용자가 제공 하는 각 인수는 프로시저에 정의 된 매개 변수 중 하나에 해당 합니다. 경우에 따라 프로시저 코드는 호출 코드에서 인수의 내부 값을 변경할 수 있습니다. 다른 경우에는 프로시저에서 인수의 로컬 복사본만 변경할 수 있습니다.  
  
 프로시저를 호출 하면 Visual Basic는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)로 전달 되는 모든 인수의 로컬 복사본을 만듭니다. [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)를 전달 하는 각 인수에 대해 Visual Basic은 호출 코드에서 인수를 기본으로 하는 프로그래밍 요소에 대 한 직접 참조를 프로시저 코드에 제공 합니다.  
  
 호출 하는 코드의 기본 요소가 수정 가능한 요소이 고 인수가 `ByRef`전달 되 면 프로시저 코드는 직접 참조를 사용 하 여 호출 코드에서 요소의 값을 변경할 수 있습니다.  
  
## <a name="changing-the-underlying-value"></a>내부 값 변경  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>호출 코드에서 프로시저 인수의 내부 값을 변경 하려면  
  
1. 프로시저 선언에서 인수에 해당 하는 매개 변수에 대해 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 를 지정 합니다.  
  
2. 호출 코드에서 수정 가능한 프로그래밍 요소를 인수로 전달 합니다.  
  
3. 호출 코드에서 인수를 인수 목록에 괄호로 묶지 마십시오.  
  
4. 프로시저 코드에서 매개 변수 이름을 사용 하 여 호출 코드의 기본 요소에 값을 할당 합니다.  
  
 데모를 보려면 아래 예제를 참조 하세요.  
  
## <a name="changing-local-copies"></a>로컬 복사본 변경  
 호출 코드의 내부 요소가 수정할 수 없는 요소 이거나 인수가 `ByVal`전달 되는 경우 프로시저는 호출 코드에서 해당 값을 변경할 수 없습니다. 그러나 프로시저는 이러한 인수의 로컬 복사본을 변경할 수 있습니다.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>프로시저 코드에서 프로시저 인수의 복사본을 변경 하려면  
  
1. 프로시저 선언에서 인수에 해당 하는 매개 변수에 대해 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 을 지정 합니다.  
  
     -또는-  
  
     호출 코드에서 인수를 인수 목록에 괄호로 묶습니다. 이렇게 하면 해당 매개 변수가 `ByRef`를 지정 하는 경우에도 Visual Basic는 값으로 인수를 전달 합니다.  
  
2. 프로시저 코드에서 매개 변수 이름을 사용 하 여 인수의 로컬 복사본에 값을 할당 합니다. 호출 코드의 내부 값은 변경 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 배열 변수를 사용 하 고 해당 요소에 대해 작동 하는 두 개의 프로시저를 보여 줍니다. `increase` 프로시저는 각 요소에 하나씩만 추가 합니다. `replace` 프로시저 `a()` 매개 변수에 새 배열을 할당 한 다음 각 요소에 요소 하나를 추가 합니다.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 첫 번째 `MsgBox` 호출은 "증가 (n): 11, 21, 31, 41"를 표시 합니다. 배열 `n`는 참조 형식이 기 때문에 전달 메커니즘이 `ByVal`되더라도 `replace` 멤버를 변경할 수 있습니다.  
  
 두 번째 `MsgBox` 호출은 "replace After (n): 101, 201, 301"를 표시 합니다. `n` `ByRef`전달 되기 때문에 호출 코드에서 변수 `n`를 수정 하 고이 변수에 새 배열을 할당할 수 `replace`. `n`는 참조 형식이 기 때문에 `replace` 멤버를 변경할 수도 있습니다.  
  
 프로시저에서 호출 코드의 변수 자체를 수정 하는 것을 방지할 수 있습니다. [방법: 값 변경에 대해 프로시저 인수 보호를](./how-to-protect-a-procedure-argument-against-value-changes.md)참조 하세요.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 변수를 참조로 전달 하는 경우에는 `ByRef` 키워드를 사용 하 여이 메커니즘을 지정 해야 합니다.  
  
 Visual Basic의 기본값은 인수를 값으로 전달 하는 것입니다. 그러나 선언 된 모든 매개 변수와 함께 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드를 포함 하는 것이 좋은 프로그래밍 습관입니다. 이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 프로시저에서 호출 코드의 인수를 기반으로 하는 값을 변경 하는 것이 항상 발생할 수 있는 위험이 있습니다. 이 값을 변경 하 고이 값을 사용 하기 전에 유효성 검사를 수행할 준비를 해야 합니다.  
  
## <a name="see-also"></a>참고 항목

- [절차](./index.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)
- [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)
- [수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [인수를 값으로 전달할 때와 참조로 전달할 때의 차이점](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [방법: 인수가 값으로 전달되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)
- [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
