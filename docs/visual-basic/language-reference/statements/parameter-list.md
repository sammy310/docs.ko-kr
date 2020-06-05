---
title: 매개 변수 목록
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
ms.openlocfilehash: 706fc2414806db5608cce410bf4156839ec2d83e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404319"
---
# <a name="parameter-list-visual-basic"></a>매개 변수 목록(Visual Basic)

프로시저를 호출할 때 프로시저에 필요한 매개 변수를 지정 합니다. 여러 매개 변수는 쉼표로 구분 됩니다. 다음은 하나의 매개 변수에 대 한 구문입니다.

## <a name="syntax"></a>구문

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a>부분

`attributelist`  
선택 사항입니다. 이 매개 변수에 적용 되는 특성의 목록입니다. [특성 목록을](attribute-list.md) 꺾쇠 괄호 (" `<` " 및 "")로 묶어야 합니다 `>` .

`Optional`  
선택 사항입니다. 프로시저를 호출할 때이 매개 변수가 필요 하지 않도록 지정 합니다.

`ByVal`  
선택 사항입니다. 프로시저에서 호출 코드의 해당 인수를 기반으로 하는 변수 요소를 바꾸거나 다시 할당할 수 없도록 지정 합니다.

`ByRef`  
선택 사항입니다. 호출 하는 코드와 같은 방식으로 프로시저에서 호출 코드의 기본 변수 요소를 수정할 수 있도록 지정 합니다.

`ParamArray`  
선택 사항입니다. 매개 변수 목록의 마지막 매개 변수가 지정 된 데이터 형식의 선택적 요소 배열 임을 지정 합니다. 이를 통해 호출 코드는 프로시저에 임의 개수의 인수를 전달할 수 있습니다.

`parametername`  
필수 요소. 매개 변수를 나타내는 지역 변수의 이름입니다.

`parametertype`  
필요한 경우 `Option Strict` 는 `On`합니다. 매개 변수를 나타내는 지역 변수의 데이터 형식입니다.

`defaultvalue`  
`Optional`매개 변수에 필요 합니다. 매개 변수의 데이터 형식으로 계산 되는 상수 또는 상수 식입니다. 형식이 `Object` 나 클래스, 인터페이스, 배열 또는 구조 이면 기본값은 일 수만 있습니다 `Nothing` .

## <a name="remarks"></a>설명

매개 변수는 괄호로 묶고 쉼표로 구분 됩니다. 모든 데이터 형식을 사용 하 여 매개 변수를 선언할 수 있습니다. 을 지정 하지 않으면 기본적 `parametertype` 으로로 설정 `Object` 됩니다.

호출 하는 코드는 프로시저를 호출할 때 각 필수 매개 변수에 *인수* 를 전달 합니다. 자세한 내용은 [매개 변수와 인수 간의 차이점](../../programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)을 참조 하세요.

호출 코드에서 각 매개 변수에 전달 하는 인수는 호출 코드의 내부 요소에 대 한 포인터입니다. 이 요소가 *비가변* (상수, 리터럴, 열거형 또는 식) 인 경우 코드를 변경 하는 것은 불가능 합니다. *변수* 요소 (선언 된 변수, 필드, 속성, 배열 요소 또는 구조체 요소) 인 경우 호출 코드에서이를 변경할 수 있습니다. 자세한 내용은 [수정 가능 인수와 수정할 가능성이 없는 인수 간의 차이점](../../programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)을 참조 하세요.

변수 요소가 전달 되는 경우에 `ByRef` 도 프로시저에서 변경할 수 있습니다. 자세한 내용은 [값으로 인수를 전달 하는 것과 참조로 인수를 전달 하는 차이점](../../programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)을 참조 하세요.

## <a name="rules"></a>규칙

- **괄호.** 매개 변수 목록을 지정 하는 경우 괄호로 묶어야 합니다. 매개 변수가 없는 경우에도 빈 목록에 괄호를 사용할 수 있습니다. 이렇게 하면 요소가 프로시저 임을 명확 하 게 하 여 코드의 가독성을 향상 시킬 수 있습니다.

- **선택적 매개 변수입니다.** 매개 변수에 한정자를 사용 하는 경우 `Optional` 목록에 있는 모든 후속 매개 변수도 선택적 이어야 하며 한정자를 사용 하 여 선언 해야 합니다 `Optional` .

     모든 선택적 매개 변수 선언에서 절을 제공 해야 합니다 `defaultvalue` .

     자세한 내용은 [선택적 매개 변수](../../programming-guide/language-features/procedures/optional-parameters.md)를 참조 하세요.

- **매개 변수 배열.** `ByVal`매개 변수의 경우를 지정 해야 `ParamArray` 합니다.

     `Optional` `ParamArray` 동일한 매개 변수 목록에서 및를 모두 사용할 수는 없습니다.

     자세한 내용은 [매개 변수 배열](../../programming-guide/language-features/procedures/parameter-arrays.md)을 참조 하세요.

- **전달 메커니즘입니다.** 모든 인수에 대 한 기본 메커니즘은 이며 `ByVal` 프로시저에서 기본 변수 요소를 변경할 수 없음을 의미 합니다. 그러나 요소가 참조 형식인 경우 프로시저는 개체 자체를 바꾸거나 재할당할 수 없더라도 기본 개체의 내용이 나 멤버를 수정할 수 있습니다.

- **매개 변수 이름.** 매개 변수의 데이터 형식이 배열인 경우 괄호를 따라 즉시 수행 `parametername` 합니다. 매개 변수 이름에 대 한 자세한 내용은 [선언 된 요소 이름](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예에서는 `Function` 두 개의 매개 변수를 정의 하는 프로시저를 보여 줍니다.

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Function 문](function-statement.md)
- [Sub 문](sub-statement.md)
- [Declare 문](declare-statement.md)
- [Structure 문](structure-statement.md)
- [Option Strict 문](option-strict-statement.md)
- [특성 개요](../../programming-guide/concepts/attributes/index.md)
- [방법: 코드에서 명령문 분리 및 결합](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
