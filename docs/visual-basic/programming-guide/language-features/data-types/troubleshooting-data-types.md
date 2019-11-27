---
title: 데이터 형식 문제 해결
ms.date: 07/20/2015
helpviewer_keywords:
- Char data type [Visual Basic], converting
- Decimal data type [Visual Basic], conversions
- data types [Visual Basic], troubleshooting
- literals [Visual Basic], default types
- type characters [Visual Basic], literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types [Visual Basic]
- floating-point numbers [Visual Basic], precision
- Boolean data type [Visual Basic], converting
- literal types [Visual Basic]
- literal type characters [Visual Basic]
- floating-point numbers [Visual Basic], imprecision
- String data type [Visual Basic], converting
- floating-point numbers [Visual Basic], comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
ms.openlocfilehash: 63b2513e420320742bf7e25314743f08404f46a7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350508"
---
# <a name="troubleshooting-data-types-visual-basic"></a>데이터 형식 문제 해결(Visual Basic)

이 페이지에는 내장 데이터 형식에 대 한 작업을 수행할 때 발생할 수 있는 몇 가지 일반적인 문제가 나열 되어 있습니다.

## <a name="floating-point-expressions-do-not-compare-as-equal"></a>부동 소수점 식이 동일 하 게 비교 되지 않습니다.

부동 소수점 숫자 ([단일 데이터 형식](../../../../visual-basic/language-reference/data-types/single-data-type.md) 및 [Double 데이터 형식](../../../../visual-basic/language-reference/data-types/double-data-type.md))를 사용 하는 경우 이진 분수로 저장 된다는 점에 주의 해야 합니다. 즉, 이진 분수가 아닌 수량을 정확 하 게 표현할 수 없습니다 (k 및 n은 정수). 여기서 k 및 n은 정수입니다. 예를 들어 0.5 (= 1/2) 및 0.3125 (= 5/16)는 정확한 값으로 보유할 수 있지만 0.2 (= 1/5) 및 0.3 (= 3/10)만 근사치 수 있습니다.

이 부정확 인해 부동 소수점 값에 대해 작업을 수행 하는 경우 정확한 결과를 사용할 수 없습니다. 특히 이론적으로 동일한 두 값의 표현은 약간 다를 수 있습니다.

| 부동 소수점 수량을 비교 하려면 |
|---|
|1. <xref:System> 네임 스페이스에서 <xref:System.Math> 클래스의 <xref:System.Math.Abs%2A> 메서드를 사용 하 여 해당 차이의 절대값을 계산 합니다.<br />2. 허용 되는 최대 차이를 결정 합니다. 즉, 차이가 더 크지 않은 경우 두 수량이 동일한 것으로 간주할 수 있습니다.<br />3. 차이의 절대값을 허용 가능한 차이와 비교 합니다.|

다음 예에서는 두 `Double` 값의 잘못 된 비교와 정확한 비교를 모두 보여 줍니다.

[!code-vb[VbVbalrDataTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#10)]

이전 예제에서는 <xref:System.Double> 구조의 <xref:System.Double.ToString%2A> 메서드를 사용 하 여 `CStr` 키워드에서 사용 하는 것 보다 더 높은 정밀도를 지정할 수 있도록 합니다. 기본값은 15 자리 이지만 "G17" 형식은 17 자리로 확장 합니다.

## <a name="mod-operator-does-not-return-accurate-result"></a>Mod 연산자가 정확한 결과를 반환 하지 않습니다.

부동 소수점 저장소의 부정확 때문에 피연산자 중 하나 이상이 부동 소수점 이면 [Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md) 는 예기치 않은 결과를 반환할 수 있습니다.

[Decimal 데이터 형식은](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) 부동 소수점 표현을 사용 하지 않습니다. `Single` 및 `Double` 부정확 한에 있는 많은 숫자는 `Decimal`에서 정확 하 게 사용할 수 있습니다 (예: 0.2 및 0.3). 산술은 부동 소수점 에서보다 `Decimal` 속도가 느리므로 더 나은 정밀도를 얻기 위해 성능이 저하 될 수 있습니다.

|부동 소수점 수량의 정수 나머지를 찾으려면|
|---|
|1. 변수를 `Decimal`으로 선언 합니다.<br />2. 리터럴 형식 문자 `D`를 사용 하 여 `Long` 데이터 형식에 대 한 값이 너무 클 경우 리터럴을 강제로 `Decimal`합니다.|

다음 예제에서는 부동 소수점 피연산자의 잠재적 부정확을 보여 줍니다.

[!code-vb[VbVbalrDataTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#11)]

이전 예제에서는 <xref:System.Double> 구조의 <xref:System.Double.ToString%2A> 메서드를 사용 하 여 `CStr` 키워드에서 사용 하는 것 보다 더 높은 정밀도를 지정할 수 있도록 합니다. 기본값은 15 자리 이지만 "G17" 형식은 17 자리로 확장 합니다.

`zeroPointTwo` `Double`이므로 0.2에 대 한 값은 저장 된 값이 0.20000000000000001 인 무한 반복 이진 분수입니다. 이 수량으로 2.0을 나누면 0.19999999999999991의 나머지가 9.9999999999999995 생성 됩니다.

`decimalRemainder`에 대 한 식에서 리터럴 형식 문자 `D` 피연산자는 모두 `Decimal`하 고 0.2에는 정확한 표현이 있습니다. 따라서 `Mod` 연산자는 예상 나머지가 0.0을 생성 합니다.

`decimalRemainder`를 `Decimal`으로 선언 하는 것 만으로는 충분 하지 않습니다. 또한 리터럴을 강제로 `Decimal`하도록 하거나 기본적으로 `Double`를 사용 하 고 `decimalRemainder` `doubleRemainder`와 동일한 부정확 한 값을 수신 해야 합니다.

## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>부울 형식이 숫자 형식으로 정확 하 게 변환 되지 않습니다.

[부울 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값은 숫자로 저장 되지 않으며 저장 된 값은 숫자와 동일 하지 않습니다. 이전 버전과의 호환성을 위해 Visual Basic는 변환 키워드 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`등)를 제공 하 여 `Boolean` 및 숫자 형식 간에 변환 합니다. 그러나 다른 언어에서는 .NET Framework 메서드와 같이 이러한 변환을 다르게 수행 하기도 합니다.

`True` 및 `False`에 대해 동일한 숫자 값을 사용 하는 코드를 작성 하면 안 됩니다. 가능 하면 `Boolean` 변수의 사용을 디자인 된 논리 값으로 제한 해야 합니다. `Boolean` 및 숫자 값을 혼합 해야 하는 경우에는 선택한 변환 방법을 이해 해야 합니다.

### <a name="conversion-in-visual-basic"></a>Visual Basic 변환

`CType` 또는 `CBool` 변환 키워드를 사용 하 여 숫자 데이터 형식을 `Boolean`로 변환 하면 0이 `False` 되 고 다른 모든 값은 `True`됩니다. 변환 키워드를 사용 하 여 `Boolean` 값을 숫자 형식으로 변환 하는 경우 `False`은 0이 되 고 `True`는-1이 됩니다.

### <a name="conversion-in-the-framework"></a>프레임 워크의 변환

<xref:System> 네임 스페이스에 있는 <xref:System.Convert> 클래스의 <xref:System.Convert.ToInt32%2A> 메서드는 `True`를 + 1로 변환 합니다.

`Boolean` 값을 숫자 데이터 형식으로 변환 해야 하는 경우 사용 하는 변환 방법에 주의 해야 합니다.

## <a name="character-literal-generates-compiler-error"></a>문자 리터럴이 컴파일러 오류를 생성 합니다.

형식 문자가 없으면 Visual Basic는 리터럴에 대 한 기본 데이터 형식을 가정 합니다. 문자 리터럴의 기본 형식 (따옴표 (`" "`))은 `String`입니다.

`String` 데이터 형식은 [Char 데이터 형식](../../../../visual-basic/language-reference/data-types/char-data-type.md)으로 확장 되지 않습니다. 즉, `Char` 변수에 리터럴을 할당 하려는 경우 축소 변환을 수행 하거나 리터럴을 `Char` 형식으로 강제 해야 합니다.

|변수 또는 상수에 할당할 Char 리터럴을 만들려면|
|---|
|1. 변수 또는 상수를 `Char`으로 선언 합니다.<br />2. 문자 값을 따옴표로 묶습니다 (`" "`).<br />3. 리터럴 형식 문자 `C`를 사용 하 여 닫는 큰따옴표를 따라 리터럴을 강제로 `Char`합니다. 형식 검사 스위치 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))를 `On`하는 경우 필요 합니다.|

다음 예에서는 `Char` 변수에 대 한 리터럴의 성공 및 성공 여부를 모두 보여 줍니다.

[!code-vb[VbVbalrDataTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#12)]

런타임에 실패할 수 있으므로 축소 변환을 사용할 경우 항상 위험이 있습니다. 예를 들어 `String` 값이 둘 이상의 문자를 포함 하는 경우 `String`에서 `Char`로의 변환이 실패할 수 있습니다. 따라서 `C` 형식 문자를 사용 하는 것이 더 효율적입니다.

## <a name="string-conversion-fails-at-run-time"></a>런타임에 문자열 변환이 실패 함

[문자열 데이터 형식은](../../../../visual-basic/language-reference/data-types/string-data-type.md) 매우 적은 확대 변환에 참여 합니다. `String`는 자신과 `Object`만 확대 되 고, `Char` 및 `Char()` (`Char` 배열)만 확대 `String`으로 확대 됩니다. 이는 `String` 변수와 상수에 다른 데이터 형식에 포함 될 수 없는 값이 포함 될 수 있기 때문입니다.

형식 검사 스위치 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))가 `On`되 면 컴파일러는 모든 암시적 축소 변환을 허용 하지 않습니다. 여기에는 `String`관련 된 내용이 포함 됩니다. 코드는 `CStr` 및 [CType 함수와](../../../../visual-basic/language-reference/functions/ctype-function.md)같은 변환 키워드를 계속 사용할 수 있습니다 .이 함수는 .NET Framework를 통해 변환을 시도 합니다.

> [!NOTE]
> `For Each…Next` 컬렉션의 요소에서 loop 제어 변수로의 변환에 대해 축소 변환 오류가 표시 되지 않습니다. 자세한 내용 및 예제는 각 항목에 대 한 "축소 변환" 섹션을 참조 하세요. [ 다음 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).

### <a name="narrowing-conversion-protection"></a>축소 변환 보호

축소 변환의 단점은 런타임에 실패할 수 있다는 것입니다. 예를 들어, `String` 변수가 "True" 또는 "False" 이외의 값을 포함 하는 경우 `Boolean`로 변환할 수 없습니다. 문장 부호 문자를 포함 하는 경우 숫자 형식으로 변환 되지 않습니다. `String` 변수는 항상 대상 형식에서 허용할 수 있는 값을 보유 하 고 있지 않은 경우에는 변환을 시도 하지 않아야 합니다.

`String`에서 다른 데이터 형식으로 변환 해야 하는 경우 가장 안전한 절차는 [Try ... Catch ... Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). 이렇게 하면 런타임 오류를 처리할 수 있습니다.

### <a name="character-arrays"></a>문자 배열

단일 `Char` 및 `Char` 요소 배열이 모두 `String`으로 확장 됩니다. 그러나 `String`는 `Char()`으로 확장 되지 않습니다. `String` 값을 `Char` 배열로 변환 하려면 <xref:System.String?displayProperty=nameWithType> 클래스의 <xref:System.String.ToCharArray%2A> 메서드를 사용할 수 있습니다.

### <a name="meaningless-values"></a>의미 없는 값

일반적으로 `String` 값은 다른 데이터 형식에서 의미가 없으며 변환은 매우 인공이 고 위험할 수 있습니다. 가능 하면 `String` 변수의 사용을 디자인 된 문자 시퀀스로 제한 해야 합니다. 다른 형식의 동일한 값에 의존 하는 코드를 작성 하면 안 됩니다.

## <a name="see-also"></a>참고 항목

- [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Visual Basic 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [데이터 형식](../../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [데이터 형식의 효율적 사용](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
