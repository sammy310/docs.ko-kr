---
title: 상수 및 열거형
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
ms.openlocfilehash: 60cd1ddac9bca685ddc5778e7d289710245a183e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374488"
---
# <a name="constants-and-enumerations-visual-basic"></a>상수 및 열거형 (Visual Basic)

Visual Basic는 개발자를 위해 미리 정의 된 많은 상수 및 열거형을 제공 합니다. 상수는 응용 프로그램 실행 전체에서 일정 하 게 유지 되는 값을 저장 합니다. 열거형은 관련된 상수 집합으로 작업하고 이름과 상수 값을 연결하는 편리한 방법을 제공합니다.  
  
## <a name="constants"></a>상수  
  
### <a name="conditional-compilation-constants"></a>조건부 컴파일 상수  

 다음 표에서는 조건부 컴파일에 사용할 수 있는 미리 정의 된 상수를 나열 합니다.  
  
|**상수**|**설명**|  
|---|---|  
|`CONFIG`|**Configuration Manager** **활성 솔루션 구성** 상자의 현재 설정에 해당 하는 문자열입니다.|  
|`DEBUG`|`Boolean` **프로젝트 속성** 대화 상자에서 설정할 수 있는 값입니다. 기본적으로 프로젝트에 대 한 디버그 구성은를 정의 `DEBUG` 합니다. `DEBUG`가 정의 되 면 <xref:System.Diagnostics.Debug> 클래스 메서드 **는 출력** 창에 대 한 출력을 생성 합니다. 정의 되지 않은 경우 <xref:System.Diagnostics.Debug> 클래스 메서드가 컴파일되지 않으며 디버그 출력이 생성 되지 않습니다.|  
|`TARGET`|프로젝트의 출력 형식을 나타내는 문자열 또는 명령줄 **대상** 옵션의 설정입니다. 의 가능한 값은 `TARGET` 다음과 같습니다.<br /><br /> -Windows 응용 프로그램의 경우 "winexe"입니다.<br />-"exe" (콘솔 응용 프로그램의 경우)<br />-클래스 라이브러리의 경우 "library"입니다.<br />-모듈의 경우 "module"입니다.<br />- **대상** 옵션은 Visual Studio 통합 개발 환경에서 설정할 수 있습니다. 자세한 내용은 [-target(Visual Basic)](../reference/command-line-compiler/target.md)을 참조하세요.|  
|`TRACE`|`Boolean` **프로젝트 속성** 대화 상자에서 설정할 수 있는 값입니다. 기본적으로 프로젝트에 대 한 모든 구성은를 정의 `TRACE` 합니다. `TRACE`가 정의 되 면 <xref:System.Diagnostics.Trace> 클래스 메서드 **는 출력** 창에 대 한 출력을 생성 합니다. 정의 되지 않은 경우 <xref:System.Diagnostics.Trace> 클래스 메서드가 컴파일되지 않으며 `Trace` 출력이 생성 되지 않습니다.|  
|`VBC_VER`|Visual Basic 버전 ( *주*)을 나타내는 숫자입니다. *부* 형식입니다.|  
  
### <a name="print-and-display-constants"></a>인쇄 및 표시 상수  

 인쇄 및 표시 함수를 호출 하는 경우 실제 값 대신 다음 상수를 코드에 사용할 수 있습니다.  
  
|**상수**|**설명**|  
|---|---|  
|`vbCrLf`|캐리지 리턴/줄 바꿈 문자 조합입니다.|  
|`vbCr`|캐리지 리턴 문자.|  
|`vbLf`|줄 바꿈 문자입니다.|  
|`vbNewLine`|줄 바꿈 문자입니다.|  
|`vbNullChar`|Null 문자.|  
|`vbNullString`|길이가 0 인 문자열 ("")과 같지 않습니다. 외부 프로시저를 호출 하는 데 사용 됩니다.|  
|`vbObjectError`|오류 번호입니다. 사용자 정의 오류 번호는 이 값보다 커야 합니다. 예를 들면 다음과 같습니다.<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|탭 문자.|  
|`vbBack`|백스페이스 문자.|  
|`vbFormFeed`|Microsoft Windows에서는 사용 되지 않습니다.|  
|`vbVerticalTab`|Microsoft Windows에서는 유용 하지 않습니다.|  
  
## <a name="enumerations"></a>열거형  

 다음 표에서는 Visual Basic에서 제공 하는 열거형을 나열 하 고 설명 합니다.  
  
|열거형|Description|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|<xref:Microsoft.VisualBasic.Interaction.Shell%2A> 함수를 호출할 때 호출된 프로그램에 사용할 창 스타일을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|오디오 메서드를 호출할 때 소리가 재생되는 방식을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A> 메서드를 호출할 때 확인할 역할 유형을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.CallType>|<xref:Microsoft.VisualBasic.Interaction.CallByName%2A> 함수를 호출할 때 호출되는 프로시저 형식을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|비교 함수를 호출할 때 문자열이 비교되는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.DateFormat>|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A> 함수를 호출할 때 날짜가 표시되는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.DateInterval>|날짜 관련 함수를 호출할 때 날짜 간격을 결정하고 형식을 지정하는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|삭제될 디렉터리에 파일이나 디렉터리가 포함된 경우 수행해야 하는 작업을 지정합니다.|  
|<xref:Microsoft.VisualBasic.DueDate>|금융 메서드를 호출할 때 지불 만기일을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|텍스트 필드가 구분 기호로 분리 되었는지 아니면 고정 너비 인지를 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|파일 액세스 함수를 호출할 때 사용할 파일 특성을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|날짜 관련 함수를 호출할 때 사용할 주의 첫째 요일을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|날짜 관련 함수를 호출할 때 사용할 연도의 첫째 주를 나타냅니다.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수에 의해 반환되는 메시지 상자에서 누른 단추를 나타냅니다.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수를 호출할 때 표시할 단추를 나타냅니다.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|파일 액세스 함수를 호출할 때 파일을 여는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.OpenMode>|파일 액세스 함수를 호출할 때 파일을 여는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.OpenShare>|파일 액세스 함수를 호출할 때 파일을 여는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|파일을 영구적으로 삭제할지 아니면 휴지통에 보관할지 여부를 지정합니다.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|모든 디렉터리를 검색할지 최상위 디렉터리만 검색할지 지정합니다.|  
|<xref:Microsoft.VisualBasic.TriState>|`Boolean`숫자 형식 지정 함수를 호출할 때 기본값을 사용할지 여부를 나타내는 값을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|작업 중에 사용자가 **취소** 를 클릭 하는 경우 수행할 작업을 지정 합니다.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|파일이 나 디렉터리를 복사, 삭제 또는 이동할 때 진행률 대화 상자를 표시할지 여부를 지정 합니다.|  
|<xref:Microsoft.VisualBasic.VariantType>|variant 개체의 형식을 나타내며 <xref:Microsoft.VisualBasic.Information.VarType%2A> 함수에서 반환됩니다.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|<xref:Microsoft.VisualBasic.Strings.StrConv%2A> 함수를 호출할 때 수행할 변환 형식을 나타냅니다.|  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic 언어 참조](index.md)
- [상수 개요](../programming-guide/language-features/constants-enums/constants-overview.md)
- [열거형 개요](../programming-guide/language-features/constants-enums/enumerations-overview.md)
