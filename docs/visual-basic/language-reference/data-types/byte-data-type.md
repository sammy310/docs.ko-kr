---
title: Byte 데이터 형식
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344073"
---
# <a name="byte-data-type-visual-basic"></a>Byte 데이터 형식 (Visual Basic)

0에서 255 사이의 값 범위에 해당 하는 부호 없는 8 비트 (1 바이트) 정수를 저장 합니다.

## <a name="remarks"></a>주의

`Byte` 데이터 형식을 사용 하 여 이진 데이터를 포함 합니다.  
  
`Byte`의 기본값은 0입니다.

## <a name="literal-assignments"></a>리터럴 할당

10 진수 리터럴, 16 진수 리터럴, 8 진수 리터럴 또는 (2017 Visual Basic부터) 이진 리터럴을 할당 하 여 `Byte` 변수를 선언 하 고 초기화할 수 있습니다. 정수 리터럴이 `Byte` 범위 밖에 있는 경우 즉, <xref:System.Byte.MinValue?displayProperty=nameWithType> 보다 작거나 <xref:System.Byte.MaxValue?displayProperty=nameWithType>보다 큰 경우 컴파일 오류가 발생 합니다.

다음 예제에서는 10 진수, 16 진수 및 이진 리터럴로 표현 된 201와 동일한 정수를 암시적으로 [정수](integer-data-type.md) 에서 `byte` 값으로 변환 합니다.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> `&h` 또는 `&H` 접두사를 사용 하 여 16 진수 리터럴을 나타내고, 접두사 `&b` 또는 `&B`를 사용 하 여 이진 리터럴을 표시 하 고, 접두사 `&o` 또는 `&O`을 사용 하 여 8 진수 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터 다음 예제에 나와 있는 것 처럼 밑줄 문자 `_`를 자릿수 구분 기호로 사용 하 여 가독성을 높일 수도 있습니다.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Visual Basic 15.5부터 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 밑줄 문자 (`_`)를 사용할 수도 있습니다. 예를 들면 다음과 같습니다.

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>프로그래밍 팁

- **음수.** `Byte`는 부호 없는 형식이 기 때문에 음수를 나타낼 수 없습니다. `Byte`형식을 반환 하는 식에 단항 빼기 (`-`) 연산자를 사용 하는 경우 Visual Basic 식을 먼저 `Short` 변환 합니다.
  
- **형식 변환.** Visual Basic 파일을 읽거나 쓸 때 또는 Dll, 메서드 및 속성을 호출 하는 경우 데이터 형식 간에 자동으로 변환할 수 있습니다. `Byte` 변수와 배열에 저장 된 이진 데이터는 이러한 형식 변환 중에 보존 됩니다. ANSI 및 유니코드 형식 간에 변환 하는 동안 해당 내용이 손상 될 수 있으므로 이진 데이터에는 `String` 변수를 사용 하면 안 됩니다.

- **넓혀.** `Byte` 데이터 형식은 `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`또는 `Double`로 확대 변환 됩니다. 즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 발생 하지 않고 `Byte`를 이러한 형식으로 변환할 수 있습니다.
  
- **문자를 입력 합니다.** `Byte`에는 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.

- **프레임 워크 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.Byte?displayProperty=nameWithType> 구조체입니다.

## <a name="example"></a>예제

 다음 예에서는 `b` `Byte` 변수입니다. 문은 변수의 범위와 비트 시프트 연산자의 응용 프로그램을 보여 줍니다.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>참고 항목

- <xref:System.Byte?displayProperty=nameWithType>
- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
