---
title: 문자열 함수(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 0002a3dd19b493f690f91f9b6c68a9241e6d6ea0
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582996"
---
# <a name="string-functions-visual-basic"></a>문자열 함수(Visual Basic)

다음 표에서는 문자열을 검색 하 고 조작 하기 위해 <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> 클래스에서 제공 하 Visual Basic 함수를 나열 합니다. Visual Basic 내장 함수로 간주할 수 있습니다. 즉, 예제에서 보여 주는 것 처럼 클래스의 명시적 멤버로 호출할 필요가 없습니다. @No__t_0 클래스에서 추가 메서드 및 경우에 따라 보충 메서드를 사용할 수 있습니다.

|.NET Framework 메서드|설명|
|---------------------------|-----------------|
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|문자에 해당 하는 문자 코드를 나타내는 `Integer` 값을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|지정 된 문자 코드와 연결 된 문자를 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|지정 된 필터 조건에 따라 `String` 배열의 하위 집합을 포함 하는 0부터 시작 하는 배열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|형식 `String` 식에 포함 된 명령에 따라 형식이 지정 된 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|시스템 제어판에 정의 된 통화 기호를 사용 하 여 통화 값으로 서식이 지정 된 식을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|날짜/시간 값을 나타내는 문자열 식을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|숫자로 서식이 지정 된 식을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|백분율로 서식이 지정된 식(100을 곱함)을 % 문자를 붙여 반환합니다.|
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|한 문자열이 다른 문자열 내에서 처음으로 나타나는 시작 위치를 지정 하는 정수를 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|문자열의 오른쪽에서 시작 하 여 다른 문자열 내에서 한 문자열의 첫 번째 발생 위치를 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|배열에 포함 된 여러 부분 문자열을 조인 하 여 만든 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|소문자로 변환 된 문자열 또는 문자를 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|문자열의 왼쪽 에서부터 지정한 수 만큼의 문자를 포함 하는 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|문자열의 문자 수를 포함 하는 정수를 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|지정 된 길이로 조정 된 지정 된 문자열을 포함 하는 왼쪽 맞춤 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|선행 공백 없이 지정 된 문자열의 복사본을 포함 하는 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|문자열에서 지정 된 수의 문자를 포함 하는 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|지정 된 부분 문자열이 지정한 횟수 만큼 다른 부분 문자열로 바뀐 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|문자열의 오른쪽 에서부터 지정한 수 만큼의 문자를 포함 하는 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|지정 된 길이로 조정 된 지정 된 문자열을 포함 하는 오른쪽 맞춤 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|후행 공백 없이 지정 된 문자열의 복사본을 포함 하는 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|지정 된 수의 공백으로 구성 된 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|지정 된 수의 부분 문자열을 포함 하는 1 차원 배열 (0부터 시작)을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|문자열 비교의 결과에 따라-1, 0 또는 1을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|지정 된 대로 변환 된 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|지정 된 횟수 만큼 반복 되는 지정 된 문자로 구성 된 문자열 또는 개체를 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|지정 된 문자열의 문자 순서가 반대인 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|선행 또는 후행 공백이 없는 지정 된 문자열의 복사본을 포함 하는 문자열을 반환 합니다.|
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|대문자로 변환 된 지정 된 문자열을 포함 하는 문자열 또는 문자를 반환 합니다.|

[Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) 문을 사용 하 여 시스템의 로캘 (`Text`) 또는 문자의 내부 이진 표현 (`Binary`)에 따라 결정 되는 대/소문자를 구분 하지 않는 텍스트 정렬 순서를 사용 하 여 문자열을 비교할지 여부를 설정할 수 있습니다. 기본 텍스트 비교 방법은 `Binary`입니다.

## <a name="example-ucase"></a>예: UCase

이 예에서는 `UCase` 함수를 사용 하 여 문자열의 대문자 버전을 반환 합니다.
[!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]

## <a name="example-ltrim"></a>예: LTrim

이 예에서는 `LTrim` 함수를 사용 하 여 선행 공백을 제거 하 고 `RTrim` 함수를 사용 하 여 문자열 변수에서 후행 공백을 제거 합니다. @No__t_0 함수를 사용 하 여 두 가지 유형의 공백을 모두 제거 합니다.

[!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]

## <a name="example-mid"></a>예: Mid

이 예에서는 `Mid` 함수를 사용 하 여 문자열에서 지정 된 수의 문자를 반환 합니다.

[!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]

## <a name="example-len"></a>예: Len

이 예에서는 `Len`을 사용 하 여 문자열의 문자 수를 반환 합니다.

[!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]

## <a name="example-instr"></a>예: InStr

이 예에서는 `InStr` 함수를 사용 하 여 다른 문자열 내에서 한 문자열의 첫 번째 발생 위치를 반환 합니다.

[!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]

## <a name="example-format"></a>예: Format

이 예에서는 `Format` 함수를 사용 하 여 `String` 형식 및 사용자 정의 형식을 모두 사용 하 여 값의 서식을 지정 하는 다양 한 방법을 보여 줍니다. 날짜 구분 기호 (`/`), 시간 구분 기호 (`:`) 및 AM/PM 표시기 (`t` 및 `tt`)의 경우 시스템에 표시 되는 실제 형식이 지정 된 출력은 코드에서 사용 하는 로캘 설정에 따라 달라 집니다. 개발 환경에 시간과 날짜가 표시 되 면 코드 로캘의 간단한 시간 형식 및 간단한 날짜 형식이 사용 됩니다.

> [!NOTE]
> 24 시간 형식을 사용 하는 로캘의 경우 AM/PM 표시기 (`t` 및 `tt`)는 아무 것도 표시 하지 않습니다.

[!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]

## <a name="see-also"></a>참조

- [C++ 키워드](../../../visual-basic/language-reference/keywords/index.md)
- [Visual Basic 런타임 라이브러리 멤버](../../../visual-basic/language-reference/runtime-library-members.md)
- [문자열 조작 요약](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
- [System.string 클래스 메서드](xref:System.String#methods)
