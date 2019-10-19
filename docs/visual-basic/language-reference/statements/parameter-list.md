---
title: 매개 변수 목록(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: 0dded7fd68256b9b9de8ebe4b48073eb40696c12
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582175"
---
# <a name="parameter-list-visual-basic"></a>매개 변수 목록(Visual Basic)

프로시저를 호출할 때 프로시저에 필요한 매개 변수를 지정 합니다. 여러 매개 변수는 쉼표로 구분 됩니다. 다음은 하나의 매개 변수에 대 한 구문입니다.

## <a name="syntax"></a>구문

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a>요소

`attributelist`  
(선택 사항) 이 매개 변수에 적용 되는 특성의 목록입니다. [특성 목록을](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호 ("`<`" 및 "`>`")로 묶어야 합니다.

`Optional`  
(선택 사항) 프로시저를 호출할 때이 매개 변수가 필요 하지 않도록 지정 합니다.

`ByVal`  
(선택 사항) 프로시저에서 호출 코드의 해당 인수를 기반으로 하는 변수 요소를 바꾸거나 다시 할당할 수 없도록 지정 합니다.

`ByRef`  
(선택 사항) 호출 하는 코드와 같은 방식으로 프로시저에서 호출 코드의 기본 변수 요소를 수정할 수 있도록 지정 합니다.

`ParamArray`  
(선택 사항) 매개 변수 목록의 마지막 매개 변수가 지정 된 데이터 형식의 선택적 요소 배열 임을 지정 합니다. 이를 통해 호출 코드는 프로시저에 임의 개수의 인수를 전달할 수 있습니다.

`parametername`  
필수 요소. 매개 변수를 나타내는 지역 변수의 이름입니다.

`parametertype`  
@No__t_0 `On` 경우 필수입니다. 매개 변수를 나타내는 지역 변수의 데이터 형식입니다.

`defaultvalue`  
@No__t_0 매개 변수에 필요 합니다. 매개 변수의 데이터 형식으로 계산 되는 상수 또는 상수 식입니다. 형식이 `Object` 이거나 클래스, 인터페이스, 배열 또는 구조 이면 기본값은 `Nothing`만 가능 합니다.

## <a name="remarks"></a>주의

매개 변수는 괄호로 묶고 쉼표로 구분 됩니다. 모든 데이터 형식을 사용 하 여 매개 변수를 선언할 수 있습니다. @No__t_0 지정 하지 않으면 기본적으로 `Object`로 설정 됩니다.

호출 하는 코드는 프로시저를 호출할 때 각 필수 매개 변수에 *인수* 를 전달 합니다. 자세한 내용은 [매개 변수와 인수 간의 차이점](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)을 참조 하세요.

호출 코드에서 각 매개 변수에 전달 하는 인수는 호출 코드의 내부 요소에 대 한 포인터입니다. 이 요소가 *비가변* (상수, 리터럴, 열거형 또는 식) 인 경우 코드를 변경 하는 것은 불가능 합니다. *변수* 요소 (선언 된 변수, 필드, 속성, 배열 요소 또는 구조체 요소) 인 경우 호출 코드에서이를 변경할 수 있습니다. 자세한 내용은 [수정 가능 인수와 수정할 가능성이 없는 인수 간의 차이점](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)을 참조 하세요.

변수 요소가 `ByRef` 전달 되는 경우에도 프로시저에서 해당 요소를 변경할 수 있습니다. 자세한 내용은 [값으로 인수를 전달 하는 것과 참조로 인수를 전달 하는 차이점](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)을 참조 하세요.

## <a name="rules"></a>규칙

- **괄호.** 매개 변수 목록을 지정 하는 경우 괄호로 묶어야 합니다. 매개 변수가 없는 경우에도 빈 목록에 괄호를 사용할 수 있습니다. 이렇게 하면 요소가 프로시저 임을 명확 하 게 하 여 코드의 가독성을 향상 시킬 수 있습니다.

- **선택적 매개 변수입니다.** 매개 변수에 `Optional` 한정자를 사용 하는 경우 목록에 있는 모든 후속 매개 변수도 선택적 이어야 하 고 `Optional` 한정자를 사용 하 여 선언 해야 합니다.

     모든 선택적 매개 변수 선언은 `defaultvalue` 절을 제공 해야 합니다.

     자세한 내용은 [선택적 매개 변수](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)를 참조 하세요.

- **매개 변수 배열.** @No__t_1 매개 변수에 대 한 `ByVal` 지정 해야 합니다.

     동일한 매개 변수 목록에서 `Optional`와 `ParamArray`를 모두 사용할 수는 없습니다.

     자세한 내용은 [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)을 참조 하세요.

- **전달 메커니즘입니다.** 모든 인수에 대 한 기본 메커니즘은 `ByVal`입니다. 즉, 프로시저에서 기본 변수 요소를 변경할 수 없습니다. 그러나 요소가 참조 형식인 경우 프로시저는 개체 자체를 바꾸거나 재할당할 수 없더라도 기본 개체의 내용이 나 멤버를 수정할 수 있습니다.

- **매개 변수 이름.** 매개 변수의 데이터 형식이 배열인 경우에는 `parametername`를 즉시 괄호로 이동 합니다. 매개 변수 이름에 대 한 자세한 내용은 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예에서는 두 개의 매개 변수를 정의 하는 `Function` 프로시저를 보여 줍니다.

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a>참조

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
