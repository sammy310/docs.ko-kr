---
title: 상속 기본 사항
ms.date: 07/20/2015
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
ms.openlocfilehash: 89fcf2a14d8938d536aa72628218242811baa1a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401462"
---
# <a name="inheritance-basics-visual-basic"></a>상속 기본 사항(Visual Basic)

문은 `Inherits` *기본*클래스라고 하는 기존 클래스를 기반으로 *파생 클래스라고*하는 새 클래스를 선언하는 데 사용됩니다. 파생 클래스는 기본 클래스에 정의된 속성, 메서드, 이벤트, 필드 및 상수를 상속하고 확장할 수 있습니다. 다음 섹션에서는 상속에 대한 몇 가지 규칙과 클래스가 상속되거나 상속되는 방식을 변경하는 데 사용할 수 있는 수정자를 설명합니다.

- 기본적으로 키워드로 표시되지 않는 한 모든 `NotInheritable` 클래스를 상속할 수 있습니다. 클래스는 프로젝트의 다른 클래스 또는 프로젝트에서 참조하는 다른 어셈블리의 클래스에서 상속할 수 있습니다.

- 여러 상속을 허용하는 언어와 달리 Visual Basic은 클래스에서 단일 상속만 허용합니다. 즉, 파생 클래스에는 하나의 기본 클래스만 있을 수 있습니다. 클래스에서는 여러 상속이 허용되지 않지만 클래스는 동일한 끝을 효과적으로 수행할 수 있는 여러 인터페이스를 구현할 수 있습니다.

- 기본 클래스에서 제한된 항목이 노출되지 않도록 하려면 파생 클래스의 액세스 형식이 기본 클래스와 같거나 더 제한적이어야 합니다. 예를 들어 `Public` 클래스는 a `Friend` 또는 `Private` 클래스를 `Friend` 상속할 수 `Private` 없으며 클래스는 클래스를 상속할 수 없습니다.

## <a name="inheritance-modifiers"></a>상속 수정자

Visual Basic은 상속을 지원하기 위해 다음 클래스 수준 문 및 수정자를 소개합니다.

- `Inherits`문 — 기본 클래스를 지정합니다.

- `NotInheritable`수정자 - 프로그래머가 클래스를 기본 클래스로 사용하지 못하도록 합니다.

- `MustInherit`수정자 - 클래스가 기본 클래스로만 사용하도록 지정합니다. 클래스의 `MustInherit` 인스턴스를 직접 만들 수 없습니다. 파생 클래스의 기본 클래스 인스턴스로만 만들 수 있습니다. C++ 및 C#과 같은 다른 프로그래밍 언어는 *추상 클래스라는* 용어를 사용하여 이러한 클래스를 설명합니다.

## <a name="overriding-properties-and-methods-in-derived-classes"></a>파생 클래스에서 속성 및 메서드 재정의

기본적으로 파생 된 클래스는 기본 클래스에서 속성 및 메서드를 상속 합니다. 상속된 속성 또는 메서드파생 클래스에서 다르게 작동 해야 하는 경우 *재정의할*수 있습니다. 즉, 파생 클래스에서 메서드의 새 구현을 정의할 수 있습니다. 다음 한정자는 속성 및 메서드가 재정의되는 방식을 제어하는 데 사용됩니다.

- `Overridable`— 파생 클래스에서 클래스의 속성 또는 메서드를 재정의할 수 있습니다.

- `Overrides`— 기본 `Overridable` 클래스에 정의된 속성 또는 메서드를 재정의합니다.

- `NotOverridable`— 상속 클래스에서 속성 또는 메서드가 재정의되지 않도록 합니다. 기본적으로 `Public` 메서드는 `NotOverridable`는 .

- `MustOverride`— 파생 클래스가 속성 또는 메서드를 재정의하도록 요구합니다. 키워드를 `MustOverride` 사용하는 경우 메서드 정의는 `Sub`" `Function`또는 `Property` 문으로만 구성됩니다. 다른 문은 허용되지 않으며 구체적으로 는 `End Sub` `End Function` 또는 문이 없습니다. `MustOverride`메서드를 클래스에서 `MustInherit` 선언해야 합니다.

급여를 처리할 클래스를 정의한다고 가정합니다. 일반적인 주에 대한 `Payroll` 급여를 계산하는 메서드가 `RunPayroll` 포함된 일반 클래스를 정의할 수 있습니다. 그런 다음 `Payroll` 직원 보너스를 배포할 `BonusPayroll` 때 사용할 수 있는 보다 전문적인 클래스의 기본 클래스로 사용할 수 있습니다.

클래스는 `BonusPayroll` 기본 `PayEmployee` `Payroll` 클래스에 정의된 메서드를 상속하고 재정의할 수 있습니다.

다음 예제에서는 상속된 메서드를 재정의하는 기본 `Payroll,` 클래스와 파생 `BonusPayroll`클래스를 `PayEmployee`정의합니다. 프로시저를 `RunPayroll`만들고 `Payroll` 개체와 개체를 `BonusPayroll` 함수에 `Pay`전달하여 두 개체의 `PayEmployee` 메서드를 실행합니다.

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a>마이베이스 키워드

키워드는 `MyBase` 클래스의 현재 인스턴스의 기본 클래스를 참조 하는 개체 변수처럼 행동 합니다. `MyBase`파생 클래스에서 재정의되거나 그림자가 있는 기본 클래스 멤버에 액세스하는 데 자주 사용됩니다. 특히 `MyBase.New` 파생 된 클래스 생성자에서 base 클래스 생성자 명시적으로 호출 하는 데 사용 됩니다.

예를 들어 기본 클래스에서 상속된 메서드를 재정의하는 파생 클래스를 디자인한다고 가정합니다. 재정의된 메서드는 기본 클래스의 메서드를 호출하고 다음 코드 조각에 표시된 대로 반환 값을 수정할 수 있습니다.

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

다음 목록에서는 다음 사용에 `MyBase`대한 제한 사항에 대해 설명합니다.

- `MyBase`는 즉시 기본 클래스와 상속된 멤버를 나타냅니다. 클래스의 멤버에 `Private` 액세스하는 데 사용할 수 없습니다.

- `MyBase`는 실제 개체가 아닌 키워드입니다. `MyBase`변수에 할당하거나 프로시저에 전달하거나 비교에 `Is` 사용할 수 없습니다.

- `MyBase` 자격을 갖춘 메서드는 즉시 기본 클래스에 정의할 필요가 없습니다. 대신 간접적으로 상속된 기본 클래스에서 정의될 수 있습니다. 올바르게 컴파일하여 `MyBase` 정규화된 참조를 사용하려면 일부 기본 클래스에는 호출에 나타나는 매개 변수의 이름과 형식과 일치하는 메서드가 포함되어야 합니다.

- 기본 클래스 `MyBase` 메서드를 호출하는 `MustOverride` 데 사용할 수 없습니다.

- `MyBase`자격을 갖추는 데 사용할 수 없습니다. 따라서 다음 코드는 유효하지 않습니다.

  `MyBase.MyBase.BtnOK_Click()`

- `MyBase`모듈에서 사용할 수 없습니다.

- `MyBase`기본 클래스가 다른 어셈블리에 `Friend` 있는 것처럼 표시된 기본 클래스 멤버에 액세스하는 데 사용할 수 없습니다.

자세한 정보 및 다른 예제는 [파생 클래스에 의해 숨겨진 변수에 액세스하는 방법을](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)참조하십시오.

## <a name="the-myclass-keyword"></a>마이클래스 키워드

키워드는 `MyClass` 원래 구현된 클래스의 현재 인스턴스를 참조하는 개체 변수처럼 실행됩니다. `MyClass`유사하지만 `Me`모든 메서드 및 속성 `MyClass` 호출은 메서드 또는 속성이 [초과 ridable이 아닌](../../../../visual-basic/language-reference/modifiers/notoverridable.md)것처럼 처리됩니다. 따라서 메서드 또는 속성파생 클래스에서 재정의의 영향을 받지 않습니다.

- `MyClass`는 실제 개체가 아닌 키워드입니다. `MyClass`변수에 할당하거나 프로시저에 전달하거나 비교에 `Is` 사용할 수 없습니다.

- `MyClass`은 포함 클래스와 해당 상속된 멤버를 나타냅니다.

- `MyClass`멤버에 대한 `Shared` 한정자로 사용할 수 있습니다.

- `MyClass``Shared` 메서드 내에서 사용할 수는 없지만 인스턴스 메서드 내에서 클래스의 공유 멤버에 액세스하는 데 사용할 수 있습니다.

- `MyClass`표준 모듈에서는 사용할 수 없습니다.

- `MyClass`기본 클래스에 정의되고 해당 클래스에 제공된 메서드의 구현이 없는 메서드를 한정하는 데 사용할 수 있습니다. 이러한 참조는 `MyBase.` *Method*와 동일한 의미를 가합니다.

다음 예제는 `Me` 비교 `MyClass`및 .

```vb
Class baseClass
    Public Overridable Sub testMethod()
        MsgBox("Base class string")
    End Sub
    Public Sub useMe()
        ' The following call uses the calling class's method, even if
        ' that method is an override.
        Me.testMethod()
    End Sub
    Public Sub useMyClass()
        ' The following call uses this instance's method and not any
        ' override.
        MyClass.testMethod()
    End Sub
End Class
Class derivedClass : Inherits baseClass
    Public Overrides Sub testMethod()
        MsgBox("Derived class string")
    End Sub
End Class
Class testClasses
    Sub startHere()
        Dim testObj As derivedClass = New derivedClass()
        ' The following call displays "Derived class string".
        testObj.useMe()
        ' The following call displays "Base class string".
        testObj.useMyClass()
    End Sub
End Class
```

재정의하더라도 `derivedClass` `testMethod`키워드는 `MyClass` `useMyClass` 재정의의 효과를 무효화하고 컴파일러는 `testMethod`의 기본 클래스 버전에 대한 호출을 해결합니다.

## <a name="see-also"></a>참고 항목

- [Inherits Statement](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
