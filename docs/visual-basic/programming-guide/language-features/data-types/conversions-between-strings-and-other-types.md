---
title: 문자열과 다른 형식 사이의 변환
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: ae8f7c2159191536013fafd8bfd10fb9a93fb785
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394223"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>문자열과 다른 형식 사이의 변환(Visual Basic)
숫자, `Boolean` 또는 날짜/시간 값을으로 변환할 수 있습니다 `String` . 문자열 `Boolean` `Date` 의 내용이 대상 데이터 형식의 유효한 값으로 해석 될 수 있는 경우 문자열 값에서 숫자, 또는로 역방향 방향을 변환할 수도 있습니다. 사용할 수 없는 경우 런타임 오류가 발생 합니다.  
  
 어느 방향에서 든 이러한 모든 할당에 대 한 변환은 축소 변환입니다. 형식 변환 키워드 (,,,,,,,,,,,,, `CBool` `CByte` `CDate` `CDbl` `CDec` `CInt` `CLng` `CSByte` `CShort` `CSng` `CStr` `CUInt` `CULng` `CUShort` 및 `CType` )를 사용 해야 합니다. <xref:Microsoft.VisualBasic.Strings.Format%2A>및 함수를 통해 <xref:Microsoft.VisualBasic.Conversion.Val%2A> 문자열과 숫자 간의 변환을 추가로 제어할 수 있습니다.  
  
 클래스 또는 구조체를 정의한 경우 `String` 와 클래스 또는 구조체의 형식 간에 형식 변환 연산자를 정의할 수 있습니다. 자세한 내용은 [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md)을 참조하세요.  
  
## <a name="conversion-of-numbers-to-strings"></a>숫자를 문자열로 변환  
 함수를 사용 하 여 `Format` 숫자를 서식이 지정 된 문자열로 변환할 수 있습니다. 여기에는 해당 숫자 뿐만 아니라 통화 기호 (예: `$` ), 천 단위 구분 기호 또는 *자릿수 그룹화 기호* (예:) `,` 및 소수 구분 기호 (예:)와 같은 기호에 대 한 서식 지정도 포함 될 수 있습니다 `.` . `Format`는 Windows **제어판**에 지정 된 **국가별 옵션** 설정에 따라 적절 한 기호를 자동으로 사용 합니다.  
  
 `&`다음 예제에 나와 있는 것 처럼 연결 () 연산자는 숫자를 암시적으로 문자열로 변환할 수 있습니다.  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>문자열을 숫자로 변환  
 함수를 사용 하 여 `Val` 문자열의 숫자를 숫자로 명시적으로 변환할 수 있습니다. `Val`숫자, 공백, 탭, 줄 바꿈 또는 마침표 이외의 문자가 나타날 때까지 문자열을 읽습니다. "&O" 및 "&H" 시퀀스는 번호 시스템의 밑수를 변경 하 고 검색을 종료 합니다. 에서 읽기를 중지할 때까지는 `Val` 적절 한 모든 문자를 숫자 값으로 변환 합니다. 예를 들어 다음 문은 값을 반환 합니다 `141.825` .  
  
 `Val("   14   1.825 miles")`  
  
 Visual Basic 문자열을 숫자 값으로 변환 하는 경우 Windows **제어판** 에 지정 된 **국가별 옵션** 설정을 사용 하 여 천 단위 구분 기호, 소수 구분 기호 및 통화 기호를 해석 합니다. 즉, 한 설정에서는 변환이 성공 하지만 다른 설정에는 성공 하지 못할 수 있습니다. 예를 들어 `"$14.20"` 은 영어 (미국) 로캘에서는 사용할 수 있지만 프랑스어 로캘에서는 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 형식 변환](type-conversions.md)
- [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md)
- [암시적 변환과 명시적 변환](implicit-and-explicit-conversions.md)
- [방법: Visual Basic에서 Object를 다른 형식으로 변환](how-to-convert-an-object-to-another-type.md)
- [배열 규칙](array-conversions.md)
- [데이터 형식](../../../language-reference/data-types/index.md)
- [형식 변환 함수](../../../language-reference/functions/type-conversion-functions.md)
- [세계화 및 지역화된 앱 개발](/visualstudio/ide/globalizing-and-localizing-applications)
