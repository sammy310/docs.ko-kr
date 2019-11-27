---
title: '방법: 두 개체가 관련이 있는지 확인'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b3f5fc017166ba9cf28359db5de850c81b73bd69
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348625"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>방법: 두 개체가 관련이 있는지 확인(Visual Basic)

두 개체를 비교 하 여 해당 관계 (있는 경우)가 생성 된 클래스 간의 관계를 결정할 수 있습니다. <xref:System.Type?displayProperty=nameWithType> 클래스의 <xref:System.Type.IsInstanceOfType%2A> 메서드는 지정 된 클래스가 현재 클래스에서 상속 되는 경우 `True`을 반환 하 고, 현재 형식이 지정 된 클래스에서 지 원하는 인터페이스인 경우에는를 반환 합니다.

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>한 개체가 다른 개체의 클래스 또는 인터페이스에서 상속 되는지 확인 하려면

1. 기본 형식인 것으로 생각 되는 개체에서 <xref:System.Object.GetType%2A> 메서드를 호출 합니다.

2. <xref:System.Object.GetType%2A>에서 반환 된 <xref:System.Type?displayProperty=nameWithType> 개체에서 <xref:System.Type.IsInstanceOfType%2A> 메서드를 호출 합니다.

3. <xref:System.Type.IsInstanceOfType%2A>에 대 한 인수 목록에서 파생 된 형식의 것으로 생각 되는 개체를 지정 합니다.

    <xref:System.Type.IsInstanceOfType%2A> 인수 형식이 <xref:System.Type?displayProperty=nameWithType> 개체 형식에서 상속 되는 경우 `True`을 반환 합니다.

## <a name="example"></a>예제
 다음 예제에서는 한 개체가 다른 개체의 클래스에서 파생 된 클래스를 나타내는지 여부를 확인 합니다.

```vb
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

<xref:System.Type.IsInstanceOfType%2A>에 대 한 호출에서 두 개체 변수의 예기치 않은 배치를 확인 합니다. 예상 되는 기본 형식은 <xref:System.Type?displayProperty=nameWithType> 클래스를 생성 하는 데 사용 되 고, 예상 되는 파생 형식은 <xref:System.Type.IsInstanceOfType%2A> 메서드에 인수로 전달 됩니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [개체 변수 값](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [방법: 두 개체가 동일한지 확인](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
