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
ms.openlocfilehash: 81e54875a3c1a4bbc5f5631e7ebac649a2e5afaf
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085895"
---
# <a name="shadowing-in-visual-basic"></a>Visual Basic에서 숨김

두 프로그래밍 요소가 동일한 이름을 공유 하는 경우 그 중 하나는 다른 *요소를 숨기 거 나 숨길*수 있습니다. 이러한 경우에는 숨겨진 요소를 참조할 수 없습니다. 대신, 코드에서 요소 이름을 사용 하는 경우 Visual Basic 컴파일러에서 해당 요소 이름을 숨기는 요소로 확인 합니다.  
  
## <a name="purpose"></a>목적  

 숨김의 주요 목적은 클래스 멤버의 정의를 보호 하는 것입니다. 기본 클래스는 이미 정의한 것과 동일한 이름으로 요소를 만드는 변경 될 수 있습니다. 이 경우 `Shadows` 한정자는 클래스를 통해 참조가 새 기본 클래스 요소가 아닌 사용자가 정의한 멤버로 확인 되도록 합니다.  
  
## <a name="types-of-shadowing"></a>섀도잉 유형  

 요소는 서로 다른 두 가지 방법으로 다른 요소를 숨길 수 있습니다. 섀도잉 요소는 숨겨진 요소를 포함 하는 영역의 하위 영역 내에서 선언할 수 있으며,이 경우 *범위를 통해*숨김은 수행 됩니다. 또는 파생 클래스에서 기본 클래스의 멤버를 다시 정의할 수 있습니다 .이 경우에는 *상속이 상속을 통해*수행 됩니다.  
  
### <a name="shadowing-through-scope"></a>범위를 통한 숨김  

 동일한 모듈, 클래스 또는 구조체의 프로그래밍 요소가 같은 이름을 갖지만 범위를 다르게 지정할 수 있습니다. 두 요소가 이러한 방식으로 선언 되 고 코드가 공유 하는 이름을 참조 하는 경우 범위가 좁은 요소가 다른 요소 (블록 범위는 가장 좁은)를 숨깁니다.  
  
 예를 들어 모듈은 `Public` 라는 변수를 정의할 수 `temp` 있으며 모듈 내의 프로시저는 라는 지역 변수를 선언할 수 있습니다 `temp` . `temp`프로시저 외부에서에 대 한 참조는 변수에 액세스 하는 반면 프로시저 내에서에 대 한 참조는 지역 변수에 액세스 `temp` `Public` 합니다. 이 경우 프로시저 변수는 `temp` 모듈 변수를 숨깁니다 `temp` .  
  
 다음 그림에서는 라는 두 개의 변수를 보여 줍니다 `temp` . 지역 변수는 `temp` `temp` 자체 프로시저 내에서 액세스할 때 멤버 변수를 숨깁니다 `p` . 그러나 키워드는 `MyClass` 숨김을 무시 하 고 멤버 변수에 액세스 합니다.  
  
 ![범위를 통해 숨김을 보여 주는 그래픽입니다.](./media/shadowing/shadow-scope-diagram.gif)
  
 범위를 통한 섀도잉 예제는 [방법: 변수와 이름이 같은 변수 숨기기](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)를 참조 하세요.  
  
### <a name="shadowing-through-inheritance"></a>상속을 통한 숨김  

 파생 클래스가 기본 클래스에서 상속 된 프로그래밍 요소를 다시 정의 하는 경우 다시 정의 하는 요소는 원래 요소를 숨깁니다. 모든 형식의 선언 된 요소 또는 오버 로드 된 요소 집합을 다른 형식으로 숨길 수 있습니다. 예를 들어 `Integer` 변수는 프로시저를 숨길 수 있습니다 `Function` . 다른 프로시저를 사용 하 여 프로시저를 숨기는 경우 다른 매개 변수 목록과 다른 반환 형식을 사용할 수 있습니다.  
  
 다음 그림은 `b` `d` 에서 상속 되는 기본 클래스 및 파생 클래스를 보여 줍니다 `b` . 기본 클래스는 이라는 프로시저를 정의 `proc` 하 고 파생 클래스는 이름이 같은 다른 프로시저를 사용 하 여 해당 프로시저를 숨깁니다. 첫 번째 `Call` 문은 파생 클래스의 숨김에 액세스 합니다 `proc` . 그러나 키워드는 `MyBase` 숨김을 무시 하 고 기본 클래스의 숨겨진 프로시저에 액세스 합니다.  
  
 ![상속을 통한 숨기기 그래픽 다이어그램](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 상속을 통한 숨김 예제는 [방법: 변수와 이름이 같은 변수 숨기기](how-to-hide-a-variable-with-the-same-name-as-your-variable.md) 및 [방법: 상속 된 변수 숨기기](how-to-hide-an-inherited-variable.md)를 참조 하세요.  
  
#### <a name="shadowing-and-access-level"></a>숨김 및 액세스 수준  

 숨김 요소는 파생 클래스를 사용 하 여 코드에서 항상 액세스할 수 있는 것은 아닙니다. 예를 들어, 선언할 수 있습니다 `Private` . 이러한 경우에는 숨김은 발생 하지 않으며, 숨김이 없는 경우 컴파일러는 동일한 요소에 대 한 참조를 확인 합니다. 이 요소는 숨기는 클래스에서 뒤로 derivational 가장 적은 수의 액세스 가능한 요소입니다. 숨겨진 요소가 프로시저인 경우 동일한 이름, 매개 변수 목록 및 반환 형식을 사용 하 여 가장 가까운 액세스 가능한 버전으로 확인 됩니다.  
  
 다음 예제에서는 세 클래스의 상속 계층 구조를 보여 줍니다. 각 클래스는 `Sub` 프로시저 `display` 를 정의 하 고, 각 파생 클래스는 `display` 기본 클래스의 프로시저를 숨깁니다.  
  
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
  
 위의 예제에서 파생 클래스는 프로시저를 `secondClass` `display` 사용 하 여 숨겨집니다 `Private` . 에서 모듈이 호출 되 면 호출 하는 `callDisplay` `display` `secondClass` 코드가 외부에 `secondClass` 있으므로 private 프로시저에 액세스할 수 없습니다 `display` . 숨김은 무효화 되 고 컴파일러는 기본 클래스 프로시저에 대 한 참조를 확인 합니다 `display` .  
  
 그러나 추가 파생 클래스는 `thirdClass` `display` 를로 선언 `Public` 하므로의 코드에서 `callDisplay` 액세스할 수 있습니다.  
  
## <a name="shadowing-and-overriding"></a>숨김 및 재정의  

 숨김과 재정의를 혼동 하지 마십시오. 파생 클래스가 기본 클래스에서 상속 하는 경우와 선언 된 요소를 다른 요소와 모두 재정의 하는 경우 둘 다 사용 됩니다. 하지만 둘 사이에는 상당한 차이점이 있습니다. 비교는 [숨김과 재정의 간의 차이점](differences-between-shadowing-and-overriding.md)을 참조 하세요.  
  
## <a name="shadowing-and-overloading"></a>숨김 및 오버 로드  

 파생 클래스에서 둘 이상의 요소를 사용 하 여 동일한 기본 클래스 요소를 숨기는 경우에는 숨기는 요소가 해당 요소의 오버 로드 된 버전이 됩니다. 자세한 내용은 [Procedure Overloading](../procedures/procedure-overloading.md)을 참조하세요.  
  
## <a name="accessing-a-shadowed-element"></a>숨겨진 요소에 액세스  

 파생 클래스에서 요소에 액세스 하는 경우 일반적으로 키워드를 사용 하 여 요소 이름을 정규화 함으로써 파생 클래스의 현재 인스턴스를 통해이 작업을 수행 `Me` 합니다. 파생 클래스가 기본 클래스의 요소를 숨기는 경우 키워드를 사용 하 여 기본 클래스 요소를 한정 하 여 해당 요소에 액세스할 수 있습니다 `MyBase` .  
  
 숨겨진 요소에 액세스 하는 예제는 [방법: 파생 클래스에 의해 숨겨진 변수에 액세스](how-to-access-a-variable-hidden-by-a-derived-class.md)를 참조 하세요.  
  
### <a name="declaration-of-the-object-variable"></a>개체 변수의 선언입니다.  

 개체 변수를 만드는 방법은 파생 클래스가 숨기는 요소 또는 숨겨진 요소에 액세스 하는지 여부에도 영향을 줄 수 있습니다. 다음 예제에서는 파생 된 클래스에서 두 개의 개체를 만들지만 한 개체가 기본 클래스로 선언 되 고 다른 개체가 파생 클래스로 선언 됩니다.  
  
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
  
 앞의 예제에서 변수는 `basObj` 기본 클래스로 선언 됩니다. 개체를 할당 `dervCls` 하는 것은 확대 변환을 구성 하므로 유효 합니다. 그러나 기본 클래스는 파생 클래스에 있는 변수의 숨김 버전에 액세스할 수 없으므로 `z` 컴파일러가 `basObj.z` 원래 기본 클래스 값으로 확인 됩니다.  
  
## <a name="see-also"></a>참조

- [References to Declared Elements](references-to-declared-elements.md)
- [Visual Basic의 범위](scope.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
- [Overloads](../../../language-reference/modifiers/shadows.md)
- [재정의](../../../language-reference/modifiers/overrides.md)
- [Me, My, MyBase 및 MyClass](../../program-structure/me-my-mybase-and-myclass.md)
- [상속 기본 사항](../objects-and-classes/inheritance-basics.md)
