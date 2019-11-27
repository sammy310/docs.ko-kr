---
title: Mod 연산자
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: b7552550d4b0496d6ad7ee76a7327054d544b874
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350910"
---
# <a name="mod-operator-visual-basic"></a>Mod 연산자 (Visual Basic)

두 숫자를 나누고 나머지만 반환 합니다.

## <a name="syntax"></a>구문

```vb
result = number1 Mod number2
```

## <a name="parts"></a>요소

`result` \
필수입니다. 임의의 숫자 변수 또는 속성입니다.

`number1` \
필수입니다. 임의의 숫자 식입니다.

`number2` \
필수입니다. 임의의 숫자 식입니다.

## <a name="supported-types"></a>지원되는 유형

모든 숫자 형식. 여기에는 부호 없는 형식과 부동 소수점 형식 및 `Decimal`포함 됩니다.

## <a name="result"></a>결과

결과는 `number1` `number2`으로 나눈 나머지입니다. 예를 들어 식 `14 Mod 4`는 2로 계산 됩니다.

> [!NOTE]
> 수학의 *나머지가* 서로 다르며 *음수에 대해* 다른 결과가 있습니다. Visual Basic, .NET Framework `op_Modulus` 연산자 및 기본 [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL 명령의 `Mod` 연산자는 모두 나머지 작업을 수행 합니다.

`Mod` 작업의 결과는 피제수, `number1`의 부호를 유지 하므로 양수 또는 음수일 수 있습니다. 결과는 항상 범위 (-`number2`, `number2`), 배타 범위에 있습니다. 예를 들면 다음과 같습니다.

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a>주의

`number1` 또는 `number2`가 부동 소수점 값 이면 나누기의 부동 소수점 나머지가 반환 됩니다. 결과의 데이터 형식은 `number1`의 데이터 형식으로 나눈 값과 `number2`가능한 모든 값을 포함할 수 있는 가장 작은 데이터 형식입니다.

`number1` 또는 `number2`가 [Nothing](../../../visual-basic/language-reference/nothing.md)으로 평가 되 면 0으로 처리 됩니다.

관련 연산자는 다음과 같습니다.

- [\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) 는 나눗셈의 정수 몫을 반환 합니다. 예를 들어 `14 \ 4` 식은 3으로 계산 됩니다.

- [/연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) 는 나머지를 포함 하 여 전체 몫을 부동 소수점 숫자로 반환 합니다. 예를 들어 `14 / 4` 식은 3.5로 계산 됩니다.

## <a name="attempted-division-by-zero"></a>0으로 나누기 시도

`number2` 0으로 계산 되는 경우 `Mod` 연산자의 동작은 피연산자의 데이터 형식에 따라 달라 집니다.

- 컴파일 시간에 `number2`을 확인할 수 없는 경우 정수 나누기는 <xref:System.DivideByZeroException> 예외를 throw 하 고 컴파일 시간에 `number2` 0으로 평가 되는 경우 컴파일 타임 오류 `BC30542 Division by zero occurred while evaluating this expression` 생성 합니다.
- 부동 소수점 나누기는 <xref:System.Double.NaN?displayProperty=nameWithType>를 반환 합니다.

## <a name="equivalent-formula"></a>동일한 수식

식 `a Mod b` 다음 수식 중 하에 해당 합니다.

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a>부동 소수점 부정확

부동 소수점 숫자를 사용 하는 경우 메모리에 항상 정확한 10 진수가 없다는 것을 명심 하십시오. 이로 인해 값 비교 및 `Mod` 연산자와 같은 특정 작업에서 예기치 않은 결과가 발생할 수 있습니다. 자세한 내용은 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)을 참조 하세요.

## <a name="overloading"></a>오버로드

`Mod` 연산자를 *오버 로드할*수 있습니다. 즉, 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다. 코드가 이러한 오버 로드를 포함 하는 클래스 또는 구조체의 인스턴스에 `Mod` 적용 되는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.

## <a name="example"></a>예제

다음 예에서는 `Mod` 연산자를 사용 하 여 두 숫자를 나누고 나머지만 반환 합니다. 두 숫자 중 하나가 부동 소수점 숫자인 경우 결과는 나머지를 나타내는 부동 소수점 숫자입니다.

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a>예제

다음 예제에서는 부동 소수점 피연산자의 잠재적 부정확을 보여 줍니다. 첫 번째 문에서 피연산자는 `Double`되며 0.2는 저장 된 값이 0.20000000000000001 인 무한 반복 이진 분수입니다. 두 번째 문에서 리터럴 형식 문자 `D` 두 피연산자를 `Decimal`하 고 0.2에 정확한 표현이 있습니다.

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
