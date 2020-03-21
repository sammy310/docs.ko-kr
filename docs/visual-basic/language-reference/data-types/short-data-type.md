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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401342"
---
# <a name="short-data-type-visual-basic"></a>짧은 데이터 유형(비주얼 베이직)

-32,768에서 32,767까지의 가치가 있는 16비트(2바이트) 정수를 보유합니다.  
  
## <a name="remarks"></a>설명  

 `Short` 데이터 형식을 사용하여 `Integer`의 전체 데이터 너비가 필요하지 않은 정수 값을 포함합니다. 경우에 따라 공통 언어 런타임으로 `Short` 변수를 밀접하게 압축하고 메모리 소비를 줄일 수 있습니다.  
  
 `Short`의 기본값은 0입니다.  
  
## <a name="literal-assignments"></a>리터럴 할당

소수점 문자, 육각 형 리터럴, 옥탈 리터럴 또는 (Visual Basic 2017로 시작) 이진 리터럴을 할당하여 `Short` 변수를 선언하고 초기화 할 수 있습니다. 정수 리터럴이 `Short` 범위를 벗어나는 경우(즉 <xref:System.Int16.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int16.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서 소수점, 육각형 및 이진 리터럴로 표시되는 정수는 1,034와 같으며 이진 리터럴은 [정수에서](integer-data-type.md) 값으로 `Short` 암시적으로 변환됩니다.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> 접두사를 `&h` 사용하거나 `&H` 육각 문자 문자, `&b` 접두사 또는 이진 `&B` 리터럴을 나타내거나 접두사를 `&o` 나타내거나 `&O` 팔각형 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터는 다음 예제와 같이 `_`밑줄 문자를 숫자 구분 기호로 사용하여 가독성을 향상시킬 수도 있습니다.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

Visual Basic 15.5부터는 접두사와 육각형, 이진 또는 옥탈 숫자 사이의 선행 구분 기호로 밑줄 문자()를`_`사용할 수도 있습니다. 다음은 그 예입니다.

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

숫자 리터럴은 다음 예제와 `S` 같이 `Short` 데이터 형식을 나타내는 형식 [문자를](../../programming-guide/language-features/data-types/type-characters.md) 포함할 수도 있습니다.

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>프로그래밍 팁

- **확대.** 데이터 `Short` 형식은 `Integer`" `Long` `Decimal`을 `Single`로 `Double`확대합니다. 이는 `Short` 오류 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType>를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.  
  
- **문자를 입력합니다.** 리터럴 형식 문자 `S`를 리터럴에 추가하면 `Short` 데이터 형식이 됩니다. `Short`식별자 유형 문자가 없습니다.  
  
- **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Int16?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Int16?displayProperty=nameWithType>
- [데이터 유형](../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [정수 데이터 유형](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Long 데이터 형식](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
