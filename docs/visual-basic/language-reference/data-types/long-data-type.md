---
title: Long 데이터 형식
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401402"
---
# <a name="long-data-type-visual-basic"></a>긴 데이터 유형(비주얼 베이직)

보유 는 -9,223,372,036,854,775,808에서 9,223,372,032,854,775,807 (9.2...E+18)의 가치에 이르는 64비트(8바이트) 정수에 속합니다.

## <a name="remarks"></a>설명

데이터 `Long` 형식을 사용하여 데이터 형식에 맞지 않는 너무 큰 `Integer` 정수를 포함합니다.

`Long`의 기본값은 0입니다.

## <a name="literal-assignments"></a>리터럴 할당

소수점 문자, 육각 형 리터럴, 옥탈 리터럴 또는 (Visual Basic 2017로 시작) 이진 리터럴을 할당하여 `Long` 변수를 선언하고 초기화 할 수 있습니다. 정수 리터럴이 `Long` 범위를 벗어나는 경우(즉 <xref:System.Int64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 4,294,967,296과 같은 정수가 `Long` 값에 할당됩니다.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> 접두사를 `&h` 사용하거나 `&H` 육각 문자 문자, `&b` 접두사 또는 이진 `&B` 리터럴을 나타내거나 접두사를 `&o` 나타내거나 `&O` 팔각형 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터는 다음 예제와 같이 `_`밑줄 문자를 숫자 구분 기호로 사용하여 가독성을 향상시킬 수도 있습니다.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Visual Basic 15.5부터는 접두사와 육각형, 이진 또는 옥탈 숫자 사이의 선행 구분 기호로 밑줄 문자()를`_`사용할 수도 있습니다. 다음은 그 예입니다.

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

숫자 리터럴은 다음 예제와 `L` 같이 `Long` 데이터 형식을 나타내는 형식 [문자를](../../programming-guide/language-features/data-types/type-characters.md) 포함할 수도 있습니다.

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>프로그래밍 팁

- **Interop 고려 사항.** .NET Framework(예: 자동화 또는 COM 개체)에 대해 작성되지 않은 `Long` 구성 요소와 인터페이싱하는 경우 다른 환경에서는 데이터 너비(32비트)가 다르다는 것을 기억하십시오. 이러한 구성 요소에 32비트 인수를 전달하는 경우 새 `Integer` Visual `Long` Basic 코드 대신선언합니다.

- **확대.** 데이터 `Long` 형식은 `Decimal`을 `Single`로 `Double`확장합니다. 이는 `Long` 오류 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType>를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.

- **문자를 입력합니다.** 리터럴 형식 문자 `L`를 리터럴에 추가하면 `Long` 데이터 형식이 됩니다. 식별자 형식 문자 `&`를 식별자에 추가하면 `Long`가 됩니다.

- **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Int64?displayProperty=nameWithType> 구조체입니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Int64>
- [데이터 유형](../../../visual-basic/language-reference/data-types/index.md)
- [정수 데이터 유형](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Short 데이터 형식](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
