---
title: 산술 연산자
ms.date: 07/20/2015
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators [Visual Basic]
- bit-shift operators [Visual Basic]
- zero, division by zero
- operators [Visual Basic], arithmetic
- division [Visual Basic], by zero
- Visual Basic code, operators
- arithmetic operators [Visual Basic], about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
ms.openlocfilehash: 8ded8d7111bd37cf8762a202b728e814aa5a082b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352653"
---
# <a name="arithmetic-operators-in-visual-basic"></a>Visual Basic의 산술 연산자
산술 연산자는 리터럴, 변수, 기타 식, 함수 및 속성 호출, 상수로 표시 되는 숫자 값의 계산과 관련 된 많은 익숙한 산술 연산을 수행 하는 데 사용 됩니다. 또한 산술 연산자를 사용 하 여 분류 하는 비트 시프트 연산자는 피연산자의 개별 비트 수준에서 작동 하 고 비트 패턴을 왼쪽 또는 오른쪽으로 이동 하는 연산자입니다.  
  
## <a name="arithmetic-operations"></a>산술 연산  
 다음 예제가 보여 주는 것 처럼 [+ 연산자](../../../../visual-basic/language-reference/operators/addition-operator.md)를 사용 하 여 식에 두 값을 추가 하거나 [-연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md)를 사용 하 여 다른 값에서 1을 뺄 수 있습니다.  
  
 [!code-vb[VbVbalrOperators#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#57)]  
  
 또한 부정 [연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md)를 사용 하지만 다음 예제와 같이 피연산자를 하나만 사용 합니다.  
  
 [!code-vb[VbVbalrOperators#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#58)]  
  
 곱하기와 나누기는 다음 예제에서 보여 주는 것 처럼 각각 [* 연산자](../../../../visual-basic/language-reference/operators/multiplication-operator.md) 및 [/연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)를 사용 합니다.  
  
 [!code-vb[VbVbalrOperators#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#59)]  
  
 다음 예제와 같이 지 한가 [^ 연산자](../../../../visual-basic/language-reference/operators/exponentiation-operator.md)를 사용 합니다.  
  
 [!code-vb[VbVbalrOperators#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#60)]  
  
 정수 나누기는 [\ 연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md)를 사용 하 여 수행 됩니다. 정수 나누기는 몫을 반환 합니다. 즉, 나머지는 고려 하지 않고 나누는 수를 피제수로 나눌 수 있는 횟수를 나타내는 정수입니다. 제 수와 피제수는 모두이 연산자에 대 한 정수 계열 형식 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`) 이어야 합니다. 다른 모든 형식은 먼저 정수 계열 형식으로 변환 해야 합니다. 다음 예제에서는 정수 나누기를 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#61)]  
  
 모듈러스 연산은 [Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md)를 사용 하 여 수행 됩니다. 이 연산자는 제 수를 피제수로 나눈 후 나머지를 반환 합니다. 제 수와 피제수 모두 정수 계열 형식인 경우 반환 되는 값은 정수 계열입니다. 제 수와 피제수가 부동 소수점 형식인 경우 반환 되는 값도 부동 소수점입니다. 다음 예에서는 이러한 동작을 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbalrOperators#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#63)]  
  
### <a name="attempted-division-by-zero"></a>0으로 나누기 시도  
 0으로 나누기는 관련 데이터 형식에 따라 다른 결과를 가집니다. 정수 부분 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`)에서는 .NET Framework 예외가 throw 됩니다.<xref:System.DivideByZeroException> `Decimal` 또는 `Single` 데이터 형식에 대 한 나누기 연산에서 .NET Framework는 <xref:System.DivideByZeroException> 예외도 throw 합니다.  
  
 `Double` 데이터 형식을 포함 하는 부동 소수점 분할에서는 예외가 throw 되지 않으며 피제수에 따라 <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>또는 <xref:System.Double.NegativeInfinity>를 나타내는 클래스 멤버가 생성 됩니다. 다음 표에서는 `Double` 값을 0으로 나누려고 시도 하는 다양 한 결과를 요약 하 여 보여 줍니다.  
  
|피제수 데이터 형식|제 들 데이터 형식|피제수 값|결과|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN> (수학적으로 정의 된 숫자 아님)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 <xref:System.DivideByZeroException> 예외를 catch 하는 경우 해당 멤버를 사용 하 여 처리 하는 데 도움이 될 수 있습니다. 예를 들어 <xref:System.Exception.Message%2A> 속성은 예외에 대 한 메시지 텍스트를 포함 합니다. 자세한 내용은 [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.  
  
## <a name="bit-shift-operations"></a>비트 시프트 연산  
 비트 시프트 연산은 비트 패턴에서 산술 시프트를 수행 합니다. 패턴은 왼쪽에 있는 피연산자에 포함 되 고 오른쪽의 피연산자는 패턴을 이동할 위치 수를 지정 합니다. [> > 연산자](../../../../visual-basic/language-reference/operators/right-shift-operator.md) 를 사용 하 여 패턴을 오른쪽으로 이동 하거나 [< < 연산자](../../../../visual-basic/language-reference/operators/left-shift-operator.md)를 사용 하 여 왼쪽으로 이동할 수 있습니다.  
  
 패턴 피연산자의 데이터 형식은 `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`또는 `ULong`여야 합니다. 시프트 금액 피연산자의 데이터 형식은 `Integer` 이거나 `Integer`으로 확장 되어야 합니다.  
  
 산술 시프트는 순환 하지 않습니다. 즉, 결과의 한쪽 끝에서 이동 하는 비트가 다른 쪽 끝에서는 다시 계산 되지 않습니다. 시프트에 의해 비워진 비트 위치는 다음과 같이 설정 됩니다.  
  
- 산술 왼쪽 시프트의 경우 0입니다.  
  
- 양수의 산술 오른쪽 시프트 인 경우 0입니다.  
  
- 부호 없는 데이터 형식의 산술 오른쪽 시프트 (`Byte`, `UShort`, `UInteger`, `ULong`)의 경우 0입니다.  
  
- 1-음수 (`SByte`, `Short`, `Integer`또는 `Long`)의 산술 오른쪽 시프트  
  
 다음 예에서는 `Integer` 값을 왼쪽과 오른쪽으로 이동 합니다.  
  
 [!code-vb[VbVbalrOperators#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#64)]  
  
 산술 시프트는 오버플로 예외를 생성 하지 않습니다.  
  
## <a name="bitwise-operations"></a>비트 연산  
 논리 연산자 외에도, `Not`, `Or`, `And`및 `Xor`는 숫자 값에 사용 될 때 비트 산술 연산을 수행 합니다. 자세한 내용은 [Visual Basic 논리 및 비트 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)의 "비트 연산"을 참조 하세요.  
  
## <a name="type-safety"></a>형식 안전성  
 일반적으로 피연산자는 동일한 형식 이어야 합니다. 예를 들어 `Integer` 변수를 추가 하는 경우 다른 `Integer` 변수에 추가 하 고 결과를 `Integer` 형식의 변수에도 할당 해야 합니다.  
  
 적절 한 형식 안전 코딩 방법을 보장 하는 한 가지 방법은 [Option Strict 문을](../../../../visual-basic/language-reference/statements/option-strict-statement.md)사용 하는 것입니다. `Option Strict On`를 설정 하는 경우 Visual Basic에서 *형식 안전* 변환을 자동으로 수행 합니다. 예를 들어 `Double` 변수에 `Integer` 변수를 추가 하 고 `Double` 변수에 값을 할당 하려고 하면 `Integer` 값이 데이터 손실 없이 `Double`으로 변환 될 수 있으므로 작업이 정상적으로 진행 됩니다. 반면, 형식이 안전 하지 않은 변환은 컴파일러 오류를 `Option Strict On`으로 발생 시킵니다. 예를 들어 `Double` 변수에 `Integer` 변수를 추가 하 고 `Integer` 변수에 값을 할당 하려고 하면 `Double` 변수가 암시적으로 `Integer`형식으로 변환 될 수 없으므로 컴파일러 오류가 발생 합니다.  
  
 그러나 `Option Strict Off`를 설정 하는 경우 Visual Basic에서 암시적 축소 변환을 수행할 수 있지만 예기치 않은 데이터 손실이 나 전체 자릿수가 발생할 수 있습니다. 따라서 프로덕션 코드를 작성할 때 `Option Strict On`를 사용 하는 것이 좋습니다. 자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [산술 연산자](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [비트 시프트 연산자](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Visual Basic의 연결 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Visual Basic 논리 및 비트 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [연산자의 효율적 결합](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
