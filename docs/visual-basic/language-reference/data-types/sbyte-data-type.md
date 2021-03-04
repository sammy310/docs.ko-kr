---
description: '자세한 정보: SByte 데이터 형식 (Visual Basic)'
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
ms.openlocfilehash: a6a63ec742cf4a93080c9cc2f9906c5c6c21f0a8
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102102895"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte 데이터 형식 (Visual Basic)

-128부터 127 까지의 값 범위에 해당 하는 부호 있는 8 비트 (1 바이트) 정수를 저장 합니다.

## <a name="remarks"></a>설명

`SByte`데이터 형식을 사용 하 여 전체 데이터 너비를 요구 하지 않는 정수 값을 포함 `Integer` 하거나의 데이터 너비의 절반에 해당 하는 정수 값을 포함 합니다 `Short` . 경우에 따라 공용 언어 런타임은 변수를 긴밀 하 게 압축 하 고 메모리 사용을 줄일 수 있습니다 `SByte` .

`SByte`의 기본값은 0입니다.

## <a name="literal-assignments"></a>리터럴 할당

`SByte`10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (Visual Basic 2017부터) 이진 리터럴을 할당 하 여 변수를 선언 하 고 초기화할 수 있습니다.

다음 예제에서는 10 진수, 16 진수 및 이진 리터럴로 표시 되는-102와 동일한 정수가 값에 할당 됩니다 `SByte` . 이 예제를 사용 하려면 컴파일러 스위치를 사용 하 여 컴파일해야 `/removeintchecks` 합니다.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> 접두사 또는를 사용 하 여 `&h` `&H` 16 진수 리터럴을 표시 하거나, 접두사 또는을 사용 하 여 이진 리터럴을 표시 하 고, 접두사 또는를 사용 하 여 `&b` `&B` `&o` `&O` 8 진수 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터 `_` 다음 예제와 같이 밑줄 문자를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

Visual Basic 15.5부터 `_` 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 ()를 사용할 수도 있습니다. 다음은 그 예입니다. 

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

정수 리터럴이 `SByte` 범위를 벗어나는 경우(즉 <xref:System.SByte.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.SByte.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다. 정수 리터럴에 접미사가 없으면 [정수가](integer-data-type.md) 유추 됩니다. 정수 리터럴이 형식의 범위를 벗어나면 `Integer` [Long](long-data-type.md) 이 유추 됩니다. 즉, 앞의 예제에서 숫자 리터럴 및은 값이 `0x9A` `0b10011010` 156 인 32 비트 부호 있는 정수로 해석 됩니다 <xref:System.SByte.MaxValue?displayProperty=nameWithType> . Decimal이 아닌 정수를에 할당 하는 것과 같은 코드를 성공적으로 컴파일하려면 `SByte` 다음 중 하나를 수행할 수 있습니다.

- 컴파일러 스위치를 사용 하 여 컴파일하여 정수 범위 검사를 사용 하지 않도록 설정 `/removeintchecks` 합니다.

- [형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 를 사용 하 여에 할당 하려는 리터럴 값을 명시적으로 정의 `SByte` 합니다. 다음 예에서는에 음수 리터럴 값을 할당 합니다 `Short` `SByte` . 음수의 경우 숫자 리터럴의 상위 단어에 대 한 상위 비트를 설정 해야 합니다. 이 예제의 경우 리터럴 값의 비트는 15입니다 `Short` .

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>프로그래밍 팁

- **CLS 규격.** `SByte`데이터 형식이 cls ( [공용 언어 사양](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) )의 일부가 아니므로 cls 규격 코드는이를 사용 하는 구성 요소를 사용할 수 없습니다.

- **넓혀.** `SByte`데이터 형식은,,,, 및로 확대 변환 `Short` `Integer` `Long` `Decimal` `Single` `Double` 됩니다. 즉, `SByte` 오류가 발생 하지 않고 이러한 형식으로 변환할 수 있습니다 <xref:System.OverflowException?displayProperty=nameWithType> .

- **문자를 입력 합니다.** `SByte` 에는 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.

- **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.SByte?displayProperty=nameWithType> 구조체입니다.

## <a name="see-also"></a>참고 항목

- <xref:System.SByte?displayProperty=nameWithType>
- [데이터 형식](index.md)
- [형식 변환 함수](../functions/type-conversion-functions.md)
- [변환 요약](../keywords/conversion-summary.md)
- [Short 데이터 형식](short-data-type.md)
- [Integer 데이터 형식](integer-data-type.md)
- [Long 데이터 형식](long-data-type.md)
- [데이터 형식의 효율적 사용](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
