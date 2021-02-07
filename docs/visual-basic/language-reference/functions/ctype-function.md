---
description: '자세한 정보: CType 함수 (Visual Basic)'
title: CType Function
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 9732f52b40e5f762769ba5dc340c000e7e1ba17a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701263"
---
# <a name="ctype-function-visual-basic"></a>CType 함수(Visual Basic)

식을 지정한 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스로 명시적으로 변환한 결과를 반환 합니다.

## <a name="syntax"></a>Syntax

```vb
CType(expression, typename)
```

## <a name="parts"></a>부분

`expression` 모든 유효한 식입니다. 의 값 `expression` 이에서 허용 하는 범위를 벗어나면 `typename` Visual Basic 예외를 throw 합니다.

`typename``As`문의 절, `Dim` 즉 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스의 이름에 적합 한 식입니다.

## <a name="remarks"></a>설명

> [!TIP]
> 다음 함수를 사용 하 여 형식 변환을 수행할 수도 있습니다.
>
> - `CByte` `CDbl` `CInt` 특정 데이터 형식으로 변환을 수행 하는,, 등의 형식 변환 함수 자세한 내용은 [형식 변환 함수](type-conversion-functions.md)를 참조하세요.
> - [DirectCast operator](../operators/directcast-operator.md) 또는 [TryCast operator](../operators/trycast-operator.md). 이러한 연산자를 적용 하려면 한 형식이 다른 형식에서 상속 하거나 다른 형식을 구현 해야 합니다. `CType`데이터 형식으로 변환 하는 경우 보다 약간 더 나은 성능을 제공할 수 있습니다 `Object` .

`CType` 는 인라인으로 컴파일 되므로 변환 코드는 식을 계산 하는 코드의 일부입니다. 변환을 수행 하기 위해 프로시저가 호출 되지 않기 때문에 코드가 더 빨리 실행 되는 경우도 있습니다.

에서로의 변환이 정의 되지 않은 경우 `expression` `typename` (예:에서 `Integer` 로 `Date` ) Visual Basic 컴파일 시간 오류 메시지를 표시 합니다.

런타임에 변환이 실패 하면 적절 한 예외가 throw 됩니다. 축소 변환에 실패 하는 경우 <xref:System.OverflowException> 가 가장 일반적인 결과입니다. 변환이 정의 되지 않은 경우이 <xref:System.InvalidCastException> throw 됩니다. 예를 들어 `expression` 가 형식이 `Object` 고 해당 런타임 형식이로 변환 되지 않은 경우이 문제가 발생할 수 있습니다 `typename` .

또는의 데이터 형식이 `expression` `typename` 정의한 클래스 또는 구조체 인 경우 `CType` 해당 클래스 또는 구조체를 변환 연산자로 정의할 수 있습니다. 이렇게 하면 `CType` *오버 로드 된 연산자* 역할을 수행 합니다. 이 작업을 수행 하는 경우 throw 할 수 있는 예외를 포함 하 여 클래스 또는 구조체에서 변환의 동작을 제어할 수 있습니다.

## <a name="overloading"></a>오버로딩

`CType`코드 외부에서 정의 된 클래스 또는 구조체에서 연산자를 오버 로드할 수도 있습니다. 코드가 이러한 클래스나 구조체 간에 변환 되는 경우 해당 연산자의 동작을 이해 하 고 있어야 합니다 `CType` . 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.

## <a name="converting-dynamic-objects"></a>동적 개체 변환

동적 개체의 형식 변환은 또는 메서드를 사용 하는 사용자 정의 동적 변환에 의해 수행 됩니다 <xref:System.Dynamic.DynamicObject.TryConvert%2A> <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> . 동적 개체로 작업 하는 경우 메서드를 사용 <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> 하 여 동적 개체를 변환 합니다.

## <a name="example"></a>예제

다음 예에서는 함수를 사용 하 여 `CType` 식을 데이터 형식으로 변환 합니다 `Single` .

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

추가 예제는 [암시적 변환과 명시적 변환](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [형식 변환 함수](type-conversion-functions.md)
- [변환 함수](conversion-functions.md)
- [Operator Statement](../statements/operator-statement.md)
- [방법: 변환 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [.NET Framework의 형식 변환](../../../standard/base-types/type-conversion.md)
