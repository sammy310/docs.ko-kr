---
title: End 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: 66dba1df125a08b8ae05519a0c66edb6da15ceaa
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583420"
---
# <a name="end-statement"></a>End 문
실행을 즉시 종료 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
End  
```  
  
## <a name="remarks"></a>주의  
 프로시저의 아무 곳에 나 `End` 문을 추가 하 여 전체 응용 프로그램의 실행을 강제로 중단할 수 있습니다. `End` `Open` 문으로 열린 모든 파일을 닫고 모든 응용 프로그램의 변수를 지웁니다. 응용 프로그램은 해당 개체에 대 한 참조를 보유 하는 다른 프로그램이 없고 해당 코드가 실행 되 고 있지 않은 즉시 닫힙니다.  
  
> [!NOTE]
> @No__t_0 문은 코드 실행을 갑자기 중지 하 고 `Dispose` 또는 `Finalize` 메서드나 다른 Visual Basic 코드를 호출 하지 않습니다. 다른 프로그램에서 보유 하 고 있는 개체 참조는 무효화 됩니다. @No__t_1 또는 `Catch` 블록 내에 `End` 문이 있으면 컨트롤이 해당 `Finally` 블록에 전달 되지 않습니다.  
  
 @No__t_0 문은 실행을 일시 중단 하지만 `End`와는 달리 컴파일된 실행 파일 (.exe)에서 발생 한 경우를 제외 하 고는 파일을 닫지 않거나 모든 변수를 지웁니다.  
  
 @No__t_0 열려 있을 수 있는 리소스에 참석 하지 않고 응용 프로그램을 종료 하기 때문에 사용 하기 전에 완전히 닫아야 합니다. 예를 들어 응용 프로그램에 열려 있는 양식이 있는 경우 컨트롤이 `End` 문에 도달 하기 전에 닫아야 합니다.  
  
 을 즉시 중지 해야 하는 경우에만 `End`을 자주 사용 해야 합니다. 프로시저를 종료 하는 일반적인 방법 ([Return 문](../../../visual-basic/language-reference/statements/return-statement.md) 및 [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md))은 프로시저를 완전히 종료 하는 것이 아니라 호출 하는 코드를 완전히 닫을 수 있는 기회를 제공 합니다. 예를 들어 콘솔 응용 프로그램은 단순히 `Main` 프로시저에서 `Return` 수 있습니다.  
  
> [!IMPORTANT]
> @No__t_0 문은 <xref:System> 네임 스페이스에서 <xref:System.Environment> 클래스의 <xref:System.Environment.Exit%2A> 메서드를 호출 합니다. <xref:System.Environment.Exit%2A> 하려면 `UnmanagedCode` 권한이 있어야 합니다. 그렇지 않으면 <xref:System.Security.SecurityException> 오류가 발생 합니다.  
  
 그 다음에 추가 키워드가 나오면 [end \<keyword > 문이](../../../visual-basic/language-reference/statements/end-keyword-statement.md) 해당 프로시저 또는 블록 정의의 끝을 서술 합니다. 예를 들어 `End Function`은 `Function` 프로시저의 정의를 종료 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `End` 문을 사용 하 여 사용자가 요청 하는 경우 코드 실행을 종료 합니다.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>스마트 디바이스 개발자 노트  
 이 문은 지원 되지 않습니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Stop 문](../../../visual-basic/language-reference/statements/stop-statement.md)
- [End \<keyword > 문](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
