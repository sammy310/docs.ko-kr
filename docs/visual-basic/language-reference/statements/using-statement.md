---
description: '자세한 정보: Using 문 (Visual Basic)'
title: Using 문
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: fea77a441182b7c3ecac58d4fe7f1297a87f086c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740888"
---
# <a name="using-statement-visual-basic"></a>Using 문(Visual Basic)

블록의 시작을 선언 `Using` 하 고 필요에 따라 블록에서 제어 하는 시스템 리소스를 가져옵니다.

## <a name="syntax"></a>Syntax

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a>부분

|용어|정의|  
|---|---|  
|`resourcelist`|를 제공 하지 않는 경우 필수 사항 `resourceexpression` 입니다. 이 블록이 제어 하는 하나 이상의 시스템 리소스 목록 `Using` 으로, 쉼표로 구분 합니다.|  
|`resourceexpression`|를 제공 하지 않는 경우 필수 사항 `resourcelist` 입니다. 이 블록에 의해 제어 되는 시스템 리소스를 참조 하는 참조 변수 또는 식 `Using` 입니다.|  
|`statements`|선택 사항입니다. 블록이 실행 하는 문 블록입니다 `Using` .|  
|`End Using`|필수 사항입니다. 블록의 정의를 종료 `Using` 하 고 제어 하는 모든 리소스를 삭제 합니다.|  

 파트의 각 리소스에 `resourcelist` 는 다음과 같은 구문과 파트가 있습니다.

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 또는

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a>resourcelist 파트

|용어|정의|  
|---|---|  
|`resourcename`|필수 요소. 블록에서 제어 하는 시스템 리소스를 참조 하는 참조 변수입니다 `Using` .|  
|`New`|문이 리소스를 획득 하는 경우에 필요 `Using` 합니다. 이미 리소스를 취득 한 경우 두 번째 구문 대체 방법을 사용 합니다.|  
|`resourcetype`|필수 사항입니다. 리소스의 클래스입니다. 클래스는 인터페이스를 구현 해야 합니다 <xref:System.IDisposable> .|  
|`arglist`|선택 사항입니다. 인스턴스를 만들기 위해 생성자에 전달 하는 인수 목록입니다 `resourcetype` . [매개 변수 목록](parameter-list.md)을 참조 하세요.|  
|`resourceexpression`|필수 사항입니다. 의 요구 사항을 충족 하는 시스템 리소스를 참조 하는 변수 또는 식 `resourcetype` 입니다. 두 번째 구문 대체 방법을 사용 하는 경우 제어를 문에 전달 하기 전에 리소스를 가져와야 합니다 `Using` .|  
  
## <a name="remarks"></a>설명

 코드에 파일 핸들, COM 래퍼 또는 SQL 연결과 같은 관리 되지 않는 리소스가 필요한 경우도 있습니다. `Using`블록은 코드가 완료 될 때 이러한 리소스를 하나 이상 삭제 하는 것을 보장 합니다. 이렇게 하면 다른 코드에서 사용할 수 있습니다.

 관리 되는 리소스는 추가 코딩 없이 GC (.NET Framework 가비지 수집기)에 의해 삭제 됩니다. `Using`관리 되는 리소스에 대 한 블록이 필요 하지 않습니다. 그러나 `Using` 가비지 수집기를 대기 하는 대신 블록을 사용 하 여 관리 되는 리소스를 강제로 삭제할 수 있습니다.

 `Using`블록은 획득, 사용 및 삭제의 세 부분으로 구성 됩니다.

- *취득* 은 변수를 만들고 초기화 하 여 시스템 리소스를 참조 하는 것을 의미 합니다. `Using`문은 하나 이상의 리소스를 얻거나 블록을 입력 하기 전에 정확히 하나의 리소스를 획득 한 후 문에 제공할 수 있습니다 `Using` . 를 제공 하는 경우 `resourceexpression` 문에 제어를 전달 하기 전에 리소스를 얻어야 합니다 `Using` .

- *사용* 은 리소스에 액세스 하 고 작업을 수행 하는 것을 의미 합니다. 과 사이의 문은 `Using` `End Using` 리소스의 사용을 나타냅니다.

- *삭제* 는 <xref:System.IDisposable.Dispose%2A> 의 개체에 대해 메서드를 호출 하는 것을 의미 `resourcename` 합니다. 이렇게 하면 개체가 리소스를 완전히 종료할 수 있습니다. `End Using`문은 블록의 컨트롤에 있는 리소스를 삭제 합니다 `Using` .

## <a name="behavior"></a>동작

 블록은 `Using` `Try` `Finally` `Try` 블록이 리소스를 사용 하 고 블록에서 해당 리소스를 `Finally` 삭제 하는 ... 생성 처럼 동작 합니다. 따라서 블록을 `Using` 종료 하는 방법에 관계 없이 블록은 리소스 삭제를 보장 합니다. 이는를 제외 하 고 처리 되지 않은 예외의 경우에도 마찬가지입니다 <xref:System.StackOverflowException> .

 문에 의해 획득 된 모든 리소스 변수의 범위는 `Using` 블록으로 제한 됩니다 `Using` .

 문에서 둘 이상의 시스템 리소스를 지정 하는 경우 `Using` 다른 범위 내에 블록을 중첩 한 것과 같은 결과가 나타납니다 `Using` .

 `resourcename`가 이면 `Nothing` 에 대 한 호출이 <xref:System.IDisposable.Dispose%2A> 수행 되지 않으며 예외가 throw 되지 않습니다.

## <a name="structured-exception-handling-within-a-using-block"></a>Using 블록 내에서 구조적 예외 처리

 블록에서 발생할 수 있는 예외를 처리 해야 하는 경우 `Using` 전체 `Try` ... 생성을 추가할 수 있습니다. `Finally` 문이 리소스를 획득 하는 데 실패 한 경우를 처리 해야 하는 경우를 테스트 하 여 `Using` 가 인지를 확인할 수 있습니다 `resourcename` `Nothing` .

## <a name="structured-exception-handling-instead-of-a-using-block"></a>Using 블록 대신 구조적 예외 처리

 리소스 획득을 보다 세부적으로 제어 해야 하거나 블록에 추가 코드가 필요한 경우 `Finally` `Using` 블록을 `Try` ... `Finally` 생성으로 다시 작성할 수 있습니다. 다음 예제에서는 `Try` `Using` 의 획득 및 삭제에 해당 하는 해골 및 생성을 보여 줍니다 `resource` .

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
> 블록 내의 코드는 `Using` 개체를 다른 변수에 할당 하면 안 `resourcename` 됩니다. 블록을 종료 하면 `Using` 리소스가 삭제 되 고 다른 변수는 가리키는 리소스에 액세스할 수 없습니다.

## <a name="example"></a>예제

 다음 예에서는 log.txt 라는 파일을 만들고 두 줄의 텍스트를 파일에 씁니다. 또한이 예제에서는 동일한 파일을 읽고 텍스트 줄을 표시 합니다.

 및 클래스는 인터페이스를 구현 하기 때문에 <xref:System.IO.TextWriter> <xref:System.IO.TextReader> <xref:System.IDisposable> 코드는 `Using` 문을 사용 하 여 쓰기 및 읽기 작업 후에 파일이 올바르게 닫혀 있는지 확인할 수 있습니다.

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a>참고 항목

- <xref:System.IDisposable>
- [Try...Catch...Finally 문](try-catch-finally-statement.md)
- [방법: 시스템 리소스 삭제](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
