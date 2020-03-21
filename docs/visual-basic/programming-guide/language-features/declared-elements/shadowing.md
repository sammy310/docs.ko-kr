---
title: 섀도잉
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
ms.openlocfilehash: 20a33478f622fca6d3183772f53dcb3e72f79409
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266887"
---
# <a name="shadowing-in-visual-basic"></a>시각적 기본의 그림자
두 프로그래밍 요소가 같은 이름을 공유하면 그 중 하나가 숨기거나 다른 하나는 *그림자로*숨길 수 있습니다. 이러한 경우 그림자 요소를 참조할 수 없습니다. 대신 코드에서 요소 이름을 사용하는 경우 Visual Basic 컴파일러는 이를 섀도잉 요소로 확인합니다.  
  
## <a name="purpose"></a>목적  
 그림자의 주요 목적은 반원의 정의를 보호하는 것이다. 기본 클래스는 이미 정의된 것과 이름이 같은 요소를 만드는 변경작업을 겪을 수 있습니다. 이 경우 `Shadows` 수정자는 클래스를 통해 참조를 사용하여 새 기본 클래스 요소 대신 정의한 멤버로 해결하도록 합니다.  
  
## <a name="types-of-shadowing"></a>그림자의 종류  
 요소는 두 가지 방법으로 다른 요소의 그림자를 만들 수 있습니다. 그림자 요소는 그림자 요소가 포함된 영역의 하위 영역 내에서 선언할 수 있으며, 이 경우 그림자는 *범위를 통해*수행됩니다. 또는 파생 클래스는 기본 클래스의 멤버를 재정의할 수 있으며, 이 경우 그림자는 *상속을 통해*수행됩니다.  
  
### <a name="shadowing-through-scope"></a>범위를 통해 그림자  
 동일한 모듈, 클래스 또는 구조의 프로그래밍 요소는 이름이 같지만 범위가 다를 수 있습니다. 이러한 방식으로 두 요소가 선언되고 코드가 공유하는 이름을 참조하면 범위가 좁은 요소가 다른 요소의 그림자를 지정합니다(블록 범위는 가장 좁습니다).  
  
 예를 들어 모듈은 명명된 `Public` `temp`변수를 정의할 수 있으며 모듈 내의 `temp`프로시저도 명명된 로컬 변수를 선언할 수 있습니다. 프로시저 내에서 참조는 `temp` 로컬 변수에 `temp` 액세스하는 반면 프로시저 외부에서 참조는 변수에 액세스합니다. `Public` 이 경우 프로시저 `temp` 변수는 모듈 `temp`변수를 숨김시게 합니다.  
  
 다음 그림에서는 두 변수(모두 `temp`명명된 변수)를 보여 주십니다. 로컬 변수는 `temp` 자체 프로시저 내에서 액세스할 때 멤버 변수를 `temp` 숨바히게 합니다. `p` 그러나 키워드는 `MyClass` 그림자를 우회하고 멤버 변수에 액세스합니다.  
  
 ![범위를 통해 그림자를 표시하는 그래픽입니다.](./media/shadowing/shadow-scope-diagram.gif)
  
 범위를 통해 그림자의 예는 [참조 방법: 변수와 같은 이름의 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>상속을 통해 그림자  
 파생 클래스가 기본 클래스에서 상속된 프로그래밍 요소를 재정의하는 경우 재정의 요소는 원래 요소의 그림자를 지정합니다. 모든 유형의 선언된 요소 또는 오버로드된 요소 집합을 다른 유형과 함께 섀도우할 수 있습니다. 예를 들어 `Integer` 변수는 프로시저를 숨는 다. `Function` 다른 프로시저를 사용하여 프로시저를 섀도우하는 경우 다른 매개 변수 목록과 다른 반환 유형을 사용할 수 있습니다.  
  
 다음 그림에서는 기본 `b` 클래스와 `b`에서 `d` 상속하는 파생 클래스를 보여 주며 있습니다. 기본 클래스는 명명된 `proc`프로시저를 정의하고 파생된 클래스는 동일한 이름의 다른 프로시저로 그 를 숨는다. 첫 `Call` 번째 문은 파생 `proc` 클래스의 그림자에 액세스합니다. 그러나 키워드는 `MyBase` 그림자를 우회하고 기본 클래스의 그림자 프로시저에 액세스합니다.  
  
 ![상속을 통한 숨기기 그래픽 다이어그램](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 상속을 통해 그림자를 드리는 예제의 경우 [방법: 변수와 동일한 이름의 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) 및 [방법: 상속된 변수 숨기기.](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
  
#### <a name="shadowing-and-access-level"></a>그림자 및 액세스 수준  
 파생 된 클래스를 사용 하 여 코드에서 항상 액세스할 수 있는 그림자 요소입니다. 예를 들어 선언될 `Private`수 있습니다. 이러한 경우 그림자가 지정되고 컴파일러가 그림자가 없는 경우 와 동일한 요소에 대한 참조를 해결합니다. 이 요소는 그림자 클래스에서 뒤로 가장 적은 파생 단계로 액세스할 수 있는 요소입니다. 그림자 요소가 프로시저인 경우 해상도는 이름이 나, 매개 변수 목록 및 반환 형식이 있는 가장 가까운 액세스 가능한 버전입니다.  
  
 다음 예제에서는 세 클래스의 상속 계층 구조를 보여 주다. 각 클래스는 `Sub` 프로시저를 `display`정의하고 각 파생 `display` 클래스는 해당 기본 클래스의 프로시저를 섀도우합니다.  
  
```vb  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 앞의 예제에서 파생된 클래스 `secondClass` 그림자는 `display` `Private` 프로시저를 통해 표시됩니다. 모듈에서 `callDisplay` `display` `secondClass`호출할 때 호출 `secondClass` 코드가 외부에 있으므로 `display` 개인 프로시저에 액세스할 수 없습니다. 그림자가 숨김이 무산되고 컴파일러가 기본 `display` 클래스 프로시저에 대한 참조를 해결합니다.  
  
 그러나 파생된 클래스는 `thirdClass` `display` `Public`로 선언하므로 의 `callDisplay` 코드에서 액세스할 수 있습니다.  
  
## <a name="shadowing-and-overriding"></a>그림자 및 재정의  
 그림자를 재정의와 혼동하지 마십시오. 파생 된 클래스가 기본 클래스에서 상속 될 때 사용 되며 둘 다 다른 선언 된 요소를 재정의 합니다. 그러나 둘 사이에는 상당한 차이가 있습니다. 비교를 위해 [그림자와 재정의 간의 차이점을](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)참조하십시오.  
  
## <a name="shadowing-and-overloading"></a>그림자 및 오버로드  
 파생 클래스에서 두 개 이상의 요소로 동일한 기본 클래스 요소를 섀도우하면 그림자 요소가 해당 요소의 오버로드된 버전이 됩니다. 자세한 내용은 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)을 참조하세요.  
  
## <a name="accessing-a-shadowed-element"></a>그림자 요소에 액세스  
 파생 클래스에서 요소에 액세스하는 경우 일반적으로 `Me` 해당 파생 클래스의 현재 인스턴스를 통해 키워드로 요소 이름을 한정합니다. 파생 클래스가 기본 클래스의 요소를 그림자로 지정하는 경우 `MyBase` 키워드로 한정하여 기본 클래스 요소에 액세스할 수 있습니다.  
  
 그림자 요소에 액세스하는 예제는 파생 [클래스에 의해 숨겨진 변수에 액세스하는 방법을](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)참조하십시오.  
  
### <a name="declaration-of-the-object-variable"></a>개체 변수 선언  
 개체 변수를 만드는 방법은 파생 된 클래스가 그림자 요소 또는 그림자 요소에 액세스하는지 여부에 영향을 줄 수 있습니다. 다음 예제에서는 파생 된 클래스에서 두 개의 개체를 만듭니다하지만 한 개체는 기본 클래스로 선언 되 고 다른 개체는 파생 된 클래스로 선언 됩니다.  
  
```vb  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 앞의 예제에서 변수는 `basObj` 기본 클래스로 선언됩니다. 개체에 `dervCls` 개체를 할당하는 것은 확대 변환을 구성하므로 유효합니다. 그러나 기본 클래스는 파생 된 클래스에서 `z` 변수의 그림자 버전에 액세스할 수 `basObj.z` 없으므로 컴파일러는 원래 기본 클래스 값으로 확인합니다.  
  
## <a name="see-also"></a>참고 항목

- [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [재정의](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
