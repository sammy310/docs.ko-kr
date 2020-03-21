---
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
ms.openlocfilehash: 7cdbd5fb192fd5cc1be6260dcdcdb1f30cf3f865
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401312"
---
# <a name="ushort-data-type-visual-basic"></a>UShort 데이터 유형(시각적 기본)

0에서 65,535사이의 부호없는 16비트(2바이트) 정수를 보유합니다.  
  
## <a name="remarks"></a>설명

 `UShort` 데이터 형식을 사용하여 에 대한 `Byte`이진 데이터가 너무 큽에 포함됩니다.  
  
 `UShort`의 기본값은 0입니다.  

## <a name="literal-assignments"></a>리터럴 할당

소수점 문자, 육각 형 리터럴, 옥탈 리터럴 또는 (Visual Basic 2017로 시작) 이진 리터럴을 할당하여 `UShort` 변수를 선언하고 초기화 할 수 있습니다. 정수 리터럴이 `UShort` 범위를 벗어나는 경우(즉 <xref:System.UInt16.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt16.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서는 소수점, 육각형 및 이진 리터럴로 표시되는 정수는 65,034와 같으며 값에 `UShort` 할당됩니다.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> 접두사를 `&h` 사용하거나 `&H` 육각 문자 문자, `&b` 접두사 또는 이진 `&B` 리터럴을 나타내거나 접두사를 `&o` 나타내거나 `&O` 팔각형 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터는 다음 예제와 같이 `_`밑줄 문자를 숫자 구분 기호로 사용하여 가독성을 향상시킬 수도 있습니다.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

Visual Basic 15.5부터는 접두사와 육각형, 이진 또는 옥탈 숫자 사이의 선행 구분 기호로 밑줄 문자()를`_`사용할 수도 있습니다. 다음은 그 예입니다.

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

숫자 리터럴은 다음 `US` 예제와 `us` 같이 `UShort` 데이터 형식을 나타내는 문자 또는 [형식을](../../programming-guide/language-features/data-types/type-characters.md) 포함할 수도 있습니다.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>프로그래밍 팁
  
- **음수.** 서명되지 않은 형식이기 때문에 `UShort` 음수를 나타낼 수 없습니다. 입력을`-` `UShort`평가하는 식에서 unary 빼기 () 연산자를 사용하는 경우 `Integer` Visual Basic은 식을 먼저 변환합니다.  
  
- **CLS 규정 준수.** `UShort` 데이터 형식은 공통 언어 [사양(CLS)의](https://www.ecma-international.org/publications/standards/Ecma-335.htm) 일부가 아니므로 CLS 호환 코드는 이를 사용하는 구성 요소를 사용할 수 없습니다.
  
- **확대.** 데이터 `UShort` 형식은 `Integer`" `UInteger` `Long` `ULong` `Decimal` `Single`에 대해 , `Double` 즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 `UShort` 발생하지 않고 이러한 유형으로 변환할 수 있습니다.  
  
- **문자를 입력합니다.** 리터럴 형식 문자를 `US` 리터럴 문자에 적용하면 `UShort` 데이터 형식에 강제로 적용됩니다. `UShort`식별자 유형 문자가 없습니다.  
  
- **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.UInt16?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.UInt16>
- [데이터 유형](../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [방법: 부호 없는 형식을 사용하는 Windows 함수 호출](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
