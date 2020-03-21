---
title: ULong 데이터 형식
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401318"
---
# <a name="ulong-data-type-visual-basic"></a>ULong 데이터 유형(비주얼 베이직)

0에서 18,446,744,073,709,551,615(1.84배 10 ^ 19)의 값에 이르는 서명되지 않은 64비트(8바이트) 정수를 보유합니다.

## <a name="remarks"></a>설명

`ULong` 데이터 형식을 사용하여 이진 데이터가 `UInteger`너무 크거나 서명되지 않은 가장 큰 정수 값을 포함합니다.

`ULong`의 기본값은 0입니다.

## <a name="literal-assignments"></a>리터럴 할당

소수점 문자, 육각 형 리터럴, 옥탈 리터럴 또는 (Visual Basic 2017로 시작) 이진 리터럴을 할당하여 `ULong` 변수를 선언하고 초기화 할 수 있습니다. 정수 리터럴이 `ULong` 범위를 벗어나는 경우(즉 <xref:System.UInt64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 7,934,076,125와 같은 정수가 `ULong` 값에 할당됩니다.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> 접두사를 `&h` 사용하거나 `&H` 육각 문자 문자, `&b` 접두사 또는 이진 `&B` 리터럴을 나타내거나 접두사를 `&o` 나타내거나 `&O` 팔각형 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터는 다음 예제와 같이 `_`밑줄 문자를 숫자 구분 기호로 사용하여 가독성을 향상시킬 수도 있습니다.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Visual Basic 15.5부터는 접두사와 육각형, 이진 또는 옥탈 숫자 사이의 선행 구분 기호로 밑줄 문자()를`_`사용할 수도 있습니다. 다음은 그 예입니다.

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

숫자 리터럴은 다음 `UL` 예제와 `ul` 같이 `ULong` 데이터 형식을 나타내는 문자 또는 [형식을](../../programming-guide/language-features/data-types/type-characters.md) 포함할 수도 있습니다.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>프로그래밍 팁

- **음수.** 서명되지 않은 형식이기 때문에 `ULong` 음수를 나타낼 수 없습니다. 입력을`-` `ULong`평가하는 식에서 unary 빼기 () 연산자를 사용하는 경우 `Decimal` Visual Basic은 식을 먼저 변환합니다.

- **CLS 규정 준수.** `ULong` 데이터 형식은 공통 언어 [사양(CLS)의](https://www.ecma-international.org/publications/standards/Ecma-335.htm) 일부가 아니므로 CLS 호환 코드는 이를 사용하는 구성 요소를 사용할 수 없습니다.

- **Interop 고려 사항.** .NET Framework에 대해 작성되지 않은 구성 요소(예: 자동화 또는 COM 개체)와 `ulong` 인터페이싱하는 경우 다른 환경에서 다른 데이터 너비(32비트)를 가질 수 있습니다. 이러한 구성 요소에 32비트 인수를 전달하는 경우 관리되는 `UInteger` Visual `ULong` Basic 코드가 아닌 것처럼 선언합니다.

  또한 자동화는 Windows 95, Windows 98, Windows ME 또는 Windows 2000에서 64비트 정수를 지원하지 않습니다. 이러한 플랫폼의 자동화 `ULong` 구성 요소에 Visual Basic 인수를 전달할 수 없습니다.

- **확대.** 데이터 `ULong` 형식은 에 `Decimal` `Single`대해 `Double`넓혀지고 . 즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 `ULong` 발생하지 않고 이러한 유형으로 변환할 수 있습니다.

- **문자를 입력합니다.** 리터럴 형식 문자를 `UL` 리터럴 문자에 적용하면 `ULong` 데이터 형식에 강제로 적용됩니다. `ULong`식별자 유형 문자가 없습니다.

- **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.UInt64?displayProperty=nameWithType> 구조체입니다.

## <a name="see-also"></a>참고 항목

- <xref:System.UInt64>
- [데이터 유형](../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [방법: 부호 없는 형식을 사용하는 Windows 함수 호출](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
