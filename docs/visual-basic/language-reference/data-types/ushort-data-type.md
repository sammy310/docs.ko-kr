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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343861"
---
# <a name="ushort-data-type-visual-basic"></a>UShort 데이터 형식 (Visual Basic)

0에서 65535 사이의 값에 해당 하는 부호 없는 16 비트 (2 바이트) 정수를 저장 합니다.  
  
## <a name="remarks"></a>주의

 `UShort` 데이터 형식을 사용 하 여 `Byte`에 비해 너무 많은 이진 데이터를 포함 합니다.  
  
 `UShort`의 기본값은 0입니다.  

## <a name="literal-assignments"></a>리터럴 할당

10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (2017 Visual Basic부터) 이진 리터럴을 할당 하 여 `UShort` 변수를 선언 하 고 초기화할 수 있습니다. 정수 리터럴이 `UShort` 범위를 벗어나는 경우(즉 <xref:System.UInt16.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt16.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서는 10 진수, 16 진수 및 이진 리터럴로 표현 된 65034와 동일한 정수를 `UShort` 값에 할당 합니다.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> `&h` 또는 `&H` 접두사를 사용 하 여 16 진수 리터럴을 나타내고, 접두사 `&b` 또는 `&B`를 사용 하 여 이진 리터럴을 표시 하 고, 접두사 `&o` 또는 `&O`을 사용 하 여 8 진수 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터 다음 예제에 나와 있는 것 처럼 밑줄 문자 `_`를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

Visual Basic 15.5부터 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 (`_`)를 사용할 수도 있습니다. 예를 들면 다음과 같습니다.

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

숫자 리터럴은 `US` 또는 `us` [형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 를 포함 하 여 다음 예제와 같이 `UShort` 데이터 형식을 나타낼 수도 있습니다.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>프로그래밍 팁
  
- **음수.** `UShort`는 부호 없는 형식이 기 때문에 음수를 나타낼 수 없습니다. `UShort`형식을 반환 하는 식에 단항 빼기 (`-`) 연산자를 사용 하는 경우 Visual Basic 식을 먼저 `Integer` 변환 합니다.  
  
- **CLS 규격.** `UShort` 데이터 형식은 cls ( [공용 언어 사양](https://www.ecma-international.org/publications/standards/Ecma-335.htm) )의 일부가 아니므로 cls 규격 코드는이를 사용 하는 구성 요소를 사용할 수 없습니다.
  
- **넓혀.** `UShort` 데이터 형식은 `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`및 `Double`로 확대 변환 됩니다. 즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 발생 하지 않고 `UShort`를 이러한 형식으로 변환할 수 있습니다.  
  
- **문자를 입력 합니다.** 리터럴 형식 문자 `US`을 리터럴에 추가 하면 `UShort` 데이터 형식으로 강제 적용 됩니다. `UShort`에 식별자 형식 문자가 없습니다.  
  
- **프레임 워크 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.UInt16?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.UInt16>
- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [방법: 부호 없는 형식을 사용하는 Windows 함수 호출](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
