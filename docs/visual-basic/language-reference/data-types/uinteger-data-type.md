---
description: UInteger 데이터 형식에 대해 자세히 알아보세요.
title: UInteger 데이터 형식
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: c3c04f746f0e2cf15bc1881544b93a538dbdc04e
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104837"
---
# <a name="uinteger-data-type"></a>UInteger 데이터 형식

0에서 4294967295 사이의 값에 해당 하는 부호 없는 32 비트 (4 바이트) 정수를 저장 합니다.

## <a name="remarks"></a>설명

`UInteger`데이터 형식은 가장 효율적인 데이터 너비의 가장 큰 부호 없는 값을 제공 합니다.

`UInteger`의 기본값은 0입니다.

## <a name="literal-assignments"></a>리터럴 할당

`UInteger`10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (Visual Basic 2017부터) 이진 리터럴을 할당 하 여 변수를 선언 하 고 초기화할 수 있습니다. 정수 리터럴이 `UInteger` 범위를 벗어나는 경우(즉 <xref:System.UInt32.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 3,000,000,000과 같은 정수가 `UInteger` 값에 할당됩니다.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> 접두사 또는를 사용 하 여 `&h` `&H` 16 진수 리터럴을 표시 하거나, 접두사 또는을 사용 하 여 이진 리터럴을 표시 하 고, 접두사 또는를 사용 하 여 `&b` `&B` `&o` `&O` 8 진수 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터 `_` 다음 예제와 같이 밑줄 문자를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

Visual Basic 15.5부터 `_` 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 ()를 사용할 수도 있습니다. 다음은 그 예입니다. 

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

`UI`다음 예제와 같이 숫자 리터럴은 또는 `ui` [형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 를 포함 하 여 데이터 형식을 나타낼 수도 있습니다 `UInteger` .

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>프로그래밍 팁

`UInteger`및 `Integer` 데이터 형식은 더 적은 비트를 사용 하는 경우에도 더 작은 정수 형식 ( `UShort` , `Short` , 및)을 사용 하 여 더 `Byte` `SByte` 적은 비트를 로드 하 고 저장 하 고 페치할 수 있으므로 32 비트 프로세서에서 최적의 성능을 제공 합니다.

- **음수.** `UInteger`는 부호 없는 형식이 기 때문에 음수를 나타낼 수 없습니다. `-`형식을 반환 하는 식에 단항 빼기 () 연산자를 사용 하는 경우 `UInteger` Visual Basic는 식을 `Long` 먼저 변환 합니다.

- **CLS 규격.** `UInteger`데이터 형식이 cls ( [공용 언어 사양](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) )의 일부가 아니므로 cls 규격 코드는이를 사용 하는 구성 요소를 사용할 수 없습니다.

- **Interop 고려 사항.** .NET Framework 용으로 작성 되지 않은 구성 요소 (예: Automation 또는 COM 개체)와 상호 작용 하는 경우와 같은 형식은 `uint` 다른 환경에서 서로 다른 데이터 너비 (16 비트)를 가질 수 있다는 점에 유의 하세요. 이러한 구성 요소에 16 비트 인수를 전달 하는 경우 `UShort` `UInteger` 관리 되는 Visual Basic 코드에서 대신로 선언 합니다.

- **넓혀.** `UInteger`데이터 형식은,,, 및로 확대 변환 `Long` `ULong` `Decimal` `Single` `Double` 됩니다. 즉, `UInteger` 오류가 발생 하지 않고 이러한 형식으로 변환할 수 있습니다 <xref:System.OverflowException?displayProperty=nameWithType> .

- **문자를 입력 합니다.** 리터럴 형식 문자를 리터럴에 추가 하면 `UI` `UInteger` 데이터 형식이 됩니다. `UInteger` 에는 식별자 형식 문자가 없습니다.

- **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.UInt32?displayProperty=nameWithType> 구조체입니다.

## <a name="see-also"></a>참고 항목

- <xref:System.UInt32>
- [데이터 형식](index.md)
- [형식 변환 함수](../functions/type-conversion-functions.md)
- [변환 요약](../keywords/conversion-summary.md)
- [방법: 부호 없는 형식을 사용하는 Windows 함수 호출](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [데이터 형식의 효율적 사용](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
