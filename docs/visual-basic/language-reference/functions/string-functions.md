---
title: 문자열 함수
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 778e57eadd75baf1aabd100f9d8d41a490f79a04
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406290"
---
# <a name="string-functions-visual-basic"></a>문자열 함수(Visual Basic)

다음 표에서는 <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> 문자열을 검색 하 고 조작 하기 위해 클래스에서 제공 Visual Basic는 함수를 나열 합니다. Visual Basic 내장 함수로 간주할 수 있습니다. 즉, 예제에서 보여 주는 것 처럼 클래스의 명시적 멤버로 호출할 필요가 없습니다. 클래스에서 추가 메서드 및 경우에 따라 보충 메서드를 사용할 수 있습니다 <xref:System.String?displayProperty=nameWithType> .

|.NET Framework 메서드|Description|
|---------------------------|-----------------|
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|`Integer`문자에 해당 하는 문자 코드를 나타내는 값을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|지정한 문자 코드와 연관된 문자를 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|지정된 필터링 기준에 따라 `String` 배열의 하위 집합을 포함하는 0부터 시작하는 배열을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|형식 `String` 식에 포함된 명령에 따라 형식 지정된 문자열을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|시스템 제어판에 정의된 통화 기호를 사용하여 통화 값으로 서식이 지정된 식을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|날짜/시간 값을 나타내는 문자열 식을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|숫자로 서식이 지정된 식을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|백분율로 서식이 지정된 식(100을 곱함)을 % 문자를 붙여 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|한 문자열에서 다른 문자열이 처음으로 나타나는 위치를 지정하는 정수를 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|문자열의 오른쪽에서 시작하여 한 문자열 내에서 다른 문자열이 처음 나오는 위치를 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|배열에 포함된 여러 부분 문자열을 조인하여 작성되는 문자열을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|소문자로 변환된 문자열 또는 문자를 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|문자열의 왼쪽에서 지정한 수의 문자를 포함하는 문자열을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|문자열의 문자 수를 포함 하는 정수를 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|지정된 문자열을 지정한 길이에 맞게 조정하고 왼쪽에 맞춘 문자열을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|선행 공백 없이 지정 된 문자열의 복사본을 포함 하는 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|문자열에서 지정 된 수의 문자를 포함 하는 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|지정된 부분 문자열이 지정된 횟수만큼 다른 부분 문자열로 대체된 문자열을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|문자열의 오른쪽에서 지정한 개수의 문자를 포함하는 문자열을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|지정된 길이에 맞게 조정된 특정 문자열이 포함된 문자열(오른쪽에 맞춰진 문자열)을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|후행 공백 없이 지정 된 문자열의 복사본을 포함 하는 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|지정한 수 만큼의 공백으로 구성되는 문자열을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|지정된 수의 부분 문자열을 포함하는 0부터 시작하는 1차원 배열을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|문자열 비교의 결과에 따라 -1, 0 또는 1을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|지정된 대로 변환된 문자열을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|지정된 횟수만큼 반복되는 특정 문자로 구성된 문자열 또는 개체를 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|지정된 문자열의 문자 순서를 역순으로 한 문자열을 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|선행 또는 후행 공백이 없는 지정 된 문자열의 복사본을 포함 하는 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|대문자로 변환된 특정 문자열이 있는 문자열 또는 문자를 반환합니다.|

[Option Compare](../statements/option-compare-statement.md) 문을 사용 하 여 문자열을 대/소문자를 구분 하지 않는 텍스트 정렬 순서를 사용 하 여 비교할 수 있습니다 (). 시스템의 로캘 ( `Text` ) 또는 문자 ()의 내부 이진 표현에 따라 결정 됩니다 `Binary` . 기본 텍스트 비교 방법은 `Binary`입니다.

## <a name="example-ucase"></a>예: UCase

다음 예제에서는 `UCase` 함수를 사용하여 대문자 문자열을 반환합니다.
[!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]

## <a name="example-ltrim"></a>예: LTrim

이 예제에서는 문자열 변수에서 `LTrim` 함수를 사용하여 선행 공백을 제거하고 `RTrim` 함수를 사용하여 후행 공백을 제거하며 `Trim` 함수를 사용하여 양쪽 공백을 모두 제거합니다.

[!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]

## <a name="example-mid"></a>예: Mid

이 예에서는 함수를 사용 하 여 `Mid` 문자열에서 지정 된 수의 문자를 반환 합니다.

[!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]

## <a name="example-len"></a>예: Len

다음 예제에서는 `Len` 함수를 사용하여 문자열의 문자 개수를 반환합니다.

[!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]

## <a name="example-instr"></a>예: InStr

다음 예제에서는 `InStr` 함수를 사용하여 한 문자열 안에 다른 문자열이 처음으로 나타나는 위치를 반환합니다.

[!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]

## <a name="example-format"></a>예: Format

다음 예제에서는 `Format` 형식과 사용자 정의 형식을 모두 사용하여 값의 형식을 지정하는 `String` 함수의 다양한 사용 방법을 보여 줍니다. 날짜 구분 기호(`/`), 시간 구분 기호(`:`), AM/PM 표시기(`t` 및 `tt`)의 경우 시스템에 실제로 표시되는 출력 형식은 코드에서 사용하는 로캘 설정에 따라 달라집니다. 개발 환경에 시간과 날짜가 표시되는 경우 코드 로캘의 간단한 시간 형식과 날짜 형식이 사용됩니다.

> [!NOTE]
> 24시간 형식을 사용하는 로캘의 경우에는 AM/PM 표시기(`t`와 `tt`)에 아무것도 표시되지 않습니다.

[!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]

## <a name="see-also"></a>참고 항목

- [C++ 키워드](../keywords/index.md)
- [Visual Basic 런타임 라이브러리 멤버](../runtime-library-members.md)
- [문자열 조작 요약](../keywords/string-manipulation-summary.md)
- [System.string 클래스 메서드](xref:System.String#methods)
