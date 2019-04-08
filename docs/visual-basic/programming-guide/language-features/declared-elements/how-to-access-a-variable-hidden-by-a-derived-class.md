---
title: '방법: 파생된 클래스 (Visual Basic)에 의해 숨겨진 변수에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: a97a51d4570d87eaa873fb3152ad810f528dff46
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832179"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>방법: 파생된 클래스 (Visual Basic)에 의해 숨겨진 변수에 액세스
변수에 액세스 하는 파생된 클래스에서 코드를 컴파일러가 파생 단계의 이전 버전과 액세스 하는 클래스에서 액세스할 수 있는 버전 즉, 가장 가까운 액세스할 수 있는 버전에 대 한 참조에 확인 일반적으로 합니다. 파생된 클래스에서 변수를 정의 하는 경우 코드에 일반적으로 해당 정의 액세스 합니다.  
  
 파생된 클래스 변수의 기본 클래스에서 변수를 숨기면이 기본 클래스 버전을 숨깁니다. 한정 하면 기본 클래스 변수에 액세스할 수는 있지만 `MyBase` 키워드입니다.  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>파생된 클래스에 의해 숨겨진 기본 클래스 변수에 액세스  
  
-   식 또는 대입문, 변수 이름 앞에 야 합니다 `MyBase` 키워드와 마침표 (`.`).  
  
     컴파일러는 변수의 기본 클래스 버전에 대 한 참조를 확인합니다.  
  
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
 위험을 낮추기 위해서는 숨겨진 변수의 의도 하지 않은 버전에 대 한 참조를 완전히 숨겨진된 변수에 대 한 모든 참조를 한정할 수 있습니다. 숨김 변수 이름이 같은 둘 이상의 버전을 소개합니다. 코드 문이 변수 이름에는 참조, 컴파일러 참조를 확인 하는 버전 코드 문의 위치 및 한정 문자열의 현재 상태 등의 요인에 따라 달라 집니다. 잘못 된 버전의 변수 참조의 위험이 있습니다이 합니다.  
  
## <a name="see-also"></a>참고자료

- [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Visual Basic의 숨김 기능](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [숨기기와 재정의의 차이점](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [방법: 변수 이름이 같은 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [방법: 상속된 된 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [재정의](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
