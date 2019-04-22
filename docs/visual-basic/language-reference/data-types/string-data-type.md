---
title: String 데이터 형식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
ms.openlocfilehash: 3e87dc6527b4351467b1155439ee8266157c16ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842293"
---
# <a name="string-data-type-visual-basic"></a>String 데이터 형식(Visual Basic)
0에서 65535 사이의 값의 부호 없는 16 비트 (2 바이트) 코드 포인트 순서 범위를 가집니다. 각 *코드 포인트*, 또는 문자 코드를 단일 유니코드 문자를 나타냅니다. 0에서 약 두 십억 문자열을 포함할 수 있습니다 (2 ^31) 유니코드 문자입니다.  
  
## <a name="remarks"></a>설명  
 사용 된 `String` 배열 관리 오버 헤드 없이 여러 문자를 저장할 데이터 형식 `Char()`, 배열을 `Char` 요소.  
  
 기본값인 `String` 는 `Nothing` (null 참조). 이 하지 빈 문자열과 같은 (값 `""`).  
  
## <a name="unicode-characters"></a>유니코드 문자  
 유니코드는 첫 번째 128 개 코드 포인트 (0 ~ 127) 문자와 미국 표준 키보드의 기호에 해당 합니다. 이러한 128 개 코드 포인트는 ASCII 문자 집합을 정의 하는 것과 동일 합니다. 두 번째 128 개 코드 포인트 (128-255)는 라틴 문자 기반의 알파벳 문자, 악센트, 통화 기호 및 소수와 같은 특수 문자를 나타냅니다. 유니코드 기호의 다양 한 나머지 코드 포인트 (256-65535)를 사용합니다. 전 세계 텍스트 문자, 분음 부호, 및 수학 및 공학 기호 포함 됩니다.  
  
 와 같은 메서드를 사용할 수 있습니다 <xref:System.Char.IsDigit%2A> 하 고 <xref:System.Char.IsPunctuation%2A> 의 개별 문자에는 `String` 유니코드 분류를 결정 하는 변수입니다.  
  
## <a name="format-requirements"></a>형식 요구 사항  
 묶어야를 `String` 리터럴은 따옴표 (`" "`). 두 개의 연속 된 따옴표를 사용 하는 문자열의 문자 중 하나로 따옴표를 포함 해야 합니다 (`""`). 다음은 이에 대한 예입니다.  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 문자열에 인용 부호를 나타내는 연속 따옴표는 시작 및 종료 하는 따옴표와 무관 합니다 `String` 리터럴.  
  
## <a name="string-manipulations"></a>문자열 조작  
 문자열을 할당 한 후에 `String` 변수를 해당 문자열은 *변경할 수 없는*, 길이 또는 내용을 변경할 수 없습니다. 즉. 어떤 방식으로 문자열을 변경 하면 Visual Basic 새 문자열을 만들고 이전 것을 중단 합니다. `String` 변수는 다음 새 문자열을 가리킵니다.  
  
 콘텐츠를 조작할 수는 `String` 다양 한 문자열 함수를 사용 하 여 변수입니다. 다음 예제는 <xref:Microsoft.VisualBasic.Strings.Left%2A> 함수  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 다른 구성 요소에서 만든 문자열 선행 또는 후행 공백을 채워질 수 있습니다. 이러한 문자열을 수신 하는 경우 사용할 수 있습니다 합니다 <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, 및 <xref:Microsoft.VisualBasic.Strings.RTrim%2A> 이러한 공백을 제거 하는 함수입니다.  
  
 문자열 조작에 대 한 자세한 내용은 참조 하세요. [문자열](../../../visual-basic/programming-guide/language-features/strings/index.md)합니다.  
  
## <a name="programming-tips"></a>프로그래밍 팁  
  
-   **음수를 사용할 수 있습니다.** 문자를 소유 해야 `String` 부호 없는 및 음수 값을 나타낼 수 없습니다. 사용 하지 않아야 어떤 경우 든 `String` 숫자 값을 포함 하도록 합니다.  
  
-   **Interop 고려 사항입니다.** .NET Framework 용으로 작성 되지 구성 요소와 상호 작용 하는 경우 Automation 또는 COM 개체를 해야 문자열 문자를 다른 데이터 너비 (8 비트)에 있는 다른 환경에서. 이러한 구성 요소 8 비트 문자의 문자열 인수를 전달 하는 경우로 선언 `Byte()`, 배열을 `Byte` 요소 대신 `String` 새 Visual Basic 코드에서.  
  
-   **형식 문자입니다.** 식별자 형식 문자를 추가 `$` 모든 식별자를 리터럴에 `String` 데이터 형식입니다. `String` 에 리터럴 형식 문자가 없습니다. 컴파일러는 따옴표로 묶인 리터럴을 처리 하는 반면 (`" "`)으로 `String`입니다.  
  
-   **Framework 형식입니다.** .NET Framework의 해당 형식은 <xref:System.String?displayProperty=nameWithType> 클래스입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.String?displayProperty=nameWithType>
- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [Char 데이터 형식](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [방법: 부호 없는 형식을 사용하는 Windows 함수 호출](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
