---
description: '자세한 정보: UShort 데이터 형식 (Visual Basic)'
title: UShort 데이터 형식
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
ms.openlocfilehash: 43c18bad3e24e14c28d2ca3d5d88170d584e55a8
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106646"
---
# <a name="ushort-data-type-visual-basic"></a>UShort 데이터 형식 (Visual Basic)

0에서 65535 사이의 값에 해당 하는 부호 없는 16 비트 (2 바이트) 정수를 저장 합니다.  
  
## <a name="remarks"></a>설명

 `UShort`에 대해 너무 크지 않은 이진 데이터를 포함 하려면 데이터 형식을 사용 `Byte` 합니다.  
  
 `UShort`의 기본값은 0입니다.  

## <a name="literal-assignments"></a>리터럴 할당

`UShort`10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (Visual Basic 2017부터) 이진 리터럴을 할당 하 여 변수를 선언 하 고 초기화할 수 있습니다. 정수 리터럴이 `UShort` 범위를 벗어나는 경우(즉 <xref:System.UInt16.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt16.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서는 10 진수, 16 진수 및 이진 리터럴로 표현 된 65034와 동일한 정수가 값에 할당 됩니다 `UShort` .
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> 접두사 또는를 사용 하 여 `&h` `&H` 16 진수 리터럴을 표시 하거나, 접두사 또는을 사용 하 여 이진 리터럴을 표시 하 고, 접두사 또는를 사용 하 여 `&b` `&B` `&o` `&O` 8 진수 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터 `_` 다음 예제와 같이 밑줄 문자를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

Visual Basic 15.5부터 `_` 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 ()를 사용할 수도 있습니다. 다음은 그 예입니다. 

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

`US`다음 예제와 같이 숫자 리터럴은 또는 `us` [형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 를 포함 하 여 데이터 형식을 나타낼 수도 있습니다 `UShort` .

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>프로그래밍 팁
  
- **음수.** `UShort`는 부호 없는 형식이 기 때문에 음수를 나타낼 수 없습니다. `-`형식을 반환 하는 식에 단항 빼기 () 연산자를 사용 하는 경우 `UShort` Visual Basic는 식을 `Integer` 먼저 변환 합니다.  
  
- **CLS 규격.** `UShort`데이터 형식이 cls ( [공용 언어 사양](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) )의 일부가 아니므로 cls 규격 코드는이를 사용 하는 구성 요소를 사용할 수 없습니다.
  
- **넓혀.** `UShort`데이터 형식은,,,,, 및로 확대 변환 `Integer` `UInteger` `Long` `ULong` `Decimal` `Single` `Double` 됩니다. 즉, `UShort` 오류가 발생 하지 않고 이러한 형식으로 변환할 수 있습니다 <xref:System.OverflowException?displayProperty=nameWithType> .  
  
- **문자를 입력 합니다.** 리터럴 형식 문자를 리터럴에 추가 하면 `US` `UShort` 데이터 형식이 됩니다. `UShort` 에는 식별자 형식 문자가 없습니다.  
  
- **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.UInt16?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.UInt16>
- [데이터 형식](index.md)
- [형식 변환 함수](../functions/type-conversion-functions.md)
- [변환 요약](../keywords/conversion-summary.md)
- [방법: 부호 없는 형식을 사용하는 Windows 함수 호출](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [데이터 형식의 효율적 사용](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
