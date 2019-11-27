---
title: Short 데이터 형식
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: 8dfdfb56de32e4b3a96729b09ccf46a6fee9a424
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343932"
---
# <a name="short-data-type-visual-basic"></a>Short 데이터 형식 (Visual Basic)

-32768부터 32767 까지의 값 범위에 해당 하는 부호 있는 16 비트 (2 바이트) 정수를 저장 합니다.  
  
## <a name="remarks"></a>주의  

 `Short` 데이터 형식을 사용 하 여 `Integer`의 전체 데이터 너비가 필요 하지 않은 정수 값을 포함 합니다. 경우에 따라 공용 언어 런타임에서 `Short` 변수를 긴밀 하 게 함께 압축 하 고 메모리 사용을 줄일 수 있습니다.  
  
 `Short`의 기본값은 0입니다.  
  
## <a name="literal-assignments"></a>리터럴 할당

10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (2017 Visual Basic부터) 이진 리터럴을 할당 하 여 `Short` 변수를 선언 하 고 초기화할 수 있습니다. 정수 리터럴이 `Short` 범위를 벗어나는 경우(즉 <xref:System.Int16.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int16.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서는 10 진수, 16 진수 및 이진 리터럴로 표현 된 1034와 동일한 정수를 암시적으로 [정수](integer-data-type.md) 에서 `Short` 값으로 변환 합니다.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> `&h` 또는 `&H` 접두사를 사용 하 여 16 진수 리터럴을 나타내고, 접두사 `&b` 또는 `&B`를 사용 하 여 이진 리터럴을 표시 하 고, 접두사 `&o` 또는 `&O`을 사용 하 여 8 진수 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터 다음 예제에 나와 있는 것 처럼 밑줄 문자 `_`를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

Visual Basic 15.5부터 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 (`_`)를 사용할 수도 있습니다. 예를 들면 다음과 같습니다.

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

다음 예제와 같이 숫자 리터럴은 `Short` 데이터 형식을 나타내는 `S` [형식 문자](../../programming-guide/language-features/data-types/type-characters.md) 를 포함할 수도 있습니다.

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>프로그래밍 팁

- **넓혀.** `Short` 데이터 형식은 `Integer`, `Long`, `Decimal`, `Single`또는 `Double`로 확대 변환 됩니다. 이는 `Short` 오류 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType>를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.  
  
- **문자를 입력 합니다.** 리터럴 형식 문자 `S`를 리터럴에 추가하면 `Short` 데이터 형식이 됩니다. `Short`에 식별자 형식 문자가 없습니다.  
  
- **프레임 워크 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.Int16?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Int16?displayProperty=nameWithType>
- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Integer 데이터 형식](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Long 데이터 형식](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
