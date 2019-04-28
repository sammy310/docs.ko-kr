---
title: '방법: 두 개체가 관련이 있는지 여부를 확인 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: f59e00d80d28fc4bf24874d25b5c12643649c834
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769072"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>방법: 두 개체가 관련이 있는지 여부를 확인 (Visual Basic)
생성 된 클래스 간의 관계를 확인 하려면 두 개체를 비교할 수 있습니다. 합니다 <xref:System.Type.IsInstanceOfType%2A> 메서드를 <xref:System.Type?displayProperty=nameWithType> 반환 클래스 `True` 지정된 된 클래스는 현재 클래스에서 상속 하는 경우 또는 현재 형식이 지정된 된 클래스에서 지 원하는 인터페이스인 경우.  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>한 개체가 다른 개체의 클래스 또는 인터페이스에서 상속 하는 경우를 확인 하려면  
  
1. 기본 형식, 호출 될 수 있습니다 하 생각 하는 개체에는 <xref:System.Object.GetType%2A> 메서드.  
  
2. 에 <xref:System.Type?displayProperty=nameWithType> 에서 반환 된 개체 <xref:System.Object.GetType%2A>를 호출 합니다 <xref:System.Type.IsInstanceOfType%2A> 메서드.  
  
3. 에 대 한 인수 목록의 <xref:System.Type.IsInstanceOfType%2A>, 파생 형식 이라고 생각 되는 개체 수를 지정 합니다.  
  
     <xref:System.Type.IsInstanceOfType%2A> 반환 `True` 해당 인수 형식에서 상속 하는 경우는 <xref:System.Type?displayProperty=nameWithType> 개체 유형입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 개체가 다른 개체의 클래스에서 파생 된 클래스를 나타내는지 여부를 결정 합니다.  
  
```  
Public Class baseClass  
End Class  
Public Class derivedClass : Inherits baseClass  
End Class  
Public Class testTheseClasses  
    Public Sub seeIfRelated()  
        Dim baseObj As Object = New baseClass()  
        Dim derivedObj As Object = New derivedClass()  
        Dim related As Boolean  
        related = baseObj.GetType().IsInstanceOfType(derivedObj)  
        MsgBox(CStr(related))  
    End Sub  
End Class  
```  
  
 예기치 않은 위치에 대 한 호출에서 두 개체 변수를 주의 <xref:System.Type.IsInstanceOfType%2A>합니다. 때문된 기본 형식이 생성 되는 <xref:System.Type?displayProperty=nameWithType> 클래스 및 파생된 형식 때문된에 인수로 전달 되는 <xref:System.Type.IsInstanceOfType%2A> 메서드.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [개체 변수 값](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [방법: 두 개체가 동일한 지 여부를 결정 합니다.](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
