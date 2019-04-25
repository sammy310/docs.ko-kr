---
title: CType 함수(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: dbf01263723a9e2890dab57d5ffc3d467ed250fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801681"
---
# <a name="ctype-function-visual-basic"></a>CType 함수(Visual Basic)

식을 지정한 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스 명시적으로 변환한 결과 반환 합니다.

## <a name="syntax"></a>구문

```
CType(expression, typename)
```

## <a name="parts"></a>요소

`expression` 모든 유효한 식입니다. 경우 값 `expression` 에서 허용 범위를 벗어난 `typename`, Visual Basic 예외를 throw 합니다.

`typename` 유효한 식일을 `As` 절을 `Dim` 문, 즉, 모든 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스의 이름입니다.

## <a name="remarks"></a>설명

> [!TIP]
> 또한 형식 변환을 수행 하려면 다음 함수를 사용할 수 있습니다.
>
> - 같은 변환 함수를 입력 `CByte`, `CDbl`, 및 `CInt` 특정 데이터 형식 변환을 수행 하는 합니다. 자세한 내용은 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)를 참조하세요.
> - [DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 나 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md)합니다. 이러한 연산자는 하나의 형식에서 상속 되거나 다른 형식을 구현에 필요 합니다. 보다 약간 더 나은 성능을 제공할 수 있습니다 `CType` 사이에서 변환할 때의 `Object` 데이터 형식입니다.

`CType` 인라인으로 컴파일됩니다., 변환 코드가 식을 계산 하는 코드의 일부임을 의미 합니다. 일부 경우 코드를 한 절차가 없습니다 변환을 수행 하려면 호출 되므로 빠르게를 실행 합니다.

정의 된 변환이 없는 경우 `expression` 하 `typename` (예를 들어 `Integer` 에 `Date`), Visual Basic 컴파일 시간 오류 메시지가 표시 됩니다.

런타임에 변환에 실패 하면 해당 예외가 throw 됩니다. 축소 변환에 실패 하면는 <xref:System.OverflowException> 가장 일반적인 결과입니다. 변환이 정의 하는 경우는 <xref:System.InvalidCastException> throw 합니다. 예를 들어이 발생할 수 있습니다 `expression` 유형임 `Object` 해당 런타임 형식이 변환 되지 않습니다 및 `typename`합니다.

데이터 형식이 `expression` 나 `typename` 클래스 또는 구조를 정의한 정의할 수 있습니다 `CType` 해당 클래스 또는 구조로 변환 연산자에서. 따라서 `CType` 역할을 *오버 로드 된 연산자*합니다. 이 작업을 수행 하는 경우에 클래스 또는 구조를 throw 할 수 있는 예외를 포함 하 여 변환 하 고 동작을 제어할 수 있습니다.

## <a name="overloading"></a>오버로딩

`CType` 연산자 클래스 또는 구조체 외부 코드에 정의 된도 오버 로드할 수 있습니다. 코드와 같은 클래스 또는 구조체에서 변환, 하는 경우 사용할의 동작을 알고 있어야 해당 `CType` 연산자입니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.

## <a name="converting-dynamic-objects"></a>동적 개체 변환

동적 개체의 형식 변환을 사용 하는 사용자 정의 동적 변환을 수행한 합니다 <xref:System.Dynamic.DynamicObject.TryConvert%2A> 또는 <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> 메서드. 동적 개체를 사용 하는 경우 사용 된 <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> 동적 개체를 변환 하는 방법입니다.

## <a name="example"></a>예제

다음 예제에서는 합니다 `CType` 식을 변환 하는 함수는 `Single` 데이터 형식입니다.

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

추가 예제를 보려면 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)합니다.

## <a name="see-also"></a>참고자료

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 함수](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)
- [방법: 변환 연산자를 정의 합니다.](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [.NET Framework의 형식 변환](../../../standard/base-types/type-conversion.md)
