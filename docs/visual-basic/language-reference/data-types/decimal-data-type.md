---
title: Decimal 데이터 형식
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: 6d62bcc1d043b45c0fc30154d9dc633b998f97b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344038"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal 데이터 형식(Visual Basic)

10의 가변 배율로 조정된 96비트(12바이트) 정수 숫자를 표시하는 서명된 128비트(16바이트) 값을 보유합니다. 배율 인수는 소수점 오른쪽의 자릿수를 지정 합니다. 범위는 0에서 28 까지입니다. 소수 자릿수가 0 인 소수 자릿수가 0 인 경우 가능한 최대값은 +/-79228162514264337593543950335 (+/-7.9228162514264337593543950335E + 28)입니다. 28 자리의 소수 자릿수를 사용 하면 가장 큰 값은 +/-7.9228162514264337593543950335이 고 0이 아닌 가장 작은 값은 +/-0.0000000000000000000000000001 (+/-1E-28)입니다.

## <a name="remarks"></a>주의

`Decimal` 데이터 형식은 숫자에 대 한 최대 유효 자릿수를 제공 합니다. 최대 29 개의 유효 숫자를 지원 하며 7.9228 x 10 ^ 28을 초과 하는 값을 나타낼 수 있습니다. 매우 많은 숫자가 필요 하지만 반올림 오류를 허용할 수 없는 재무와 같은 계산에 특히 적합 합니다.

`Decimal`의 기본값은 0입니다.

## <a name="programming-tips"></a>프로그래밍 팁

- **소수.** `Decimal`은 부동 소수점 데이터 형식이 아닙니다. `Decimal` 구조체는 부호 비트와 소수 부분을 지정 하는 정수 배율 인수와 함께 이진 정수 값을 포함 합니다. 이로 인해 `Decimal` 숫자는 부동 소수점 형식 (`Single` 및 `Double`) 보다 메모리에서 보다 정확 하 게 표시 됩니다.

- **성능.** `Decimal` 데이터 형식은 모든 숫자 형식이 가장 느립니다. 데이터 형식을 선택 하기 전에 성능에 대 한 정밀도의 중요도를 평가 해야 합니다.

- **넓혀.** `Decimal` 데이터 형식은 `Single` 또는 `Double`으로 확대 됩니다. 즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 발생 하지 않고 `Decimal`를 이러한 형식 중 하나로 변환할 수 있습니다.

- **후행 0입니다.** Visual Basic은 `Decimal` 리터럴에 후행 0을 저장 하지 않습니다. 그러나 `Decimal` 변수는 계산을 얻은 후행 0을 유지 합니다. 다음 예제에서는 이것을 보여 줍니다.

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  위의 예제에서 `MsgBox` 출력은 다음과 같습니다.

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **문자를 입력 합니다.** 리터럴 형식 문자 `D`를 리터럴에 추가하면 `Decimal` 데이터 형식이 됩니다. 식별자 형식 문자 `@`를 식별자에 추가하면 `Decimal`가 됩니다.

- **프레임 워크 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.Decimal?displayProperty=nameWithType> 구조체입니다.

## <a name="range"></a>범위

 `D` 형식 문자를 사용 하 여 `Decimal` 변수나 상수에 많은 값을 할당 해야 할 수도 있습니다. 이 요구 사항은 다음 예제와 같이 리터럴 형식 문자가 리터럴을 따르는 경우를 제외 하 고 컴파일러가 리터럴을 `Long` 해석 하기 때문입니다.

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

할당 된 값이 `Long`범위 내에 있기 때문에 `bigDec1`에 대 한 선언이 오버플로를 생성 하지 않습니다. `Decimal` 변수에 `Long` 값을 할당할 수 있습니다.

`bigDec2` 선언에는 할당 된 값이 `Long`에 비해 너무 커서 오버플로 오류가 발생 합니다. 숫자 리터럴은 먼저 `Long`해석 될 수 없으므로 `Decimal` 변수에 할당할 수 없습니다.

`bigDec3`의 경우 리터럴 형식 문자는 컴파일러에서 리터럴을 `Long`아닌 `Decimal` 해석 하도록 하 여 문제를 해결 `D` 합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [Single 데이터 형식](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Double 데이터 형식](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
