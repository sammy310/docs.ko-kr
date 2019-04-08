---
title: On Error 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.OnError
helpviewer_keywords:
- Visual Basic code, control flow
- Resume Next statement [Visual Basic]
- errors [Visual Basic], trapping
- error handling, On Error statement
- Next statement [Visual Basic], On Error
- control flow [Visual Basic], branching
- Error keyword [Visual Basic]
- execution [Visual Basic], conditional
- Resume statement [Visual Basic], and On Error statement
- Error statement [Visual Basic], and On Error statement
- GoTo statement [Visual Basic], and On Error statement
- branching [Visual Basic], on error
- conditional statements [Visual Basic], On Error
- On Error statement [Visual Basic], syntax
- On keyword [Visual Basic]
- run-time errors [Visual Basic], handling
- On Error statement [Visual Basic]
ms.assetid: ff947930-fb84-40cf-bd66-1ea219561d5c
ms.openlocfilehash: 0a5a5261e6b71178adce02a5635c1f91a1469f3d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834272"
---
# <a name="on-error-statement-visual-basic"></a>On Error 문(Visual Basic)
오류 처리 루틴을 사용 하도록 설정 하 고 프로시저;에서 루틴의 위치를 지정 오류 처리 루틴을 사용 하지 않으려면 사용할 수도 있습니다.  
  
 발생 하는 모든 런타임 오류는 심각한 오류를 처리 하지: 오류 메시지가 표시 되 고 실행이 중지 됩니다.  
  
 가능한 경우 구조화 되지 않은 예외 처리를 사용 하는 것이 아니라 코드에서 처리 하는 구조화 된 예외를 사용 하는 것이 좋습니다 하며 `On Error` 문입니다. 자세한 내용은 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.  
  
> [!NOTE]
>  합니다 `Error` 키워드에도 사용 합니다 [Error 문](../../../visual-basic/language-reference/statements/error-statement.md), 이전 버전과 호환성을 위해 지원 되는 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`GoTo` `line`|에 필요한 지정 된 줄에서 시작 하는 오류 처리 루틴을 사용 하면 `line` 인수입니다. `line` 인수는 모든 줄 레이블 또는 줄 번호입니다. 런타임 오류가 발생 하는 경우 오류 처리기 활성화 될 때 지정된 된 줄에 분기를 제어 합니다. 지정된 된 줄에서와 동일한 절차에 있어야 합니다 `On Error` 문 또는 컴파일 타임 오류가 발생 합니다.|  
|`GoTo` 0|현재 프로시저에서 활성화 된 오류 처리기를 사용 하지 않도록 설정 하 고 다시 설정 `Nothing`합니다.|  
|`GoTo` -1|현재 프로시저에서 사용 가능한 예외를 사용 하지 않도록 설정 하 고 다시 설정 `Nothing`합니다.|  
|`Resume Next`|런타임 오류가 발생 하는 컨트롤 여기서 오류가 발생 하 고 해당 지점에서 실행이 계속 문 바로 다음 문으로 이동 지정 합니다. 이 양식을 사용 하 여 대신 `On Error GoTo` 개체에 액세스할 때.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  구조화 되지 않은 예외 처리를 사용 하기 보다는 가능 하면 코드에서 구조적된 예외 처리를 사용 하는 것이 좋습니다 하며 `On Error` 문입니다. 자세한 내용은 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.  
  
 "enabled" 오류 처리기가으로 켜져 있는 `On Error` 문입니다. "활성" 오류 처리기가 오류를 처리 하는 처리기를 사용 하도록 설정된 합니다.  
  
 오류 처리기가 활성 상태인 동안 오류가 발생 하는 경우 (오류 발생 간에 및 `Resume`, `Exit Sub`를 `Exit Function`, 또는 `Exit Property` 문), 현재 프로시저의 오류 처리기는 오류를 처리할 수 없습니다. 호출 하는 프로시저로 제어가 반환 됩니다.  
  
 호출 하는 프로시저에 설정 된 오류 처리기, 오류 처리에 활성화 됩니다. 오류 처리기를 호출 하는 프로시저의 활성 상태인 경우 제어가 사용 하지만 비활성화 된 오류 처리기를 찾을 때까지 이전 호출 프로시저를 통해 다시 전달 됩니다. 이러한 오류 처리기가 있으면 오류가 심각한는 실제로 발생 한 시점입니다.  
  
 오류 처리기 제어를 호출 하는 프로시저를 다시 전달 될 때마다 해당 프로시저는 현재 프로시저가 됩니다. 현재 프로시저에서 지정 된 지점에서 실행이 재개는 오류가 모든 프로시저에 오류 처리기가 처리 되 면는 `Resume` 문입니다.  
  
> [!NOTE]
>  오류 처리 루틴을 아닙니다를 `Sub` 프로시저 또는 `Function` 프로시저입니다. 이 줄 레이블 또는 줄 번호 표시 된 코드의 섹션입니다.  
  
## <a name="number-property"></a>Number 속성  
 오류 처리 루틴에서 값을 사용 합니다 `Number` 의 속성을 `Err` 오류의 원인을 확인 하는 개체입니다. 루틴을 테스트 하거나 관련 속성 값을 저장 해야 합니다 `Err` 다른 오류가 발생할 수 있습니다 하거나 오류가 발생할 수 있는 절차 앞 이라고 전에 개체입니다. 속성 값을 `Err` 개체는 가장 최근의 오류만을 반영 합니다. 관련 된 오류 메시지 `Err.Number` 에 포함 된 `Err.Description`합니다.  
  
## <a name="throw-statement"></a>Throw 문  
 사용 하 여 발생 하는 오류를 `Err.Raise` 메서드 집합을 `Exception` 의 새로 만든된 인스턴스에 대 한 속성을 <xref:System.Exception> 클래스입니다. 파생 된 예외 형식의 예외 발생을 지원 하기 위해는 `Throw` 언어 문이 지원 됩니다. 이 예외 인스턴스가 throw 되는 단일 매개 변수를 사용 합니다. 다음 예제에서는 기존 예외 처리 지원을 사용 하 여 이러한 기능을 사용할 수 있는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrErrorHandling#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#17)]  
  
 `On Error GoTo` 문을 예외 클래스에 관계 없이 모든 오류를 포착 합니다.  
  
## <a name="on-error-resume-next"></a>On Error Resume 다음  
 `On Error Resume Next` 런타임 오류를 발생 시킨 문 바로 다음 문으로 계속 하거나 포함 하는 프로시저에서 호출 바로 다음에 최신 문을 사용 하 여 실행이 넘어갑니다는 `On Error Resume Next` 문입니다. 이 문은 런타임 오류가 있더라도 계속 실행할 수 있습니다. 프로시저 내의 다른 위치로 제어를 전송 하는 것이 아니라 오류 발생 오류 처리 루틴을 배치할 수 있습니다. `On Error Resume Next` 문이 비활성화 됩니다 다른 프로시저를 호출 하는 경우 실행 해야 하므로 `On Error Resume Next` 각 문이 인라인 오류 해당 루틴 내에서 처리 하려는 경우 루틴을 호출 합니다.  
  
> [!NOTE]
>  합니다 `On Error Resume Next` 구문에 더 적합할 수 있습니다 `On Error GoTo` 다른 개체에 액세스 하는 동안 발생 한 오류를 처리 하는 경우. 검사 `Err` 각 상호 작용 후 개체를 사용 하 여 코드에서 액세스 된 개체에 대 한 합니다. 확인할 수 있는 개체의 오류 코드에 배치 `Err.Number`, 개체가 원래 오류를 생성 하는 데 뿐만 아니라 (에서 지정 된 개체 `Err.Source`).  
  
## <a name="on-error-goto-0"></a>Error GoTo 0 대  
 `On Error GoTo 0` 현재 프로시저의 오류 처리를 사용 하지 않도록 설정 합니다. 라인 0 프로시저 0 번 줄이 있는 경우에 오류 처리 코드의 시작으로 지정 하지 않습니다. 없이 `On Error GoTo 0` 문에서 오류 처리기 프로시저 종료 될 때 자동으로 비활성화 됩니다.  
  
## <a name="on-error-goto--1"></a>Error GoTo-1에서  
 `On Error GoTo -1` 현재 프로시저에서 예외를 사용 하지 않도록 설정 합니다. 절차-1 번 줄을 포함 하는 경우에-1 번 줄 오류 처리 코드의 시작으로 지정 하지 않습니다. 없이 `On Error GoTo -1` 예외가 문을 프로시저 종료 될 때 자동으로 비활성화 됩니다.  
  
 오류 처리 코드 오류가 발생 하지 않은 경우 실행을 방지 하려면 배치는 `Exit Sub`하십시오 `Exit Function`, 또는 `Exit Property` 문은 다음 조각 처럼 오류 처리 루틴을 바로 앞:  
  
 [!code-vb[VbVbalrErrorHandling#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#18)]  
  
 여기에서 오류 처리 코드가 다음과 `Exit Sub` 문 앞에 오는 및는 `End Sub` 문을 프로시저 흐름을 구분 하기 위해. 프로시저에서 아무 곳 이나 오류 처리 코드를 배치할 수 있습니다.  
  
## <a name="untrapped-errors"></a>포착된 되지 않은 오류  
 개체의 오류를 포착 되지 않은 개체는 실행 파일로 실행 중일 때 제어 응용 프로그램에 반환 됩니다. 개발 환경 내에서 포착된 되지 않은 오류는 적절 한 옵션을 설정 하는 경우에 제어 응용 프로그램에 반환 됩니다. 옵션을 디버깅 하는 동안 집합,를 설정 하는 방법 및 호스트 클래스를 만들 수 있는지 여부 수에 대 한 호스트 응용 프로그램의 설명서를 참조 하세요.  
  
 다른 개체에 액세스 하는 개체를 만드는 경우에 다시 전달 하는 모든 처리 되지 않은 오류를 처리 하려고 해야 합니다. 오류 코드를 매핑할 수 없는 경우 `Err.Number` 고유한 오류 및이 전달 하는 중 하나에 개체의 호출자에 게 다시 합니다. 오류 코드를 추가 하 여 오류를 지정 해야 합니다 `VbObjectError` 상수입니다. 예를 들어 1052는 오류 코드가 다음과 같이 할당 합니다.  
  
 [!code-vb[VbVbalrErrorHandling#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#19)]  
  
> [!CAUTION]
>  Windows 동적 연결 라이브러리 (Dll)를 호출 하는 동안 시스템 오류 예외를 발생 하지 않습니다 및 Visual Basic 오류 트래핑을 사용 하 여 잡아낼 수 없습니다. 성공 또는 실패 (에 따라 API 사양)에 대 한 각 반환 값을 검사 하는 DLL 함수를 호출할 때 오류가 발생 하면 값을 확인 합니다 `Err` 개체의 `LastDLLError` 속성입니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 먼저 사용 하 여는 `On Error GoTo` 문을 프로시저 내에서 오류 처리 루틴을의 위치를 지정 합니다. 예제에서는 0으로 나누려 할 6 오류 번호를 생성 합니다. 오류 처리 루틴에서 오류가 처리 되 고 제어 오류를 발생 시킨 명령문에 반환 됩니다. `On Error GoTo 0` 문을 오류 잡기를 해제 합니다. 그런 다음 `On Error Resume Next` 문을 다음 문으로 생성 된 오류에 대 한 컨텍스트를 특정 알 수 있도록 오류 트래핑을 지연 시키려면 사용 합니다. `Err.Clear` 의 선택을 취소 하는 데 사용 되는 `Err` 오류가 처리 되 면 개체의 속성입니다.  
  
 [!code-vb[VbVbalrErrorHandling#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#20)]  
  
## <a name="requirements"></a>요구 사항  
 **네임스페이스:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **어셈블리:** Visual Basic 런타임 라이브러리(Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Number%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Description%2A>
- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [End 문](../../../visual-basic/language-reference/statements/end-statement.md)
- [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Resume 문](../../../visual-basic/language-reference/statements/resume-statement.md)
- [오류 메시지](../../../visual-basic/language-reference/error-messages/index.md)
- [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
