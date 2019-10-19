---
title: Operator 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: c4fae40992fa665121aff637ae427ef0cafbf547
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582378"
---
# <a name="operator-statement"></a>Operator Statement

클래스 또는 구조체에서 연산자 프로시저를 정의 하는 연산자 기호, 피연산자 및 코드를 선언 합니다.

## <a name="syntax"></a>구문

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a>요소

`attrlist`  
(선택 사항) [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조 하십시오.

`Public`  
필수 요소. 이 연산자 프로시저에 [공용](../../../visual-basic/language-reference/modifiers/public.md) 액세스 권한이 있음을 나타냅니다.

`Overloads`  
(선택 사항) [오버 로드](../../../visual-basic/language-reference/modifiers/overloads.md)를 참조 하세요.

`Shared`  
필수 요소. 이 연산자 프로시저가 [공유](../../../visual-basic/language-reference/modifiers/shared.md) 프로시저 임을 나타냅니다.

`Shadows`  
(선택 사항) [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)를 참조 하세요.

`Widening`  
@No__t_0를 지정 하지 않는 한 변환 연산자에 필요 합니다. 이 연산자 프로시저가 [확대](../../../visual-basic/language-reference/modifiers/widening.md) 변환을 정의 함을 나타냅니다. 이 도움말 페이지의 "확대 및 축소 변환"을 참조 하십시오.

`Narrowing`  
@No__t_0를 지정 하지 않는 한 변환 연산자에 필요 합니다. 이 연산자 프로시저가 [축소](../../../visual-basic/language-reference/modifiers/narrowing.md) 변환을 정의 함을 나타냅니다. 이 도움말 페이지의 "확대 및 축소 변환"을 참조 하십시오.

`operatorsymbol`  
필수 요소. 이 연산자 프로시저가 정의 하는 연산자의 기호 또는 식별자입니다.

`operand1`  
필수 요소. 단항 연산자의 단일 피연산자 이름 및 형식 (변환 연산자 포함) 또는 이항 연산자의 왼쪽 피연산자입니다.

`operand2`  
이항 연산자에 필요 합니다. 이항 연산자 오른쪽 피연산자의 이름과 형식입니다.

`operand1` 및 `operand2`에는 다음과 같은 구문과 부분이 있습니다.

`[ ByVal ] operandname [ As operandtype ]`

|파트|설명|
|----------|-----------------|
|`ByVal`|선택 사항 이지만 전달 메커니즘이 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)이어야 합니다.|
|`operandname`|필수 요소. 이 피연산자를 나타내는 변수의 이름입니다. [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.|
|`operandtype`|@No__t_0 `On` 하지 않는 한 선택 사항입니다. 이 피연산자의 데이터 형식입니다.|

`type`  
@No__t_0 `On` 하지 않는 한 선택 사항입니다. 연산자 프로시저에서 반환 하는 값의 데이터 형식입니다.

`statements`  
(선택 사항) 연산자 프로시저에서 실행 하는 문 블록입니다.

`returnvalue`  
필수 요소. 연산자 프로시저가 호출 코드에 반환 하는 값입니다.

`End` `Operator`  
필수 요소. 이 연산자 프로시저의 정의를 종료 합니다.

## <a name="remarks"></a>주의

클래스 또는 구조체 에서만 `Operator`를 사용할 수 있습니다. 즉, 연산자의 *선언 컨텍스트* 는 소스 파일, 네임 스페이스, 모듈, 인터페이스, 프로시저 또는 블록이 될 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.

모든 연산자는 `Public Shared` 해야 합니다. 두 피연산자 중 하나에 대해 `ByRef`, `Optional` 또는 `ParamArray`를 지정할 수 없습니다.

연산자 기호 또는 식별자를 사용 하 여 반환 값을 저장할 수 없습니다. @No__t_0 문을 사용 해야 하 고 값을 지정 해야 합니다. 프로시저의 아무 곳에 나 원하는 수의 `Return` 문이 표시 될 수 있습니다.

이러한 방식으로 연산자를 정의 하는 것은 `Overloads` 키워드를 사용 하는지 여부에 관계 없이 *연산자 오버 로드*라고 합니다. 다음 표에는 정의할 수 있는 연산자가 나와 있습니다.

|Type|연산자|
|----------|---------------|
|단항|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|이항|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|변환(단항)|`CType`|

이진 목록의 `=` 연산자는 대입 연산자가 아닌 비교 연산자입니다.

@No__t_0를 정의 하는 경우 `Widening` 또는 `Narrowing`를 지정 해야 합니다.

## <a name="matched-pairs"></a>짝이 되는 쌍

특정 연산자를 일치 하는 쌍으로 정의 해야 합니다. 이러한 쌍의 연산자 중 하나를 정의 하는 경우 다른 연산자도 정의 해야 합니다. 일치 하는 쌍은 다음과 같습니다.

- `=` 및 `<>`

- `>` 및 `<`

- `>=` 및 `<=`

- `IsTrue` 및 `IsFalse`

## <a name="data-type-restrictions"></a>데이터 형식 제한 사항

정의 하는 모든 연산자는 정의 하는 클래스 또는 구조체를 포함 해야 합니다. 즉, 클래스 또는 구조체는 다음의 데이터 형식으로 나타나야 합니다.

- 단항 연산자의 피연산자입니다.

- 이항 연산자의 피연산자 중 하나 이상입니다.

- 변환 연산자의 피연산자 또는 반환 형식입니다.

 특정 연산자에는 다음과 같은 추가 데이터 형식 제한이 있습니다.

- @No__t_0 및 `IsFalse` 연산자를 정의 하는 경우 둘 다 `Boolean` 형식을 반환 해야 합니다.

- @No__t_0 및 `>>` 연산자를 정의 하는 경우 `operand2` `operandtype`에 대 한 `Integer` 형식을 지정 해야 합니다.

반환 형식은 두 피연산자의 형식에 해당 하지 않아도 됩니다. 예를 들어 `=` 또는 `<>` 같은 비교 연산자는 두 피연산자가 모두 `Boolean` 되지 않은 경우에도 `Boolean`를 반환할 수 있습니다.

## <a name="logical-and-bitwise-operators"></a>논리 및 비트 연산자

@No__t_0, `Or`, `Not` 및 `Xor` 연산자는 Visual Basic에서 논리적 or 비트 연산을 수행할 수 있습니다. 그러나 클래스 또는 구조체에서 이러한 연산자 중 하나를 정의 하는 경우에는 비트 연산을 정의할 수 있습니다.

@No__t_0 연산자는 `Operator` 문으로 직접 정의할 수 없습니다. 그러나 다음 조건을 충족 하는 경우 `AndAlso`를 사용할 수 있습니다.

- @No__t_1에 사용 하려는 것과 동일한 피연산자 유형에 `And`를 정의 했습니다.

- @No__t_0 정의는 사용자가 정의한 클래스 또는 구조체와 동일한 형식을 반환 합니다.

- @No__t_1를 정의한 클래스 또는 구조체에 `IsFalse` 연산자를 정의 했습니다.

마찬가지로, 클래스 또는 구조체의 반환 형식을 사용 하 여 동일한 피연산자에 `Or`을 정의 하 고 클래스 또는 구조체에 `IsTrue`를 정의한 경우 `OrElse`를 사용할 수 있습니다.

## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions

*확대 변환은* 런타임에 항상 성공 하지만 *축소 변환은* 런타임에 실패할 수 있습니다. 자세한 내용은 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.

@No__t_0 변환 프로시저를 선언 하는 경우 프로시저 코드에서 오류를 생성 해서는 안 됩니다. 이것은 다음을 의미합니다.

- 항상 `type` 형식의 유효한 값을 반환 해야 합니다.

- 가능한 모든 예외 및 기타 오류 조건을 처리 해야 합니다.

- 호출 하는 프로시저에서 반환 되는 모든 오류를 처리 해야 합니다.

변환 프로시저가 성공 하지 못할 수 있거나 처리 되지 않은 예외가 발생할 수 있는 경우 `Narrowing` 되도록 선언 해야 합니다.

## <a name="example"></a>예제

다음 코드 예에서는 `Operator` 문을 사용 하 여 `And`, `Or`, `IsFalse` 및 `IsTrue` 연산자에 대 한 연산자 프로시저를 포함 하는 구조체의 개요를 정의 합니다. `And` 및 `Or`는 각각 `abc` 형식의 두 피연산자를 사용 하 고 `abc` 형식을 반환 합니다. `IsFalse` 및 `IsTrue`는 `abc` 형식의 단일 피연산자를 사용 하 고 `Boolean`를 반환 합니다. 이러한 정의를 통해 호출 코드는 `abc` 형식의 피연산자를 사용 하 여 `And`, `AndAlso`, `Or` 및 `OrElse`를 사용할 수 있습니다.

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a>참조

- [IsFalse 연산자](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [IsTrue 연산자](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [확장](../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [방법: 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [방법: 변환 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [방법: 연산자 프로시저 호출](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [방법: 연산자를 정의하는 클래스 사용](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
