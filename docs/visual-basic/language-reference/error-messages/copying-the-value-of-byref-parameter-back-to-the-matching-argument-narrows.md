---
description: "자세한 정보: BC32053: ' ByRef ' 매개 변수 ' '의 값을 <parametername> 일치 하는 인수에 다시 복사 ' '에서 ' ' 형식 <typename1> 으로 축소 <typename2>"
title: ByRef' 매개 변수 '<parametername>'의 값을 해당 인수에 다시 복사하면 '<typename1>' 형식에서 '<typename2>' 형식으로 축소 변환됩니다.
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: 36df6f1c5363a9517c8f3bec4410f5c3d7e38325
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471047"
---
# <a name="bc32053-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a>BC32053: ' ByRef ' 매개 변수 ' '의 값을 일치 하는 \<parametername> 인수에 다시 복사 하면 ' \<typename1> ' 형식에서 ' ' 형식으로 축소 변환 됩니다. \<typename2>

해당 매개 변수 형식으로 확대 되는 인수를 사용 하 여 프로시저를 호출 하 고 매개 변수에서 인수로 변환 하는 것은 축소입니다.

 클래스 또는 구조체를 정의하는 경우 해당 클래스 또는 구조체 형식을 다른 형식으로 변환하는 변환 연산자를 하나 이상 정의할 수 있습니다. 다른 형식을 클래스 또는 구조체 형식으로 다시 변환하는 역방향 변환 연산자를 정의할 수도 있습니다. 프로시저 호출에서 클래스 또는 구조체 형식을 사용 하는 경우 이러한 변환 연산자를 사용 하 여 인수 형식을 해당 매개 변수의 형식으로 변환할 수 Visual Basic.

 [ByRef](../modifiers/byref.md)인수를 전달 하는 경우 Visual Basic는 경우에 따라 참조를 전달 하는 대신 프로시저의 지역 변수에 인수 값을 복사 합니다. 이 경우 프로시저가 반환 될 때 Visual Basic는 지역 변수 값을 호출 코드의 인수에 다시 복사 해야 합니다.

 `ByRef` 인수 값이 프로시저에 복사되고 인수 및 매개 변수가 동일한 형식인 경우에는 변환이 필요하지 않습니다. 그러나 형식이 서로 다르면 Visual Basic 양방향으로 변환 해야 합니다. 형식 중 하나가 클래스 또는 구조체 형식이 면 Visual Basic 다른 형식으로 변환 해야 합니다. 이러한 변환 중 하나가 확대 되는 경우 역방향 변환은 축소 될 수 있습니다.

 **오류 ID:** BC32053

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 가능 하면 프로시저 매개 변수와 동일한 형식의 호출 인수를 사용 하므로 Visual Basic는 변환을 수행할 필요가 없습니다.

- 매개 변수 형식과 다른 인수 형식을 사용하여 프로시저를 호출해야 하지만 호출 인수에 값을 반환할 필요가 없는 경우 매개 변수를 [ByRef](../modifiers/byval.md) 가 아니라 `ByRef`로 정의합니다.

- 호출 인수에 값을 반환 해야 하는 경우 가능한 경우 역방향 변환 연산자를 [확대](../modifiers/widening.md)로 정의 합니다.

## <a name="see-also"></a>추가 정보

- [절차](../../programming-guide/language-features/procedures/index.md)
- [프로시저 매개 변수 및 인수](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [값 또는 참조로 인수 전달](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [연산자 프로시저](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Operator Statement](../statements/operator-statement.md)
- [방법: 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [방법: 변환 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Visual Basic의 형식 변환](../../programming-guide/language-features/data-types/type-conversions.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
