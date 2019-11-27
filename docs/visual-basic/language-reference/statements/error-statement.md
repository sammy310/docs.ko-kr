---
title: Error 문
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 668ffbc7b8db73a706c5771bb0734a77f8fc0206
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351246"
---
# <a name="error-statement"></a>Error 문
오류가 발생 한 경우를 시뮬레이션 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a>요소  
 `errornumber`  
 필수입니다. 모든 유효한 오류 번호가 될 수 있습니다.  
  
## <a name="remarks"></a>주의  
 `Error` 문은 이전 버전과의 호환성을 위해 지원 됩니다. 새 코드에서 특히 개체를 만들 때 `Err` 개체의 `Raise` 메서드를 사용 하 여 런타임 오류를 생성 합니다.  
  
 `errornumber` 정의 된 경우 `Error` 문은 `Err` 개체의 속성에 다음과 같은 기본값을 할당 한 후에 오류 처리기를 호출 합니다.  
  
|속성|값|  
|--------------|-----------|  
|`Number`|`Error` 문에 대 한 인수로 지정 된 값입니다. 모든 유효한 오류 번호가 될 수 있습니다.|  
|`Source`|현재 Visual Basic 프로젝트의 이름입니다.|  
|`Description`|지정 된 `Number`에 대 한 `Error` 함수의 반환 값에 해당 하는 문자열 식입니다 (이 문자열이 있는 경우). 문자열이 없으면 `Description`에 길이가 0 인 문자열 ("")이 포함 됩니다.|  
|`HelpFile`|적절 한 Visual Basic 도움말 파일의 정규화 된 드라이브, 경로 및 파일 이름입니다.|  
|`HelpContext`|`Number` 속성에 해당 하는 오류에 대 한 적절 한 Visual Basic 도움말 파일 컨텍스트 ID입니다.|  
|`LastDLLError`|0입니다.|  
  
 오류 처리기가 없거나 사용할 수 없는 경우에는 오류 메시지가 생성 되 고 `Err` 개체 속성에서 표시 됩니다.  
  
> [!NOTE]
> 일부 Visual Basic 호스트 응용 프로그램에서 개체를 만들 수 없습니다. 클래스 및 개체를 만들 수 있는지 여부를 확인 하려면 호스트 응용 프로그램의 설명서를 참조 하세요.  
  
## <a name="example"></a>예제  
 이 예에서는 `Error` 문을 사용 하 여 오류 번호 11을 생성 합니다.  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>요구 사항  
 **네임 스페이스:** [microsoft.visualbasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.visualbasic)  
  
## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [On Error 문](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [Resume 문](../../../visual-basic/language-reference/statements/resume-statement.md)
- [오류 메시지](../../../visual-basic/language-reference/error-messages/index.md)
