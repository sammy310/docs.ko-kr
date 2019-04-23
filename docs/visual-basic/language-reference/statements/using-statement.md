---
title: Using 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: fe53ea58dc98a4de793fe9dad1c3ceeac71622fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843203"
---
# <a name="using-statement-visual-basic"></a>Using 문(Visual Basic)
시작을 선언 된 `Using` 블록과 선택적으로 블록을 제어 하는 시스템 리소스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`resourcelist`|제공 하지 않는 경우 필요한 `resourceexpression`합니다. 이는 하나 이상의 시스템 리소스 목록 `Using` 쉼표로 구분 하 여 컨트롤을 차단 합니다.|  
|`resourceexpression`|제공 하지 않는 경우 필요한 `resourcelist`합니다. 참조 변수 또는 시스템 리소스에 대 한이 제어를 참조 하는 식을 `Using` 블록입니다.|  
|`statements`|선택 사항입니다. 문 블록을 하는 `Using` 블록이 실행 됩니다.|  
|`End Using`|필수 요소. 정의 종료 합니다 `Using` 블록 및 제어 하는 모든 리소스를 삭제 합니다.|  
  
 각 리소스에는 `resourcelist` 파트에는 다음 구문과 구성 요소:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 또는  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>resourcelist 파트  
  
|용어|정의|  
|---|---|  
|`resourcename`|필수 요소. 시스템 리소스를 가리키는 참조 변수는는 `Using` 컨트롤을 차단 합니다.|  
|`New`|필요한 경우는 `Using` 문은 리소스를 획득 합니다. 리소스를 이미 구입한 경우 두 번째 대체 구문을 사용 합니다.|  
|`resourcetype`|필수 요소. 클래스 리소스입니다. 클래스를 구현 해야 합니다는 <xref:System.IDisposable> 인터페이스입니다.|  
|`arglist`|선택 사항입니다. 인스턴스를 만드는 생성자에 전달 하는 인수의 목록 `resourcetype`합니다. 참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.|  
|`resourceexpression`|필수 요소. 변수 또는 식의 요구 사항을 충족 하는 시스템 리소스를 가리키는 `resourcetype`합니다. 리소스 제어를 전달 하기 전에 가져와야 두 번째 구문 대안을 사용 하는 경우는 `Using` 문입니다.|  
  
## <a name="remarks"></a>설명  
 경우에 따라 코드에는 SQL 연결, 파일 핸들 및 COM 래퍼를 등 관리 되지 않는 리소스를 필요합니다. `Using` 블록으로 코드 완료 되 면 하나 이상의 이러한 리소스의 삭제를 보장 합니다. 이에 사용할 수 있게 다른 코드를 사용 합니다.  
  
 관리 되는 리소스는 사용자의 추가 코딩 없이.NET Framework 가비지 수집기 (GC)에서 삭제 됩니다. 불필요 한 `Using` 관리 되는 리소스에 대 한 블록입니다. 그러나 여전히 사용할 수는 `Using` 가비지 수집기를 기다리지 않고 관리 되는 리소스의 삭제를 차단 합니다.  
  
 `Using` 블록에는 세 부분으로 구성: 취득, 사용 및 삭제 합니다.  
  
-   *취득* 변수를 만들고 시스템 리소스를 가리키도록 초기화 하는 것을 의미 합니다. 합니다 `Using` 문은 하나 이상의 리소스를 얻을 수 있습니다 하거나 블록에 들어가기 전에 정확히 한 개의 리소스를 획득 하 고 제공 합니다 `Using` 문. 제공 하는 경우 `resourceexpression`에 제어를 전달 하기 전에 리소스를 가져와야 합니다 `Using` 문.  
  
-   *사용 현황* 리소스에 액세스 하 고 사용 하 여 작업을 수행 합니다. 사이 있는 문은 `Using` 고 `End Using` 리소스 사용을 나타냅니다.  
  
-   *폐기* 의미를 호출 합니다 <xref:System.IDisposable.Dispose%2A> 개체에서 메서드 `resourcename`. 이 개체를를 해당 리소스를 완전히 종료할 수 있습니다. 합니다 `End Using` 문 아래에 있는 리소스를 삭제 합니다 `Using` 블록의 제어 합니다.  
  
## <a name="behavior"></a>동작  
 A `Using` 블록 처럼는 `Try`... `Finally` 는 생성 합니다 `Try` 블록은 리소스를 사용 및 `Finally` 블록을 삭제 합니다. 이 인해는 `Using` 블록은 블록을 종료 하는 방법에 관계 없이 리소스를 삭제 합니다. 예외가 처리 되지 않은 경우에 마찬가지 제외 하 고는 <xref:System.StackOverflowException>합니다.  
  
 획득 한 모든 리소스 변수의 범위는 `Using` 문 제한 됩니다는 `Using` 블록입니다.  
  
 둘 이상의 시스템 리소스를 지정 하는 경우는 `Using` 중첩 문을 효과 동일 `Using` 내에서 다른 하나를 차단 합니다.  
  
 경우 `resourcename` 는 `Nothing`에 대 한 호출이 <xref:System.IDisposable.Dispose%2A> 설정 되 고 예외가 throw 됩니다.  
  
## <a name="structured-exception-handling-within-a-using-block"></a>구조적된 예외 처리를 사용 하 여 블록 내에서  
 내에서 발생할 수 있는 예외를 처리 해야 합니다 `Using` 블록 전체를 추가할 수 있습니다 `Try`... `Finally` 를 생성 합니다. 사례를 처리 하는 경우 위치는 `Using` 문 리소스를 설정 하는 동안에 실패 하는지 테스트할 수 있습니다 `resourcename` 는 `Nothing`합니다.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>구조적된 예외 처리를 사용 하 여 블록 대신  
 보다 세부적으로 제어 리소스를 취득 해야 경우에 추가 코드가 필요 합니다 `Finally` 블록 다시 작성할 수 있습니다 합니다 `Using` 으로 차단는 `Try`... `Finally` 생성 합니다. 다음 예제에서는 스 켈 레 톤 `Try` 하 고 `Using` 가져오기 및 삭제에 해당 하는 구문을 `resource`합니다.  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
>  내에서 코드를 `Using` 블록에서 개체를 할당 하지 말아야 `resourcename` 다른 변수에 합니다. 종료 하는 경우는 `Using` 블록에 리소스를 삭제 하 고 다른 변수에서 가리키는 리소스를 액세스할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 파일에 두 줄 텍스트를 쓰고 log.txt 라는 파일을 만듭니다. 또한 동일한 해당 파일을 읽습니다 하 고 텍스트의 줄이 표시 됩니다.  
  
 때문에 <xref:System.IO.TextWriter> 및 <xref:System.IO.TextReader> 클래스 구현 합니다 <xref:System.IDisposable> 인터페이스 코드를 사용할 수 `Using` 파일 올바르게 닫힌 후 쓰기 및 읽기 작업을 확인 하는 문.  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.IDisposable>
- [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [방법: 시스템 리소스 해제](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
