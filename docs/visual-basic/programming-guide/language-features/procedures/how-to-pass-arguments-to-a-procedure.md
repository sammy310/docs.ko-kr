---
description: '자세한 정보: 방법: 프로시저에 인수 전달 (Visual Basic)'
title: '방법: 프로시저에 인수 전달'
ms.date: 07/20/2015
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
ms.openlocfilehash: e4dcdac19699c4b4b1f88327034a9e9d4364f040
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434331"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>방법: 프로시저에 인수 전달(Visual Basic)

프로시저를 호출할 때 인수 목록이 있는 프로시저 이름을 괄호 안에 사용 합니다. 프로시저에서 정의 하는 모든 필수 매개 변수에 해당 하는 인수를 제공 하 고 선택적으로 매개 변수에 인수를 제공할 수 있습니다 `Optional` . 호출에 매개 변수를 제공 하지 않는 경우 `Optional` 후속 인수를 제공 하는 경우 인수 목록에 쉼표를 포함 하 여 해당 자리를 표시 해야 합니다.  
  
 와 같이 해당 매개 변수와 다른 데이터 형식의 인수를 전달 하려는 경우 `Byte` `String` 형식 확인 스위치 ([Option Strict 문](../../../language-reference/statements/option-strict-statement.md))를로 설정할 수 있습니다 `Off` . `Option Strict`가 이면 `On` 확대 변환 또는 명시적 변환 키워드 중 하나를 사용 해야 합니다. 자세한 내용은 [확대 및 축소 변환](../data-types/widening-and-narrowing-conversions.md) 및 [형식 변환 함수](../../../language-reference/functions/type-conversion-functions.md)를 참조 하세요.  
  
 자세한 내용은 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)를 참조 하세요.  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>프로시저에 하나 이상의 인수를 전달 하려면  
  
1. 호출 문에서 괄호를 사용 하 여 프로시저 이름을 따릅니다.  
  
2. 괄호 안에 인수 목록을 넣습니다. 프로시저에서 정의 하는 각 필수 매개 변수에 대 한 인수를 포함 하 고 인수를 쉼표로 구분 합니다.  
  
3. 각 인수가 해당 매개 변수에 대해 프로시저에서 정의 하는 형식으로 변환할 수 있는 데이터 형식으로 계산 되는 유효한 식 인지 확인 합니다.  
  
4. 매개 변수가 [선택적](../../../language-reference/modifiers/optional.md)으로 정의 된 경우 인수 목록에 포함 하거나 생략할 수 있습니다. 생략 하면 프로시저는 해당 매개 변수에 대해 정의 된 기본값을 사용 합니다.  
  
5. 매개 변수에 대 한 인수를 생략 하 고 매개 변수 `Optional` 목록에 다른 매개 변수가 있는 경우 인수 목록에서 생략 된 인수의 자리를 추가 쉼표로 표시할 수 있습니다.  
  
     다음 예에서는 Visual Basic 함수를 호출 합니다 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> .  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     앞의 예제에서는 표시 되는 메시지 문자열인 필수 첫 번째 인수를 제공 합니다. 메시지 상자에 표시할 단추를 지정 하는 선택적 두 번째 매개 변수에 대 한 인수를 생략 합니다. 호출에서 값을 제공 하지 않으므로는 `MsgBox` `MsgBoxStyle.OKOnly` **확인** 단추만 표시 하는 기본값인를 사용 합니다.  
  
     인수 목록에서 두 번째 쉼표는 생략 된 두 번째 인수의 자리를 표시 하 고 마지막 문자열은 `MsgBox` 제목 표시줄에 표시 되는 텍스트인의 선택적 세 번째 매개 변수로 전달 됩니다.  
  
## <a name="see-also"></a>추가 정보

- [하위 프로시저](./sub-procedures.md)
- [함수 프로시저](./function-procedures.md)
- [속성 프로시저](./property-procedures.md)
- [연산자 프로시저](./operator-procedures.md)
- [방법: 프로시저의 매개 변수 정의](./how-to-define-a-parameter-for-a-procedure.md)
- [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)
- [재귀 프로시저](./recursive-procedures.md)
- [프로시저 오버로딩](./procedure-overloading.md)
- [개체 및 클래스](../objects-and-classes/index.md)
- [개체 지향 프로그래밍(Visual Basic)](../../concepts/object-oriented-programming.md)
