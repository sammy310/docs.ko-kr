---
title: '방법: 시스템 리소스 해제(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: c780ee1a174ad044593960bc30a3ee2e1f929390
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583139"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>방법: 시스템 리소스 해제(Visual Basic)
@No__t_0 블록을 사용 하 여 코드가 블록을 종료할 때 시스템이 리소스를 삭제 하도록 할 수 있습니다. 이는 많은 양의 메모리를 사용 하는 시스템 리소스를 사용 하는 경우 나 다른 구성 요소 에서도를 사용 하려는 경우에 유용 합니다.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>코드가 완료 될 때 데이터베이스 연결을 삭제 하려면  
  
1. 소스 파일의 시작 부분에 데이터베이스 연결에 대 한 적절 한 [Imports 문 (.Net 네임 스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 이 포함 되어 있는지 확인 합니다 (이 경우에는 <xref:System.Data.SqlClient>).  
  
2. @No__t_1 및 `End Using` 문을 사용 하 여 `Using` 블록을 만듭니다. 블록 내에서 데이터베이스 연결을 처리 하는 코드를 배치 합니다.  
  
3. 연결을 선언 하 고 `Using` 문의 일부로이의 인스턴스를 만듭니다.  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     처리 되지 않은 예외의 경우를 비롯 하 여 블록을 종료 하는 방법에 관계 없이 시스템에서 리소스를 삭제 합니다.  
  
     범위는 블록으로 제한 되기 때문에 `Using` 블록 외부에서 `sqc`에 액세스할 수 없습니다.  
  
     이 동일한 기술을 파일 핸들, COM 래퍼 등의 시스템 리소스에서 사용할 수 있습니다. @No__t_1 블록을 종료 한 후에 다른 구성 요소에서 리소스를 사용할 수 있도록 하려는 경우 `Using` 블록을 사용 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Data.SqlClient.SqlConnection>
- [제어 흐름](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [판단 구조](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [기타 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [중첩 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Using 문](../../../../visual-basic/language-reference/statements/using-statement.md)
