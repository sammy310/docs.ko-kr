---
title: Visual Basic의 숨김 기능
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
ms.openlocfilehash: 15c7112f7e318542859162655c78e19558178e5a
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411007"
---
# <a name="shadowing-in-visual-basic"></a>Visual Basic의 숨김 기능
동일한 이름을 공유 하는 두 가지 프로그래밍 요소를 숨길 수 중 하나, 또는 *섀도*, 다른 하나입니다. 이러한 상황에서 숨겨진된 요소는 참조를 사용할 수 있습니다. 대신, 요소 이름을 사용 하는 코드를 Visual Basic 컴파일러는 섀도잉 요소 확인 합니다.  
  
## <a name="purpose"></a>용도  
 섀도잉의 주요 목적은 클래스 멤버의 정의 보호 하는 것입니다. 기본 클래스를 이미 정의한 하나로 동일한 이름을 가진 요소를 만드는 경우가 있을 수 있습니다. 이런 경우는 `Shadows` 한정자를 사용 하면 참조 멤버에 해결 해야 할 클래스를 통해 새 기본 클래스 요소에 대신 정의 합니다.  
  
## <a name="types-of-shadowing"></a>숨김 형식  
 요소는 두 가지 방법으로 다른 요소를 숨길 수 있습니다. 섀도잉 요소는 섀도잉 사례 이루어집니다 섀도잉 된 요소를 포함 하는 영역 부분 내에서 선언할 수 있습니다 *범위를 통한*합니다. 파생 클래스는 섀도잉 사례 이루어집니다 기본 클래스의 멤버를 재정의할 수 또는 *상속을 통해*합니다.  
  
### <a name="shadowing-through-scope"></a>범위를 통한 숨김  
 동일한 모듈, 클래스 또는 구조체에 있는 이름은 같지만 다른 범위에서 요소를 프로그래밍 하는 것에 대 한 것 같습니다. 두 요소는이 방식으로 선언 된 공유 이름으로 참조 하는 코드를 더 좁은 범위를 사용 하 여 요소 나머지 요소를 숨깁니다 (블록 범위는 좁음).  
  
 예를 들어, 모듈을 정의할 수는 `Public` 라는 변수 `temp`, 모듈 내의 프로시저도 라는 지역 변수를 선언할 수 있습니다 및 `temp`합니다. 에 대 한 참조 `temp` 내에서 프로시저 액세스에 대 한 참조 하는 동안 로컬 변수의 `temp` 에서 외부 프로시저 액세스는 `Public` 변수입니다. 이 경우 프로시저가 변수 `temp` 숨기는 모듈 변수 `temp`합니다.  
  
 다음 그림에서는 두 개의 변수, 명명 된 두 `temp`합니다. 지역 변수 `temp` 멤버 변수를 숨깁니다 `temp` 자체 프로시저 내에서 액세스할 때 `p`합니다. 그러나는 `MyClass` 키워드는 숨기기를 무시 하 고 멤버 변수에 액세스 합니다.  
  
 ![범위를 통한 숨김 보여 주는 그래픽입니다.](./media/shadowing/shadow-scope-diagram.gif)
  
 범위를 통한 숨김 예제를 참조 하세요. [방법: 변수 이름이 같은 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)합니다.  
  
### <a name="shadowing-through-inheritance"></a>상속을 통한 숨김  
 기본 클래스에서 상속 된 프로그래밍 요소를 다시 정의 하는 파생된 클래스에서 재정의 요소를 원본 요소를 숨깁니다. 모든 형식의 선언 된 요소 또는 오버 로드 된 요소 집합을 다른 형식을 사용 하 여 숨길 수 있습니다. 예를 들어를 `Integer` 변수를 숨길 수 있습니다는 `Function` 프로시저입니다. 다른 프로시저를 사용 하 여 프로시저를 숨길 경우 다른 매개 변수 목록과 다른 반환 형식을 사용할 수 있습니다.  
  
 다음 그림에서는 기본 클래스를 보여 줍니다 `b` 및 파생된 클래스 `d` 에서 상속 되는 `b`합니다. 라는 프로시저를 정의 하는 기본 클래스 `proc`, 파생된 클래스는이 동일한 이름의 다른 프로시저를 사용 하 여 숨깁니다. 첫 번째 `Call` 문에서 섀도잉 액세스 `proc` 파생된 클래스에서. 그러나는 `MyBase` 키워드는 숨기기를 무시 하 고 숨겨진된 프로시저는 기본 클래스에 액세스 합니다.  
  
 ![상속을 통한 숨기기 그래픽 다이어그램](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 상속을 통한 숨김 예제를 참조 하세요. [방법: 변수 이름이 같은 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) 고 [방법: 상속된 된 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)합니다.  
  
#### <a name="shadowing-and-access-level"></a>숨기기와 액세스 수준  
 섀도잉 요소 항상 파생된 클래스를 사용 하는 코드에서 액세스할 수 있는 것은 아닙니다. 예를 들어 선언 될 수 있습니다 `Private`합니다. 이러한 경우 않으며 컴파일러 확인 했을 때 동일한 요소에 대 한 모든 참조 있었다면 섀도잉 되지 않습니다. 이 요소는 파생 단계의 뒤로 숨기는 클래스에서 액세스할 수 있는 요소입니다. 섀도잉 된 요소는 프로시저인 경우 해상도 같은 이름의 매개 변수 목록에 액세스할 수 있는 가장 가까운 버전은 한 반환 형식입니다.  
  
 다음 예제에서는 세 가지 클래스의 상속 계층 구조를 보여 줍니다. 각 클래스 정의 `Sub` 프로시저 `display`, 각 파생 클래스 그림자 및는 `display` 프로시저는 기본 클래스에 합니다.  
  
```  
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
  
 위의 예제에서는 파생된 클래스에서에서 `secondClass` 그림자 `display` 사용 하 여는 `Private` 프로시저입니다. 때 모듈 `callDisplay` 호출 `display` 에 `secondClass`를 호출 하는 코드를 벗어납니다 `secondClass` 따라서 개인에 액세스할 수 없습니다 `display` 프로시저. 섀도잉은, 컴파일러는 기본 클래스에 대 한 참조를 확인 및 `display` 프로시저입니다.  
  
 그러나 추가 파생 클래스 `thirdClass` 선언 `display` 으로 `Public`이므로 코드 `callDisplay` 액세스할 수 있습니다.  
  
## <a name="shadowing-and-overriding"></a>숨기기와 재정의  
 숨김과 재정의 혼동 하지 마십시오. 둘 다에 파생된 클래스는 기본 클래스에서 상속 하 고 다른 하나의 선언 된 요소를 다시 정의 둘 다 때 사용 됩니다. 하지만 둘 사이 중요 한 차이가 있습니다. 비교를 참조 하세요 [차이점 간의 숨기기와 재정의](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)합니다.  
  
## <a name="shadowing-and-overloading"></a>섀도잉 및 오버 로드  
 파생된 클래스에서 둘 이상의 요소를 사용 하 여 동일한 기본 클래스 요소를 숨길 경우 숨기는 요소는 해당 요소의 오버 로드 된 버전이 됩니다. 자세한 내용은 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)을 참조하세요.  
  
## <a name="accessing-a-shadowed-element"></a>섀도잉 된 요소에 액세스  
 파생된 클래스에서 요소를 액세스할 때 일반적으로 이렇게 하면 해당 파생된 클래스의 현재 인스턴스를 통해 사용 하 여 요소 이름을 정규화 하 여는 `Me` 키워드입니다. 파생된 클래스에서 기본 클래스의 요소를 숨기면 한정 기본 클래스 요소에 액세스할 수 있습니다는 `MyBase` 키워드입니다.  
  
 숨겨진된 요소에 액세스 하는 예제를 참조 하세요. [방법: 파생된 클래스에 의해 숨겨진 변수에 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)합니다.  
  
### <a name="declaration-of-the-object-variable"></a>개체 변수 선언  
 파생된 클래스는 섀도잉 요소 또는 숨겨진된 요소에 액세스 하는지 여부를 개체 변수를 만드는 방법을 달라질 수 있습니다. 다음 예제에서는 파생된 클래스에서 두 개체 만들지만 개체 기본 클래스 및 파생된 클래스와 기타로 선언 됩니다.  
  
```  
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
  
 위의 예에서 변수 `basObj` 기본 클래스로 선언 합니다. 할당을 `dervCls` 개체를 확대 변환 구성 요소 이므로 유효 합니다. 그러나 기본 클래스에서 변수 숨김 버전에 액세스할 수 없습니다 `z` 파생된 클래스에서 때문에 컴파일러에서는 `basObj.z` 원래 기본 클래스 값입니다.  
  
## <a name="see-also"></a>참고자료
- [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [재정의](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
