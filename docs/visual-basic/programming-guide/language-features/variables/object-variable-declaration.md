---
title: 개체 변수 선언
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
ms.openlocfilehash: d1964e3768124dde1deeabfada9006ff5a59def0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351811"
---
# <a name="object-variable-declaration-visual-basic"></a>개체 변수 선언(Visual Basic)
일반 선언문을 사용 하 여 개체 변수를 선언 합니다. 데이터 형식에 대해 `Object` (즉, [개체 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)) 또는 개체를 만들 보다 구체적인 클래스 중 하나를 지정 합니다.  
  
 변수를 `Object` 선언 하는 것은 <xref:System.Object?displayProperty=nameWithType>으로 선언 하는 것과 같습니다.  
  
 특정 개체 클래스를 사용 하 여 변수를 선언 하는 경우 해당 클래스와 해당 클래스가 상속 하는 클래스에 의해 노출 된 모든 메서드와 속성에 액세스할 수 있습니다. <xref:System.Object>를 사용 하 여 변수를 선언 하는 경우 런타임에 바인딩을 허용 하도록 `Option Strict Off`를 설정 하지 않으면 <xref:System.Object> 클래스의 멤버에만 액세스할 수 있습니다.  
  
## <a name="declaration-syntax"></a>선언 구문  
 다음 구문을 사용 하 여 개체 변수를 선언 합니다.  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 선언에 [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)또는 [Static](../../../../visual-basic/language-reference/modifiers/static.md) 을 지정할 수도 있습니다. 다음은 유효한 예제 선언입니다.  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a>런타임에 바인딩 및 초기 바인딩  
 코드를 실행할 때까지 특정 클래스를 알 수 없는 경우가 있습니다. 이 경우 `Object` 데이터 형식을 사용 하 여 개체 변수를 선언 해야 합니다. 이렇게 하면 모든 개체 형식에 대 한 일반 참조가 만들어지고 런타임에 특정 클래스가 할당 됩니다. 이를 *후기 바인딩*이라고 합니다. 런타임에 바인딩에는 추가 실행 시간이 필요 합니다. 또한 가장 최근에 할당 된 클래스의 메서드 및 속성으로 코드를 제한 합니다. 코드에서 다른 클래스의 멤버에 액세스 하려고 하면 런타임 오류가 발생할 수 있습니다.  
  
 컴파일 타임에 특정 클래스를 알고 있으면 개체 변수를 해당 클래스로 선언 해야 합니다. 이것을 *초기 바인딩*이라고 합니다. 초기 바인딩은 성능을 향상 시키고 코드에서 특정 클래스의 모든 메서드와 속성에 액세스할 수 있도록 보장 합니다. 위의 예제 선언에서 변수 `objA` <xref:System.Windows.Forms.Label?displayProperty=nameWithType>클래스의 개체만 사용 하는 경우 해당 선언에서 `As System.Windows.Forms.Label`를 지정 해야 합니다.  
  
### <a name="advantages-of-early-binding"></a>초기 바인딩의 장점  
 개체 변수를 특정 클래스로 선언 하면 다음과 같은 여러 가지 이점이 있습니다.  
  
- 자동 형식 검사  
  
- 특정 클래스의 모든 멤버에 대 한 액세스 보장  
  
- 코드 편집기의 Microsoft IntelliSense 지원  
  
- 코드 가독성 향상  
  
- 코드의 오류 감소  
  
- 런타임 대신 컴파일 시간에 발생 한 오류  
  
- 빠른 코드 실행  
  
## <a name="access-to-object-variable-members"></a>개체 변수 멤버에 대 한 액세스  
 `Option Strict` `On`설정 된 경우 개체 변수는 선언 된 클래스의 메서드와 속성에만 액세스할 수 있습니다. 다음 예제에서는 이것을 보여 줍니다.  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 이 예제에서 `p` 는 <xref:System.Object> 클래스 자체의 멤버만 사용할 수 있으므로 `Left` 속성을 포함하지 않습니다. 반면, `q` 형식으로 선언된 <xref:System.Windows.Forms.Label>는 <xref:System.Windows.Forms.Label> 네임스페이스에 있는 <xref:System.Windows.Forms> 클래스의 모든 메서드와 속성을 사용할 수 있습니다.  
  
## <a name="flexibility-of-object-variables"></a>개체 변수의 유연성  
 상속 계층 구조에서 개체를 작업할 때 개체 변수를 선언 하는 데 사용할 클래스를 선택할 수 있습니다. 이 옵션을 선택 하는 경우 클래스 멤버에 대 한 액세스에 대해 개체 할당의 유연성을 조정 해야 합니다. 예를 들어 <xref:System.Windows.Forms.Form?displayProperty=nameWithType> 클래스로 이어지는 상속 계층 구조를 살펴보겠습니다.  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 응용 프로그램이 <xref:System.Windows.Forms.Form>클래스에서 상속 되는 `specialForm`이라는 폼 클래스를 정의 한다고 가정 합니다. 다음 예제와 같이 `specialForm`에 대해 구체적으로 참조 하는 개체 변수를 선언할 수 있습니다.  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 위의 예제에서 선언은 변수 `nextForm` `specialForm`클래스의 개체로 제한 하지만 `specialForm`가 상속 하는 모든 클래스의 모든 멤버 뿐만 아니라 `specialForm`의 모든 메서드 및 속성을 `nextForm`에서 사용할 수 있도록 합니다.  
  
 다음 예제와 같이 개체 변수를 <xref:System.Windows.Forms.Form>형식으로 선언 하 여 보다 일반적인 개체 변수를 만들 수 있습니다.  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 위의 예제에서 선언을 사용 하면 응용 프로그램의 모든 폼을 `anyForm`에 할당할 수 있습니다. 그러나 `anyForm` <xref:System.Windows.Forms.Form>클래스의 모든 멤버에 액세스할 수 있지만 `specialForm`와 같은 특정 양식에 대해 정의 된 추가 메서드 또는 속성은 사용할 수 없습니다.  
  
 기본 클래스의 모든 멤버를 파생 클래스에서 사용할 수 있지만 기본 클래스에서 파생 클래스의 추가 멤버를 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목

- [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [개체 변수 할당](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [개체 변수 값](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [방법: 개체 변수를 선언 하 고 개체를에 할당 Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [방법: 개체의 멤버에 액세스](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
