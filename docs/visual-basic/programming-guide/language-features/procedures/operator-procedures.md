---
description: '자세한 정보: 연산자 프로시저 (Visual Basic)'
title: 연산자 프로시저
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: 836eeb2e705a96c49b5fa53e277ccf025d1915b2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100479961"
---
# <a name="operator-procedures-visual-basic"></a>연산자 프로시저(Visual Basic)

연산자 프로시저는 `*` `<>` `And` 사용자가 정의한 클래스 또는 구조체에서 표준 연산자 (예:, 또는)의 동작을 정의 하는 일련의 Visual Basic 문입니다. 이를 *연산자 오버 로드* 라고도 합니다.

## <a name="when-to-define-operator-procedures"></a>연산자 프로시저를 정의 하는 경우

클래스 또는 구조체를 정의한 경우 해당 클래스 또는 구조체의 형식으로 변수를 선언할 수 있습니다. 때로는 이러한 변수가 식의 일부로 작업에 참여 해야 하는 경우가 있습니다. 이렇게 하려면 연산자의 피연산자 여야 합니다.

Visual Basic은 기본 데이터 형식에 대해서만 연산자를 정의 합니다. 피연산자 중 하나 또는 둘 다가 클래스 또는 구조체의 형식인 경우 연산자의 동작을 정의할 수 있습니다.

자세한 내용은 [Operator 문](../../../language-reference/statements/operator-statement.md)을 참조 하세요.

## <a name="types-of-operator-procedure"></a>연산자 프로시저 유형

연산자 프로시저는 다음 형식 중 하나일 수 있습니다.

- 인수가 클래스 또는 구조체의 형식인 단항 연산자의 정의입니다.

- 하나 이상의 인수가 클래스 또는 구조체의 형식인 이항 연산자의 정의입니다.

- 인수가 클래스 또는 구조체의 형식인 변환 연산자의 정의입니다.

- 클래스 또는 구조체의 형식을 반환 하는 변환 연산자의 정의입니다.

 변환 연산자는 항상 단항 이며, 정의 하는 연산자로 항상를 사용 `CType` 합니다.

## <a name="declaration-syntax"></a>선언 구문

연산자 프로시저를 선언 하는 구문은 다음과 같습니다.

```vb
Public Shared [Widening | Narrowing] Operator operatorsymbol ( operand1 [,  operand2 ]) As datatype

' Statements of the operator procedure.

End Operator
```

`Widening` `Narrowing` 형식 변환 연산자에 대해서만 또는 키워드를 사용 합니다. 연산자 기호는 형식 변환 연산자에 대해 항상 [CType 함수](../../../language-reference/functions/ctype-function.md) 입니다.

이항 연산자를 정의 하는 두 개의 피연산자를 선언 하 고, 형식 변환 연산자를 포함 하 여 단항 연산자를 정의 하는 피연산자 하나를 선언 합니다. 모든 피연산자를 선언 해야 합니다 `ByVal` .

[Sub 프로시저](./sub-procedures.md)에 대 한 매개 변수를 선언 하는 것과 동일한 방식으로 각 피연산자를 선언 합니다.

### <a name="data-type"></a>데이터 형식

정의한 클래스 또는 구조체에서 연산자를 정의 하기 때문에 하나 이상의 피연산자는 해당 클래스 또는 구조체의 데이터 형식 이어야 합니다. 형식 변환 연산자의 경우 피연산자 또는 반환 형식이 클래스 또는 구조체의 데이터 형식 이어야 합니다.

자세한 내용은 [Operator 문](../../../language-reference/statements/operator-statement.md)을 참조 하세요.

## <a name="calling-syntax"></a>호출 구문

식에서 연산자 기호를 사용 하 여 연산자 프로시저를 암시적으로 호출 합니다. 미리 정의 된 연산자에 대해 수행 하는 것과 동일한 방식으로 피연산자를 제공 합니다.

연산자 프로시저에 대 한 암시적 호출 구문은 다음과 같습니다.

`Dim testStruct As`  *structurename*

`Dim testNewStruct As`  *structurename* `= testStruct` *operatorsymbol*      `10`

### <a name="illustration-of-declaration-and-call"></a>선언 및 호출에 대 한 그림

다음 구조체는 부호 있는 128 비트 정수 값을 구성 된 상위 및 하위 부분으로 저장 합니다. `+`두 값을 추가 하 `veryLong` 고 결과 값을 생성 하는 연산자를 정의 `veryLong` 합니다.

[!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]

다음 예에서는에 정의 된 연산자에 대 한 일반적인 호출을 보여 줍니다 `+` `veryLong` .

[!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]

## <a name="see-also"></a>추가 정보

- [절차](./index.md)
- [하위 프로시저](./sub-procedures.md)
- [함수 프로시저](./function-procedures.md)
- [속성 프로시저](./property-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [방법: 연산자 정의](./how-to-define-an-operator.md)
- [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md)
- [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md)
- [방법: 연산자를 정의하는 클래스 사용](./how-to-use-a-class-that-defines-operators.md)
