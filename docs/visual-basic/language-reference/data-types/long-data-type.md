---
description: '자세한 정보: Long 데이터 형식 (Visual Basic)'
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
ms.openlocfilehash: cb4a22fa3b9d1440f755c8a3412aa3a918b7f261
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792182"
---
# <a name="long-data-type-visual-basic"></a>Long 데이터 형식 (Visual Basic)

-9223372036854775808에서 9223372036854775807 (9.2 ... E + 18) 까지의 값 범위에 해당 하는 부호 있는 64 비트 (8 바이트) 정수를 저장 합니다.

## <a name="remarks"></a>설명

데이터 형식을 사용 하 여 `Long` 너무 커서 데이터 형식에 맞지 않는 정수를 포함할 수 `Integer` 있습니다.

`Long`의 기본값은 0입니다.

## <a name="literal-assignments"></a>리터럴 할당

`Long`10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (Visual Basic 2017부터) 이진 리터럴을 할당 하 여 변수를 선언 하 고 초기화할 수 있습니다. 정수 리터럴이 `Long` 범위를 벗어나는 경우(즉 <xref:System.Int64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 4,294,967,296과 같은 정수가 `Long` 값에 할당됩니다.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> 접두사 또는를 사용 하 여 `&h` `&H` 16 진수 리터럴을 표시 하거나, 접두사 또는을 사용 하 여 이진 리터럴을 표시 하 고, 접두사 또는를 사용 하 여 `&b` `&B` `&o` `&O` 8 진수 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터 `_` 다음 예제와 같이 밑줄 문자를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Visual Basic 15.5부터 `_` 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 ()를 사용할 수도 있습니다. 다음은 그 예입니다. 

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

`L`다음 예제와 같이 숫자 리터럴은 [형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 를 포함 하 여 데이터 형식을 나타낼 수도 있습니다 `Long` .

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>프로그래밍 팁

- **Interop 고려 사항.** .NET Framework 용으로 작성 되지 않은 구성 요소 (예: Automation 또는 COM 개체)와 상호 작용 하는 경우 `Long` 다른 환경에서는의 데이터 너비 (32 비트)가 다르다는 점에 주의 해야 합니다. 이러한 구성 요소에 32 비트 인수를 전달 하는 경우 `Integer` `Long` 새 Visual Basic 코드에서 대신로 선언 합니다.

- **넓혀.** `Long`데이터 형식은, 또는로 확대 변환 `Decimal` `Single` `Double` 됩니다. 이는 `Long` 오류 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType>를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.

- **문자를 입력 합니다.** 리터럴 형식 문자 `L`를 리터럴에 추가하면 `Long` 데이터 형식이 됩니다. 식별자 형식 문자 `&`를 식별자에 추가하면 `Long`가 됩니다.

- **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Int64?displayProperty=nameWithType> 구조체입니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Int64>
- [데이터 형식](index.md)
- [Integer 데이터 형식](integer-data-type.md)
- [Short 데이터 형식](short-data-type.md)
- [형식 변환 함수](../functions/type-conversion-functions.md)
- [변환 요약](../keywords/conversion-summary.md)
- [데이터 형식의 효율적 사용](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
