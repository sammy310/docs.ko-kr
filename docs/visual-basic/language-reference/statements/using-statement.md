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
ms.openlocfilehash: 346a26ad5751599831d8b0d3e0497e4d488eb76c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957540"
---
# <a name="using-statement-visual-basic"></a>Using 문(Visual Basic)
`Using` 블록의 시작을 선언 하 고 필요에 따라 블록에서 제어 하는 시스템 리소스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`resourcelist`|를 제공 `resourceexpression`하지 않는 경우 필수 사항입니다. 이 `Using` 블록이 제어 하는 하나 이상의 시스템 리소스 목록으로, 쉼표로 구분 합니다.|  
|`resourceexpression`|를 제공 `resourcelist`하지 않는 경우 필수 사항입니다. 이 `Using` 블록에 의해 제어 되는 시스템 리소스를 참조 하는 참조 변수 또는 식입니다.|  
|`statements`|선택 사항입니다. `Using` 블록이 실행 하는 문 블록입니다.|  
|`End Using`|필수 요소. `Using` 블록의 정의를 종료 하 고 제어 하는 모든 리소스를 삭제 합니다.|  
  
 `resourcelist` 파트의 각 리소스에는 다음과 같은 구문과 파트가 있습니다.  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 또는  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>resourcelist 파트  
  
|용어|정의|  
|---|---|  
|`resourcename`|필수 요소. 블록에서 `Using` 제어 하는 시스템 리소스를 참조 하는 참조 변수입니다.|  
|`New`|문이 리소스를 `Using` 획득 하는 경우에 필요 합니다. 이미 리소스를 취득 한 경우 두 번째 구문 대체 방법을 사용 합니다.|  
|`resourcetype`|필수 요소. 리소스의 클래스입니다. 클래스는 인터페이스를 <xref:System.IDisposable> 구현 해야 합니다.|  
|`arglist`|선택 사항입니다. 인스턴스를 만들기 위해 생성자에 전달 하는 인수 목록입니다 `resourcetype`. [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)을 참조 하세요.|  
|`resourceexpression`|필수 요소. 의 `resourcetype`요구 사항을 충족 하는 시스템 리소스를 참조 하는 변수 또는 식입니다. 두 번째 구문 대체 방법을 사용 하는 경우 제어 `Using` 를 문에 전달 하기 전에 리소스를 가져와야 합니다.|  
  
## <a name="remarks"></a>설명  
 코드에 파일 핸들, COM 래퍼 또는 SQL 연결과 같은 관리 되지 않는 리소스가 필요한 경우도 있습니다. 블록 `Using` 은 코드가 완료 될 때 이러한 리소스를 하나 이상 삭제 하는 것을 보장 합니다. 이렇게 하면 다른 코드에서 사용할 수 있습니다.  
  
 관리 되는 리소스는 추가 코딩 없이 GC (.NET Framework 가비지 수집기)에 의해 삭제 됩니다. 관리 되는 리소스에 `Using` 대 한 블록이 필요 하지 않습니다. 그러나 가비지 수집기를 대기 하는 `Using` 대신 블록을 사용 하 여 관리 되는 리소스를 강제로 삭제할 수 있습니다.  
  
 블록 `Using` 은 획득, 사용 및 삭제의 세 부분으로 구성 됩니다.  
  
- *취득* 은 변수를 만들고 초기화 하 여 시스템 리소스를 참조 하는 것을 의미 합니다. 문은 하나 이상의 리소스를 얻거나 블록을 입력 하기 전에 정확히 하나의 리소스를 획득 한 후 `Using` 문에 제공할 수 있습니다. `Using` 를 제공 `resourceexpression`하는 경우 `Using` 문에 제어를 전달 하기 전에 리소스를 얻어야 합니다.  
  
- *사용* 은 리소스에 액세스 하 고 작업을 수행 하는 것을 의미 합니다. `Using` 과`End Using` 사이의 문은 리소스의 사용을 나타냅니다.  
  
- *삭제* 는의 <xref:System.IDisposable.Dispose%2A> `resourcename`개체에 대해 메서드를 호출 하는 것을 의미 합니다. 이렇게 하면 개체가 리소스를 완전히 종료할 수 있습니다. `End Using` 문은 `Using` 블록의 컨트롤에 있는 리소스를 삭제 합니다.  
  
## <a name="behavior"></a>동작  
 `Using` 블록`Try`은 ... 블록에서 리소스 를`Finally` 사용 하 고 블록에서 리소스를 삭제 하는 구문입니다. `Finally` `Try` 따라서 블록을 종료 하 `Using` 는 방법에 관계 없이 블록은 리소스 삭제를 보장 합니다. 이는를 <xref:System.StackOverflowException>제외 하 고 처리 되지 않은 예외의 경우에도 마찬가지입니다.  
  
 `Using` 문에 의해 획득 된 모든 리소스 변수의 범위는 `Using` 블록으로 제한 됩니다.  
  
 `Using` 문에서 둘 이상의 시스템 리소스를 지정 하는 경우 다른 범위 내에 블록을 중첩 `Using` 한 것과 같은 결과가 나타납니다.  
  
 가 이면에 대<xref:System.IDisposable.Dispose%2A> 한 호출이 수행 되지 않으며 예외가 throw 되지 않습니다. `Nothing` `resourcename`  
  
## <a name="structured-exception-handling-within-a-using-block"></a>Using 블록 내에서 구조적 예외 처리  
 `Using` 블록에서 발생할 수 있는 예외를 처리 해야 하는 경우 전체 `Try`를 추가할 수 있습니다. `Finally` 생성할 수 있습니다. `Using` 문이 리소스를 획득 하는 데 실패 한 경우를 처리 해야 하는 경우를 테스트 하 여 `resourcename` 가 인지 `Nothing`를 확인할 수 있습니다.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>Using 블록 대신 구조적 예외 처리  
 리소스 획득을 보다 세부적으로 제어 해야 하는 경우 또는 `Finally` 블록 `Using` 에 추가 코드가 필요한 경우 블록 `Try`을 ... `Finally` 생성. 다음 예제에서는의 `Try` `resource`획득 및 `Using` 삭제에 해당 하는 해골 및 생성을 보여 줍니다.  
  
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
> `Using` 블록 내의 코드는 `resourcename` 개체를 다른 변수에 할당 하면 안 됩니다. `Using` 블록을 종료 하면 리소스가 삭제 되 고 다른 변수는 가리키는 리소스에 액세스할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 .log 라는 파일을 만들고 두 줄의 텍스트를 파일에 씁니다. 또한이 예제에서는 동일한 파일을 읽고 텍스트 줄을 표시 합니다.  
  
 및 <xref:System.IO.TextWriter> <xref:System.IDisposable> 클래스는 인터페이스를 구현 하기 때문에 코드는 문을 `Using` 사용 하 여 쓰기 및 읽기 작업 후에 파일이 올바르게 닫혀 있는지 확인할 수 있습니다. <xref:System.IO.TextReader>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.IDisposable>
- [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [방법: 시스템 리소스를 삭제 합니다.](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
