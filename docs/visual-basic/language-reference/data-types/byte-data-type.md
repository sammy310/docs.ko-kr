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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401354"
---
# <a name="byte-data-type-visual-basic"></a>바이트 데이터 유형(비주얼 베이직)

0에서 255까지의 값 범위의 서명되지 않은 8비트(1바이트) 정수를 보유합니다.

## <a name="remarks"></a>설명

`Byte` 데이터 형식을 사용하여 이진 데이터를 포함합니다.  
  
`Byte`의 기본값은 0입니다.

## <a name="literal-assignments"></a>리터럴 할당

소수점 문자, 육각 형 리터럴, 옥탈 리터럴 또는 (Visual Basic 2017로 시작) 이진 리터럴을 할당하여 `Byte` 변수를 선언하고 초기화 할 수 있습니다. 정수 리터럴이 a의 `Byte` 범위를 벗어나면(즉, 보다 <xref:System.Byte.MinValue?displayProperty=nameWithType> 크거나 <xref:System.Byte.MaxValue?displayProperty=nameWithType>큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서는 소수점, 육각형 및 이진 리터럴로 표시되는 201과 같은 정수는 [정수에서](integer-data-type.md) 값으로 `byte` 암시적으로 변환됩니다.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> 접두사를 `&h` 사용하거나 `&H` 육각 문자 문자, `&b` 접두사 또는 이진 `&B` 리터럴을 나타내거나 접두사를 `&o` 나타내거나 `&O` 팔각형 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017부터는 다음 예제와 같이 `_`밑줄 문자를 숫자 구분 기호로 사용하여 가독성을 향상시킬 수도 있습니다.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Visual Basic 15.5부터는 접두사와 육각형, 이진 또는 옥탈 숫자 사이의 선행 구분 기호로 밑줄 문자()를`_`사용할 수도 있습니다. 다음은 그 예입니다.

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>프로그래밍 팁

- **음수.** 서명되지 않은 형식이기 때문에 `Byte` 음수를 나타낼 수 없습니다. 입력을`-` `Byte`평가하는 식에서 unary 빼기 () 연산자를 사용하는 경우 `Short` Visual Basic은 식을 먼저 변환합니다.
  
- **형식 변환.** Visual Basic이 파일을 읽거나 쓰거나 DLL, 메서드 및 속성을 호출할 때 데이터 형식 간에 자동으로 변환할 수 있습니다. 변수 및 `Byte` 배열에 저장된 이진 데이터는 이러한 형식 변환 중에 유지됩니다. ANSI와 `String` 유니코드 형식을 변환하는 동안 내용이 손상될 수 있으므로 이진 데이터에 변수를 사용해서는 안 됩니다.

- **확대.** 데이터 `Byte` 형식은 `Short` `UShort`" `Integer` `UInteger` `Long` `ULong` `Decimal`에 대해 , " `Single` `Double` 즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 `Byte` 발생하지 않고 이러한 유형으로 변환할 수 있습니다.
  
- **문자를 입력합니다.** `Byte`리터럴 형식 문자 또는 식별자 유형 문자가 없습니다.

- **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Byte?displayProperty=nameWithType> 구조체입니다.

## <a name="example"></a>예제

 다음 예제에서는 `b` 변수입니다. `Byte` 문은 변수의 범위와 비트 시프트 연산자의 적용을 보여 줍니다.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>참고 항목

- <xref:System.Byte?displayProperty=nameWithType>
- [데이터 유형](../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
