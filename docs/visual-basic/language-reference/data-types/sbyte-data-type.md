---
title: SByte 데이터 형식
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401384"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte 데이터 유형(비주얼 베이직)

-128에서 127까지의 값 범위의 서명된 8비트(1바이트) 정수를 보유합니다.

## <a name="remarks"></a>설명

`SByte` 데이터 형식을 사용하여 `Short`의 전체 데이터 너비 `Integer` 또는 의 절반 데이터 너비가 필요하지 않은 정수 값을 포함합니다. 경우에 따라 공통 언어 런타임으로 `SByte` 변수를 밀접하게 압축하고 메모리 소비를 줄일 수 있습니다.

`SByte`의 기본값은 0입니다.

## <a name="literal-assignments"></a>리터럴 할당

소수점 문자, 육각 형 리터럴, 옥탈 리터럴 또는 (Visual Basic 2017로 시작) 이진 리터럴을 할당하여 `SByte` 변수를 선언하고 초기화 할 수 있습니다.

다음 예제에서는 소수점, 육각형 및 이진 리터럴로 표시되는 -102와 같은 정수는 값에 `SByte` 할당됩니다. 이 예제에서는 컴파일러 `/removeintchecks` 스위치를 사용 하 고 컴파일해야 합니다.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> 접두사를 `&h` 사용하거나 `&H` 육각 문자 문자, `&b` 접두사 또는 이진 `&B` 리터럴을 나타내거나 접두사를 `&o` 나타내거나 `&O` 팔각형 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터는 다음 예제와 같이 `_`밑줄 문자를 숫자 구분 기호로 사용하여 가독성을 향상시킬 수도 있습니다.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

Visual Basic 15.5부터는 접두사와 육각형, 이진 또는 옥탈 숫자 사이의 선행 구분 기호로 밑줄 문자()를`_`사용할 수도 있습니다. 다음은 그 예입니다.

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

정수 리터럴이 `SByte` 범위를 벗어나는 경우(즉 <xref:System.SByte.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.SByte.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다. 정수 리터럴에 접미사가 없는 경우 [정수는](integer-data-type.md) 유추됩니다. 정수 리터럴이 `Integer` 형식의 범위를 벗어나면 [Long이](long-data-type.md) 유추됩니다. 즉, 이전 예제에서는 숫자 `0x9A` 리터럴이 156값을 `0b10011010` 초과하는 32비트 서명된 정수로 해석됩니다. <xref:System.SByte.MaxValue?displayProperty=nameWithType> 소수점 정수를 `SByte`할당하는 이와 같은 코드를 성공적으로 컴파일하려면 다음 중 하나를 수행할 수 있습니다.

- `/removeintchecks` 컴파일러 스위치로 컴파일하여 정수 경계 검사를 사용하지 않도록 설정합니다.

- 형식 [문자를](../../programming-guide/language-features/data-types/type-characters.md) 사용하여 `SByte`에 할당할 리터럴 값을 명시적으로 정의합니다. 다음 예제에서 에 음수 `Short` 리터럴 `SByte`값을 할당합니다. 음수의 경우 숫자 리터럴의 높은 차수 단어의 높은 순서 비트를 설정해야 합니다. 이 예제의 경우 리터럴 `Short` 값의 비트 15입니다.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>프로그래밍 팁

- **CLS 규정 준수.** `SByte` 데이터 형식은 공통 언어 [사양(CLS)의](https://www.ecma-international.org/publications/standards/Ecma-335.htm) 일부가 아니므로 CLS 호환 코드는 이를 사용하는 구성 요소를 사용할 수 없습니다.

- **확대.** 데이터 `SByte` `Short`형식은 " `Integer` `Long` `Decimal` `Single`을 로 확대합니다. `Double` 즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 `SByte` 발생하지 않고 이러한 유형으로 변환할 수 있습니다.

- **문자를 입력합니다.** `SByte`리터럴 형식 문자 또는 식별자 유형 문자가 없습니다.

- **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.SByte?displayProperty=nameWithType> 구조체입니다.

## <a name="see-also"></a>참고 항목

- <xref:System.SByte?displayProperty=nameWithType>
- [데이터 유형](../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Short 데이터 형식](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [정수 데이터 유형](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Long 데이터 형식](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
