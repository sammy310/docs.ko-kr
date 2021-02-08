---
description: '다음에 대 한 자세한 정보: Operator 문'
title: Operator Statement
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
ms.openlocfilehash: f6a8ae2ac51e8bc8fe1be0de3549004b9dda4ef4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768820"
---
# <a name="operator-statement"></a>Operator Statement

클래스 또는 구조체에서 연산자 프로시저를 정의 하는 연산자 기호, 피연산자 및 코드를 선언 합니다.

## <a name="syntax"></a>Syntax

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a>부분

`attrlist`  
선택 사항입니다. [특성 목록](attribute-list.md)을 참조 하십시오.

`Public`  
필수 사항입니다. 이 연산자 프로시저에 [공용](../modifiers/public.md) 액세스 권한이 있음을 나타냅니다.

`Overloads`  
선택 사항입니다. [오버 로드](../modifiers/overloads.md)를 참조 하세요.

`Shared`  
필수 사항입니다. 이 연산자 프로시저가 [공유](../modifiers/shared.md) 프로시저 임을 나타냅니다.

`Shadows`  
선택 사항입니다. [그림자](../modifiers/shadows.md)를 참조 하세요.

`Widening`  
을 지정 하지 않는 한 변환 연산자에 필요 `Narrowing` 합니다. 이 연산자 프로시저가 [확대](../modifiers/widening.md) 변환을 정의 함을 나타냅니다. 이 도움말 페이지의 "확대 및 축소 변환"을 참조 하십시오.

`Narrowing`  
을 지정 하지 않는 한 변환 연산자에 필요 `Widening` 합니다. 이 연산자 프로시저가 [축소](../modifiers/narrowing.md) 변환을 정의 함을 나타냅니다. 이 도움말 페이지의 "확대 및 축소 변환"을 참조 하십시오.

`operatorsymbol`  
필수 사항입니다. 이 연산자 프로시저가 정의 하는 연산자의 기호 또는 식별자입니다.

`operand1`  
필수 사항입니다. 단항 연산자의 단일 피연산자 이름 및 형식 (변환 연산자 포함) 또는 이항 연산자의 왼쪽 피연산자입니다.

`operand2`  
이항 연산자에 필요 합니다. 이항 연산자 오른쪽 피연산자의 이름과 형식입니다.

`operand1` 및에 `operand2` 는 다음과 같은 구문과 부분이 있습니다.

`[ ByVal ] operandname [ As operandtype ]`

|파트|설명|
|----------|-----------------|
|`ByVal`|선택 사항 이지만 전달 메커니즘이 [ByVal](../modifiers/byval.md)이어야 합니다.|
|`operandname`|필수 사항입니다. 이 피연산자를 나타내는 변수의 이름입니다. [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.|
|`operandtype`|가이 아닌 경우 선택 사항입니다 `Option Strict` `On` . 이 피연산자의 데이터 형식입니다.|

`type`  
가이 아닌 경우 선택 사항입니다 `Option Strict` `On` . 연산자 프로시저에서 반환 하는 값의 데이터 형식입니다.

`statements`  
선택 사항입니다. 연산자 프로시저에서 실행 하는 문 블록입니다.

`returnvalue`  
필수 사항입니다. 연산자 프로시저가 호출 코드에 반환 하는 값입니다.

`End` `Operator`  
필수 사항입니다. 이 연산자 프로시저의 정의를 종료 합니다.

## <a name="remarks"></a>설명

`Operator`는 클래스 또는 구조체 에서만 사용할 수 있습니다. 즉, 연산자의 *선언 컨텍스트* 는 소스 파일, 네임 스페이스, 모듈, 인터페이스, 프로시저 또는 블록이 될 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.

모든 연산자는 여야 합니다 `Public Shared` . `ByRef` `Optional` `ParamArray` 두 피연산자에 대해, 또는를 지정할 수 없습니다.

연산자 기호 또는 식별자를 사용 하 여 반환 값을 저장할 수 없습니다. 문을 사용 해야 하 `Return` 고 값을 지정 해야 합니다. `Return`프로시저의 아무 곳에 나 원하는 수의 문이 표시 될 수 있습니다.

이러한 방식으로 연산자를 정의 하는 것은 키워드를 사용 하는지 여부에 관계 없이 *연산자 오버 로드* 라고 `Overloads` 합니다. 다음 표에는 정의할 수 있는 연산자가 나와 있습니다.

|Type|연산자|
|----------|---------------|
|단항|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|이진|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|변환(단항)|`CType`|

`=`이진 목록의 연산자는 대입 연산자가 아닌 비교 연산자입니다.

를 정의 하 `CType` 는 경우 또는를 지정 해야 합니다 `Widening` `Narrowing` .

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

- 및 연산자를 정의 하는 경우 `IsTrue` `IsFalse` 둘 다 형식을 반환 해야 합니다 `Boolean` .

- 및 연산자를 정의 하는 경우 `<<` `>>` 둘 다 `Integer` 의에 대 한 형식을 지정 해야 합니다 `operandtype` `operand2` .

반환 형식은 두 피연산자의 형식에 해당 하지 않아도 됩니다. 예를 들어 또는와 같은 비교 연산자 `=` 는 `<>` 가이 아닌 경우에도를 반환할 수 있습니다 `Boolean` `Boolean` .

## <a name="logical-and-bitwise-operators"></a>논리 및 비트 연산자

`And`,, `Or` `Not` 및 연산자는 `Xor` Visual Basic에서 논리적 or 비트 연산을 수행할 수 있습니다. 그러나 클래스 또는 구조체에서 이러한 연산자 중 하나를 정의 하는 경우에는 비트 연산을 정의할 수 있습니다.

문을 사용 하 여 직접 연산자를 정의할 수 없습니다 `AndAlso` `Operator` . 그러나 `AndAlso` 다음 조건을 충족 하는 경우에는를 사용할 수 있습니다.

- `And`에 사용 하려는 것과 동일한 피연산자 유형에 대해를 정의 했습니다 `AndAlso` .

- 정의는 `And` 정의 된 클래스 또는 구조체와 동일한 형식을 반환 합니다.

- `IsFalse`사용자가 정의한 클래스 또는 구조체에서 연산자를 정의 했습니다 `And` .

마찬가지로, `OrElse` `Or` 클래스 또는 구조체의 반환 형식을 사용 하 여 동일한 피연산자에을 정의 하 고 `IsTrue` 클래스 또는 구조체에를 정의한 경우를 사용할 수 있습니다.

## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions

*확대 변환은* 런타임에 항상 성공 하지만 *축소 변환은* 런타임에 실패할 수 있습니다. 자세한 내용은 [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.

변환 프로시저를로 선언 하는 경우 `Widening` 프로시저 코드에서 오류를 생성 해서는 안 됩니다. 이는 다음을 의미합니다.

- 항상 형식의 유효한 값을 반환 해야 합니다 `type` .

- 가능한 모든 예외 및 기타 오류 조건을 처리 해야 합니다.

- 호출 하는 프로시저에서 반환 되는 모든 오류를 처리 해야 합니다.

변환 프로시저가 성공 하지 못할 수 있거나 처리 되지 않은 예외가 발생할 수 있는 경우로 선언 해야 합니다 `Narrowing` .

## <a name="example"></a>예제

다음 코드 예제에서는 문을 사용 하 여 `Operator` `And` ,, `Or` `IsFalse` 및 `IsTrue` 연산자에 대 한 연산자 프로시저를 포함 하는 구조체의 개요를 정의 합니다. `And` 및 `Or` 는 각각 형식과 반환 형식의 두 피연산자를 사용 `abc` `abc` 합니다. `IsFalse` 및 `IsTrue` 는 각각 형식의 단일 피연산자를 사용 `abc` 하 고를 반환 `Boolean` 합니다. 이러한 정의를 통해 호출 코드는 `And` ,, `AndAlso` 및를 `Or` `OrElse` 형식의 피연산자와 함께 사용할 수 `abc` 있습니다.

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a>참고 항목

- [IsFalse 연산자](../operators/isfalse-operator.md)
- [IsTrue 연산자](../operators/istrue-operator.md)
- [Widening](../modifiers/widening.md)
- [Narrowing](../modifiers/narrowing.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [연산자 프로시저](../../programming-guide/language-features/procedures/operator-procedures.md)
- [방법: 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [방법: 변환 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [방법: 연산자 프로시저 호출](../../programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [방법: 연산자를 정의하는 클래스 사용](../../programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
