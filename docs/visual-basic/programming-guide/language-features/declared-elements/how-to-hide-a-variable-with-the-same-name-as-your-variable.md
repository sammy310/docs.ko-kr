---
title: '방법: 변수 (Visual Basic) 이름이 같은 변수 숨기기'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: 744c7aed50690d5591d1e8248e121cb66ef39108
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296188"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>방법: 변수 (Visual Basic) 이름이 같은 변수 숨기기
변수를 숨길 수 있습니다 *섀도잉* 즉, 이름이 같은 변수를 사용 하 여 정의 하 여 합니다. 두 가지 방법으로 숨기려는 변수의 섀도잉할 수 있습니다.  
  
-   **범위를 통한 숨기기.** 숨기려는 변수를 포함 하는 영역 부분 내에서 다시 선언 하 여 범위를 통한 숨길 수 있습니다.  
  
-   **상속을 통한 숨기기.** 숨기려는 변수의 클래스 수준에서 정의 하는 경우 숨길 수 있습니다 상속을 통해 사용 하 여 다시 선언 하 여 합니다 [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md) 파생된 클래스에서 키워드입니다.  
  
## <a name="two-ways-to-hide-a-variable"></a>두 가지 방법으로 변수를 숨기려면  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>범위를 통해 여 변수를 숨기려면  
  
1. 숨기려는 변수를 정의 하는 영역을 확인 하 고 변수를 사용 하 여 다시 지정 하는 하위 영역을 결정 합니다.  
  
    |변수의 지역|다시 정의할 수 있는 허용 되는 하위 영역|  
    |-----------------------|-------------------------------------------|  
    |Module|모듈 내의 클래스|  
    |클래스|클래스 내에서 하위 클래스<br /><br /> 클래스 내의 프로시저|  
  
     예를 들어 해당 프로시저 내에서 프로시저 변수를 재정의할 수 없습니다는 `If`... `End If` 생성 또는 `For` 루프입니다.  
  
2. 아직 없는 경우 하위 영역을 만듭니다.  
  
3. 동일한 하위 지역, 내에서 쓰기를 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 숨기는 변수를 선언 합니다.  
  
     변수 이름에도 다른 여러 가지 동일한 하위 지역 내에서 코드를 참조 하는 경우 컴파일러가 섀도잉 변수의에 대 한 참조를 확인 합니다.  
  
     다음 예제는 숨기기를 무시 하는 참조 뿐만 아니라 범위를 통한 숨김입니다.  
  
    ```  
    Module shadowByScope  
        ' The following statement declares num as a module-level variable.  
        Public num As Integer  
        Sub show()  
            ' The following statement declares num as a local variable.  
            Dim num As Integer  
            ' The following statement sets the value of the local variable.  
            num = 2  
            ' The following statement displays the module-level variable.  
            MsgBox(CStr(shadowByScope.num))  
        End Sub  
        Sub useModuleLevelNum()  
            ' The following statement sets the value of the module-level variable.  
            num = 1  
            show()  
        End Sub  
    End Module  
    ```  
  
     앞의 예제는 변수 선언 `num` 프로시저 수준 및 모듈 수준 (프로시저에서 `show`). 지역 변수 `num` 모듈 수준 변수를 숨깁니다 `num` 내에서 `show`이므로 로컬 변수 2로 설정 됩니다. 그러나 변수가 없습니다 로컬 그림자 `num` 에 `useModuleLevelNum` 프로시저. 따라서 `useModuleLevelNum` 모듈 수준 변수의 값을 1로 설정 합니다.  
  
     합니다 `MsgBox` 내에서 호출할 `show` 정규화 하 여 숨김 메커니즘을 우회 `num` 모듈 이름입니다. 따라서 로컬 변수 대신 모듈 수준 변수만 표시 됩니다.  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>상속을 통해 변수를 숨기려면  
  
1. 클래스 및 클래스 수준 (프로시저) 외부에서 숨기려는 변수가 선언 해야 합니다. 그렇지 않은 경우 상속을 통해 숨길 수 없습니다.  
  
2. 아직 없는 경우 변수의 클래스에서 파생 된 클래스를 정의 합니다.  
  
3. 파생된 클래스 내에서 작성 한 `Dim` 문에 변수를 선언 합니다. 포함 된 [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md) 선언에서 키워드입니다.  
  
     변수 이름에도 다른 여러 가지 파생된 클래스에서 코드를 참조 하는 경우 컴파일러는 변수에 대 한 참조를 확인 합니다.  
  
     다음 예제에서는 상속을 통한 숨김 보여 줍니다. 두 참조가 숨기는 변수에 액세스 하는, 하나는 숨기기를 무시 하는 수 있습니다.  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                 vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     앞의 예제는 변수를 선언 `shadowString` 기본 클래스에서 파생된 클래스에서이 숨깁니다. 절차 `showStrings` 파생된 클래스에서 문자열의 숨김 버전을 표시 하면 이름을 `shadowString` 한정 되지 않습니다. 다음 숨겨진된 버전을 표시 하면 `shadowString` 으로 한정 됩니다는 `MyBase` 키워드.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 숨김 변수 이름이 같은 둘 이상의 버전을 소개합니다. 코드 문이 변수 이름에는 참조, 컴파일러 참조를 확인 하는 버전 코드 문의 위치 및 한정 문자열의 현재 상태 등의 요인에 따라 달라 집니다. 숨겨진 변수의 의도 하지 않은 버전으로 참조 위험이 증가 수이 있습니다. 숨겨진된 변수에 대 한 모든 참조를 정규화 하 여 위험을 낮출 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Visual Basic의 숨김 기능](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [숨기기와 재정의의 차이점](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [방법: 상속된 된 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [방법: 파생된 클래스에 의해 숨겨진 변수에 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [재정의](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
