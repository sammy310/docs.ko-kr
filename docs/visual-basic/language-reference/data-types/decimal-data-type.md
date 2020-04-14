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
ms.openlocfilehash: d4d868ba7c05cf3c2d538de1217231df91d4f43d
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243325"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal 데이터 형식(Visual Basic)

10의 가변 배율로 조정된 96비트(12바이트) 정수 숫자를 표시하는 서명된 128비트(16바이트) 값을 보유합니다. 배율 인수는 소수점 의 오른쪽에 있는 자릿수를 지정합니다. 0에서 28까지의 범위입니다. 배율이 0(소수자릿수 없음)인 경우 가능한 가장 큰 값은 +/79,228,162,514,264,337,593,543,950,335(+/7.92286251444337555353335+)입니다. 소수점 이하 28자리의 경우 가장 큰 값은 +/7.9228162514264437533335555335이며, 가장 작은 비영값은 +/-0.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000035입니다.

## <a name="remarks"></a>설명

데이터 `Decimal` 형식은 숫자에 대해 가장 많은 중요한 숫자를 제공합니다. 최대 29개의 중요한 숫자를 지원하며 7.9228 x 10^28을 초과하는 값을 나타낼 수 있습니다. 많은 숫자가 필요하지만 반올림 오류를 견딜 수 없는 재무 와 같은 계산에 특히 적합합니다.

`Decimal`의 기본값은 0입니다.

## <a name="programming-tips"></a>프로그래밍 팁

- **정밀도.** `Decimal`는 부동 지점 데이터 형식이 아닙니다. 구조는 `Decimal` 이진 정수 값을 가지며, 부호 비트 및 값의 소수점 분수 부분을 지정하는 정수 배율 인수와 함께 있습니다. 따라서 `Decimal` 숫자는 부동 점 형식 (및)보다`Single` `Double`메모리에서 더 정확한 표현을 갖습니다.

- **성능.** 데이터 `Decimal` 형식은 모든 숫자 형식 중 에서 가장 느립니다. 데이터 형식을 선택하기 전에 성능과 정밀도의 중요성을 고려해야 합니다.

- **확대.** 데이터 `Decimal` 형식이 또는 `Single` `Double`로 확장됩니다. 즉, 오류가 `Decimal` 발생하지 않고 이러한 형식 중 <xref:System.OverflowException?displayProperty=nameWithType> 하나로 변환할 수 있습니다.

- **후행 영점.** Visual Basic은 후행 영점을 `Decimal` 리터럴에 저장하지 않습니다. 그러나 변수는 `Decimal` 후행 영점 0을 계산적으로 유지합니다. 다음은 이에 대한 예입니다.

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  앞의 `MsgBox` 예제의 출력은 다음과 같습니다.

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **문자를 입력합니다.** 리터럴 형식 문자 `D`를 리터럴에 추가하면 `Decimal` 데이터 형식이 됩니다. 식별자 형식 문자 `@`를 식별자에 추가하면 `Decimal`가 됩니다.

- **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Decimal?displayProperty=nameWithType> 구조체입니다.

## <a name="range"></a>범위

 `D` 형식 문자를 사용하여 변수 또는 상수에 큰 값을 할당해야 할 수 `Decimal` 있습니다. 이 요구 사항은 다음 예제에서 볼 `Long` 수 있듯이 리터럴 형식 문자가 리터럴을 따르지 않는 한 컴파일러가 리터럴을 문자로 해석하기 때문입니다.

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

에 대 `bigDec1` 한 선언은 오버플로를 생성 하지 않습니다 에 할당 된 `Long`값이 에 대 한 범위 내에 있기 때문에. 변수에 `Long` 값을 할당할 `Decimal` 수 있습니다.

에 할당된 `bigDec2` 값이 너무 커서 오버플로 오류가 `Long`생성됩니다. 숫자 리터럴은 먼저 로 `Long`해석할 수 없으므로 `Decimal` 변수에 할당할 수 없습니다.

의 `bigDec3`경우 리터럴 `D` 형식 문자는 컴파일러가 리터럴을 `Decimal` `Long`대신 에 로 해석하도록 하여 문제를 해결합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [데이터 유형](../../../visual-basic/language-reference/data-types/index.md)
- [Single 데이터 형식](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Double 데이터 형식](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
