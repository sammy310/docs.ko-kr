---
title: Char 데이터 형식
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: 1ed5b19a307d094fc1d5a6bb0251c57052dc9bc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344055"
---
# <a name="char-data-type-visual-basic"></a>Char 데이터 형식(Visual Basic)

0에서 65535 사이의 값에 해당 하는 부호 없는 16 비트 (2 바이트) 코드 요소를 저장 합니다. 각 *코드 포인트*또는 문자 코드는 단일 유니코드 문자를 나타냅니다.

## <a name="remarks"></a>주의

단일 문자만 포함 해야 하며 `String`의 오버 헤드가 필요 하지 않은 경우 `Char` 데이터 형식을 사용 합니다. 경우에 따라 `Char` 요소의 배열인 `Char()`를 사용 하 여 여러 문자를 포함할 수 있습니다.

`Char`의 기본값은 코드 포인트가 0 인 문자입니다.

## <a name="unicode-characters"></a>유니코드 문자

유니코드의 처음 128 코드 요소 (0 – 127)는 표준 미국 키보드의 문자 및 기호에 해당 합니다. 이러한 첫 번째 128 코드 포인트가 ASCII 문자 집합에서 정의 하는 것과 동일 합니다. 두 번째 128 코드 요소 (128-255)는 특수 문자 (예: 라틴어 기반 영문자, 악센트, 통화 기호 및 분수)를 나타냅니다. 유니코드는 전 세계 텍스트 문자, 분음 부호, 수학 및 기술 기호를 비롯 한 다양 한 기호에 대해 나머지 코드 요소 (256-65535)를 사용 합니다.

<xref:System.Char.IsDigit%2A>와 같은 메서드를 사용 하 고 `Char` 변수에 <xref:System.Char.IsPunctuation%2A> 하 여 유니코드 분류를 확인할 수 있습니다.

## <a name="type-conversions"></a>형식 변환

Visual Basic은 `Char`와 숫자 형식 사이에서 직접 변환 되지 않습니다. <xref:Microsoft.VisualBasic.Strings.Asc%2A> 또는 <xref:Microsoft.VisualBasic.Strings.AscW%2A> 함수를 사용 하 여 `Char` 값을 해당 코드 포인트를 나타내는 `Integer`로 변환할 수 있습니다. <xref:Microsoft.VisualBasic.Strings.Chr%2A> 또는 <xref:Microsoft.VisualBasic.Strings.ChrW%2A> 함수를 사용 하 여 `Integer` 값을 해당 코드 포인트를 포함 하는 `Char` 변환할 수 있습니다.

형식 검사 스위치 ( [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md))가 on 인 경우 리터럴 형식 문자를 단일 문자 문자열 리터럴에 추가 하 여 `Char` 데이터 형식으로 식별 해야 합니다. 다음 예제에서는 이것을 보여 줍니다. `Option Strict`가 on 이므로 `charVar` 변수에 대 한 첫 번째 할당은 컴파일러 오류 [BC30512](../../misc/bc30512.md) 를 생성 합니다. `c` 리터럴 형식 문자가 리터럴을 `Char` 값으로 식별 하기 때문에 두 번째는 성공적으로 컴파일됩니다.

```vb
Option Strict On

Module CharType
    Public Sub Main()
        Dim charVar As Char

        ' This statement generates compiler error BC30512 because Option Strict is On.  
        charVar = "Z"  

        ' The following statement succeeds because it specifies a Char literal.  
        charVar = "Z"c
    End Sub
End Module
```

## <a name="programming-tips"></a>프로그래밍 팁

- **음수.** `Char`는 부호 없는 형식이 며 음수 값을 나타낼 수 없습니다. 어떤 경우 든 `Char`를 사용 하 여 숫자 값을 저장 하면 안 됩니다.

- **Interop 고려 사항** .NET Framework 용으로 작성 되지 않은 구성 요소 (예: Automation 또는 COM 개체)와 상호 작용 하는 경우에는 다른 환경에서 문자 형식의 데이터 너비 (8 비트)가 서로 다를 수 있습니다. 이러한 구성 요소에 8 비트 인수를 전달 하는 경우 새 Visual Basic 코드에서 `Char` 대신 `Byte`으로 선언 합니다.

- **넓혀.** `Char` 데이터 형식은 `String`으로 확대 됩니다. 즉, `Char`를 `String`로 변환할 수 있으며 <xref:System.OverflowException?displayProperty=nameWithType>발생 하지 않습니다.

- **문자를 입력 합니다.** 리터럴 형식 문자 `C`을 단일 문자 문자열 리터럴에 추가 하면 `Char` 데이터 형식으로 강제 적용 됩니다. `Char`에 식별자 형식 문자가 없습니다.

- **프레임 워크 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.Char?displayProperty=nameWithType> 구조체입니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [String 데이터 형식](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [방법: 부호 없는 형식을 사용하는 Windows 함수 호출](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
