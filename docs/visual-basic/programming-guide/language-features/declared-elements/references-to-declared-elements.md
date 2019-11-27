---
title: References to Declared Elements
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: a6477a9f0abaf8eb9176f4f6ab2a920af6c8f500
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345296"
---
# <a name="references-to-declared-elements-visual-basic"></a>선언된 요소 참조(Visual Basic)
코드가 선언 된 요소를 참조 하는 경우 Visual Basic 컴파일러는 참조의 이름을 해당 이름의 적절 한 선언과 일치 시킵니다. 동일한 이름을 사용 하 여 두 개 이상의 요소를 선언 하는 경우 해당 이름을 *정규화* 하 여 참조할 요소를 제어할 수 있습니다.  
  
 컴파일러는 이름 참조를 가장 *좁은 범위의*이름 선언과 일치 시 키 려 고 합니다. 즉, 참조를 만드는 코드에서 시작 하 고 포함 하는 요소의 연속 수준을 통해 외부에서 작업 합니다.  
  
 다음 예에서는 이름이 같은 두 변수에 대 한 참조를 보여 줍니다. 이 예제에서는 모듈 `container`의 여러 범위 수준에서 이름이 `totalCount`인 두 변수를 선언 합니다. 프로시저 `showCount` 한정자가 없는 `totalCount`를 표시 하는 경우 Visual Basic 컴파일러는 가장 좁은 범위의 선언에 대 한 참조를 확인 합니다. 즉, `showCount`내의 지역 선언입니다. 포함 하는 모듈 `container`를 사용 하 여 `totalCount` 한정 하는 경우 컴파일러는 더 넓은 범위의 선언에 대 한 참조를 확인 합니다.  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a>요소 이름 한정  
 이 검색 프로세스를 재정의 하 고 더 광범위 한 범위에서 선언 된 이름을 지정 하려면 광범위 한 범위의 포함 요소로 이름을 *한정* 해야 합니다. 경우에 따라 포함 하는 요소를 한 정해야 할 수도 있습니다.  
  
 이름을 정규화 하면 원본 문의 앞에 target 요소가 정의 된 위치를 식별 하는 정보가 포함 됩니다. 이 정보를 *한정 문자열*이라고 합니다. 하나 이상의 네임 스페이스와 모듈, 클래스 또는 구조를 포함할 수 있습니다.  
  
 한정 문자열은 대상 요소를 포함 하는 모듈, 클래스 또는 구조체를 명확 하 게 지정 해야 합니다. 컨테이너는 일반적으로 네임 스페이스를 포함 하는 다른 요소에 있을 수 있습니다. 한정 문자열에 포함 된 요소를 여러 개 포함 해야 할 수도 있습니다.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>이름을 한정 하 여 선언 된 요소에 액세스 하려면  
  
1. 요소가 정의 된 위치를 확인 합니다. 여기에는 네임 스페이스 또는 네임 스페이스의 계층 구조도 포함 될 수 있습니다. 가장 낮은 수준의 네임 스페이스 내에서 요소는 모듈, 클래스 또는 구조체에 포함 되어야 합니다.  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2. 대상 요소의 위치를 기준으로 한정 경로를 결정 합니다. 최상위 네임 스페이스로 시작 하 고, 최하위 수준 네임 스페이스로 이동 하 고, target 요소를 포함 하는 모듈, 클래스 또는 구조체를 사용 하 여 종료 합니다. 경로의 각 요소는 뒤에 오는 요소를 포함 해야 합니다.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3. 대상 요소에 대 한 한정 문자열을 준비 합니다. 경로의 모든 요소 뒤에 마침표 (`.`)를 넣습니다. 응용 프로그램에는 한정 문자열의 모든 요소에 대 한 액세스 권한이 있어야 합니다.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. 일반적인 방법으로 target 요소를 참조 하는 식 또는 대입문을 작성 합니다.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. 대상 요소 이름 앞에 한정 문자열을 붙입니다. 이름은 요소를 포함 하는 모듈, 클래스 또는 구조체 뒤에 오는 마침표 (`.`) 바로 뒤에와 야 합니다.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. 컴파일러는 한정 문자열을 사용 하 여 대상 요소 참조와 일치할 수 있는 명확 하 고 명확한 선언을 찾습니다.  
  
 응용 프로그램에 동일한 이름을 가진 둘 이상의 프로그래밍 요소에 대 한 액세스 권한이 있는 경우 이름 참조를 정규화 해야 할 수도 있습니다. 예를 들어 <xref:System.Windows.Forms> 및 <xref:System.Web.UI.WebControls> 네임 스페이스는 모두 `Label` 클래스 (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> 및 <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>)를 포함 합니다. 응용 프로그램이 둘 다를 사용 하거나 자체 `Label` 클래스를 정의 하는 경우 서로 다른 `Label` 개체를 구분 해야 합니다. 변수 선언에 네임 스페이스 또는 가져오기 별칭을 포함 합니다. 다음 예에서는 가져오기 별칭을 사용 합니다.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>다른 포함 하는 요소의 멤버  
 다른 클래스 또는 구조체의 비공유 멤버를 사용 하는 경우 먼저 해당 멤버 이름을 클래스 또는 구조체의 인스턴스를 가리키는 변수나 식으로 정규화 해야 합니다. 다음 예제에서 `demoClass`은 `class1`라는 클래스의 인스턴스입니다.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 클래스 이름 자체를 사용 하 여 [공유](../../../../visual-basic/language-reference/modifiers/shared.md)되지 않은 멤버를 한정할 수는 없습니다. 먼저 개체 변수 (이 경우 `demoClass`)에서 인스턴스를 만든 다음 변수 이름으로 참조 해야 합니다.  
  
 클래스 또는 구조체에 `Shared` 멤버가 있는 경우 해당 멤버를 클래스 또는 구조체 이름으로 사용 하거나 인스턴스를 가리키는 변수나 식으로 한정할 수 있습니다.  
  
 모듈에는 별도의 인스턴스가 없으며 모든 멤버가 기본적으로 `Shared` 됩니다. 따라서 모듈 이름을 사용 하 여 모듈 멤버를 한정 합니다.  
  
 다음 예에서는 모듈 멤버 프로시저에 대 한 정규화 된 참조를 보여 줍니다. 이 예제에서는 프로젝트의 다른 모듈에서 이름이 `perform`인 두 개의 `Sub` 프로시저를 선언 합니다. 각 항목은 고유한 모듈 내에서 한정 없이 지정할 수 있지만 다른 위치에서 참조 하는 경우에는 정규화 되어야 합니다. `module3`의 최종 참조는 `perform`한정 되지 않으므로 컴파일러는 해당 참조를 확인할 수 없습니다.  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a>프로젝트에 대 한 참조  
 다른 프로젝트에 정의 된 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 요소를 사용 하려면 먼저 해당 프로젝트의 어셈블리 또는 형식 라이브러리에 대 한 *참조* 를 설정 해야 합니다. 참조를 설정 하려면 **프로젝트** 메뉴에서 **참조 추가** 를 클릭 하거나 [-reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) 명령줄 컴파일러 옵션을 사용 합니다.  
  
 예를 들어 .NET Framework의 XML 개체 모델을 사용할 수 있습니다. <xref:System.Xml> 네임 스페이스에 대 한 참조를 설정 하는 경우 <xref:System.Xml.XmlDocument>와 같은 해당 클래스를 선언 하 고 사용할 수 있습니다. 다음 예에서는 <xref:System.Xml.XmlDocument>를 사용 합니다.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>포함 하는 요소 가져오기  
 [Imports 문 (.Net 네임 스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 을 사용 하 여 사용 하려는 모듈이 나 클래스를 포함 하는 네임 스페이스를 *가져올* 수 있습니다. 이렇게 하면 이름을 정규화 하지 않고 가져온 네임 스페이스에 정의 된 요소를 참조할 수 있습니다. 다음 예제에서는 이전 예제를 다시 작성 하 여 <xref:System.Xml> 네임 스페이스를 가져옵니다.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 또한 `Imports` 문은 가져온 각 네임 스페이스에 대 한 *가져오기 별칭* 을 정의할 수 있습니다. 이렇게 하면 소스 코드를 더 짧고 읽기 쉽게 만들 수 있습니다. 다음 예에서는 `xD`를 <xref:System.Xml> 네임 스페이스에 대 한 별칭으로 사용 하도록 이전 예제를 다시 작성 합니다.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 `Imports` 문은 응용 프로그램에서 다른 프로젝트의 요소를 사용할 수 있도록 하지 않습니다. 즉, 참조를 설정 하는 대신 사용 됩니다. 네임 스페이스를 가져오면 해당 네임 스페이스에 정의 된 이름을 한정 하는 요구 사항이 제거 됩니다.  
  
 `Imports` 문을 사용 하 여 모듈, 클래스, 구조체 및 열거형을 가져올 수도 있습니다. 그런 다음 이러한 가져온 요소의 멤버를 한정자 없이 사용할 수 있습니다. 그러나 클래스 또는 구조체의 인스턴스로 계산 되는 변수나 식으로 클래스와 구조체의 비공유 멤버를 항상 한정 해야 합니다.  
  
## <a name="naming-guidelines"></a>명명 지침  
 이름이 같은 프로그래밍 요소를 두 개 이상 정의 하면 컴파일러에서 해당 이름에 대 한 참조를 확인 하려고 할 때 *이름 모호성이* 발생할 수 있습니다. 둘 이상의 정의가 범위에 있거나, 범위에 정의가 없는 경우 참조는 해결할 수 없는입니다. 예제를 보려면이 도움말 페이지의 "정규화 된 참조 예제"를 참조 하십시오.  
  
 모든 요소에 고유한 이름을 지정 하 여 이름 모호성을 방지할 수 있습니다. 그런 다음 네임 스페이스, 모듈 또는 클래스를 사용 하 여 해당 이름을 한정할 필요 없이 모든 요소에 대 한 참조를 만들 수 있습니다. 실수로 잘못 된 요소를 참조할 가능성이 줄어듭니다.  
  
## <a name="shadowing"></a>섀도잉  
 두 프로그래밍 요소가 동일한 이름을 공유 하는 경우 그 중 하나는 다른 *요소를 숨기 거 나 숨길*수 있습니다. 숨겨진 요소는 참조에 사용할 수 없습니다. 대신, 코드가 숨겨진 요소 이름을 사용 하는 경우 Visual Basic 컴파일러는 숨기는 요소로이를 확인 합니다. 예제에 대 한 자세한 설명은 [Visual Basic에서 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [선언 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
- [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)
