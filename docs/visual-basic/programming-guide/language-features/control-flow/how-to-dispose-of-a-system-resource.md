---
title: '방법: 시스템 리소스 삭제'
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
ms.openlocfilehash: c430bc7744f5aefaa65f2a86f3e5e22743ffed57
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077204"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>방법: 시스템 리소스 해제(Visual Basic)

블록을 사용 하면 `Using` 코드가 블록을 종료할 때 시스템에서 리소스를 삭제 하는 것을 보장할 수 있습니다. 이는 많은 양의 메모리를 사용 하는 시스템 리소스를 사용 하는 경우 나 다른 구성 요소 에서도를 사용 하려는 경우에 유용 합니다.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>코드가 완료 될 때 데이터베이스 연결을 삭제 하려면  
  
1. 소스 파일 (이 경우)의 시작 부분에 데이터베이스 연결에 대 한 적절 한 [Imports 문 (.Net 네임 스페이스 및 형식)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) 이 포함 되어 있는지 확인 <xref:System.Data.SqlClient> 합니다.  
  
2. `Using`및 문을 사용 하 여 블록을 만듭니다 `Using` `End Using` . 블록 내에서 데이터베이스 연결을 처리 하는 코드를 배치 합니다.  
  
3. 연결을 선언 하 고 문의 일부로이의 인스턴스를 만듭니다 `Using` .  
  
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
  
     `sqc` `Using` 블록의 범위는 블록으로 제한 되기 때문에 블록 외부에서 액세스할 수 없습니다.  
  
     이 동일한 기술을 파일 핸들, COM 래퍼 등의 시스템 리소스에서 사용할 수 있습니다. `Using`블록을 종료 한 후에 다른 구성 요소에서 리소스를 사용할 수 있도록 하려는 경우 블록을 사용 `Using` 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Data.SqlClient.SqlConnection>
- [제어 흐름](index.md)
- [판단 구조체](decision-structures.md)
- [루프 구조체](loop-structures.md)
- [기타 제어 구조체](other-control-structures.md)
- [중첩 제어 구조체](nested-control-structures.md)
- [Using 문](../../../language-reference/statements/using-statement.md)
