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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350827"
---
# <a name="inheritance-basics-visual-basic"></a>상속 기본 사항(Visual Basic)

`Inherits` 문은 *기본 클래스*라고 하는 기존 클래스를 기반으로 *파생 클래스*라고 하는 새 클래스를 선언 하는 데 사용 됩니다. 파생 클래스는 기본 클래스에 정의 된 속성, 메서드, 이벤트, 필드 및 상수를 상속 하 고 확장할 수 있습니다. 다음 섹션에서는 상속에 대 한 몇 가지 규칙과 클래스가 상속 되거나 상속 되는 방식을 변경 하는 데 사용할 수 있는 한정자에 대해 설명 합니다.

- 기본적으로 `NotInheritable` 키워드로 표시 되지 않은 경우 모든 클래스를 상속할 수 있습니다. 클래스는 프로젝트의 다른 클래스나 프로젝트에서 참조 하는 다른 어셈블리의 클래스에서 상속할 수 있습니다.

- 다중 상속을 허용 하는 언어와 달리 Visual Basic에서는 클래스에서 단일 상속만 허용 합니다. 즉, 파생 클래스에는 하나의 기본 클래스만 사용할 수 있습니다. 클래스에서는 여러 상속이 허용 되지 않지만 클래스는 여러 인터페이스를 구현 하 여 동일한 종료를 효과적으로 수행할 수 있습니다.

- 기본 클래스에서 제한 된 항목을 노출 하지 않도록 하려면 파생 클래스의 액세스 형식이 기본 클래스 보다 더 제한적 이거나 더 제한적 이어야 합니다. 예를 들어 `Public` 클래스는 `Friend` 또는 `Private` 클래스를 상속할 수 없으며 `Friend` 클래스는 `Private` 클래스를 상속할 수 없습니다.

## <a name="inheritance-modifiers"></a>상속 한정자

Visual Basic는 다음과 같은 클래스 수준 문과 한정자를 도입 하 여 상속을 지원 합니다.

- `Inherits` statement-기본 클래스를 지정 합니다.

- `NotInheritable` 한정자-프로그래머가 클래스를 기본 클래스로 사용할 수 없도록 합니다.

- `MustInherit` 한정자-클래스를 기본 클래스로만 사용 하도록 지정 합니다. `MustInherit` 클래스의 인스턴스를 직접 만들 수 없습니다. 파생 클래스의 기본 클래스 인스턴스로만 만들 수 있습니다. C++ 및 C#등의 다른 프로그래밍 언어에서는 *추상 클래스* 라는 용어를 사용 하 여 이러한 클래스를 설명 합니다.

## <a name="overriding-properties-and-methods-in-derived-classes"></a>파생 클래스의 속성 및 메서드 재정의

기본적으로 파생 클래스는 기본 클래스의 속성 및 메서드를 상속 합니다. 상속 된 속성 또는 메서드가 파생 클래스에서 다르게 동작 해야 하는 경우 *재정의할*수 있습니다. 즉, 파생 클래스에서 메서드의 새 구현을 정의할 수 있습니다. 다음 한정자는 속성 및 메서드가 재정의되는 방식을 제어하는 데 사용됩니다.

- `Overridable`-클래스의 속성 또는 메서드가 파생 클래스에서 재정의 될 수 있도록 허용 합니다.

- `Overrides`-기본 클래스에 정의 된 `Overridable` 속성 또는 메서드를 재정의 합니다.

- `NotOverridable`-상속 하는 클래스에서 속성 또는 메서드가 재정의 되지 않도록 합니다. 기본적으로 `Public` 메서드는 `NotOverridable`됩니다.

- `MustOverride`-파생 클래스가 속성 또는 메서드를 재정의 해야 합니다. `MustOverride` 키워드를 사용 하는 경우 메서드 정의는 `Sub`, `Function`또는 `Property` 문으로만 구성 됩니다. 다른 문은 허용 되지 않으며 특히 `End Sub` 또는 `End Function` 문이 없습니다. `MustOverride` 메서드는 `MustInherit` 클래스에서 선언 해야 합니다.

급여를 처리 하는 클래스를 정의 하려고 한다고 가정 합니다. 일반적인 주에 대 한 급여를 계산 하는 `RunPayroll` 메서드를 포함 하는 제네릭 `Payroll` 클래스를 정의할 수 있습니다. 그런 다음 `Payroll`를 보다 특수화 된 `BonusPayroll` 클래스의 기본 클래스로 사용할 수 있습니다 .이 클래스는 직원 보너스를 분산 하는 경우에 사용할 수 있습니다.

`BonusPayroll` 클래스는 기본 `Payroll` 클래스에 정의 된 `PayEmployee` 메서드를 상속 하 고 재정의할 수 있습니다.

다음 예제에서는 기본 클래스 `Payroll,` 및 파생 클래스 `BonusPayroll`를 정의 합니다 .이 클래스는 상속 된 메서드 `PayEmployee`를 재정의 합니다. `RunPayroll`프로시저는 `Payroll` 개체와 `BonusPayroll` 개체를 만들어 두 개체의 `PayEmployee` 메서드를 실행 하는 함수 `Pay`에 전달 합니다.

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a>MyBase 키워드

`MyBase` 키워드는 클래스의 현재 인스턴스에 대 한 기본 클래스를 참조 하는 개체 변수 처럼 동작 합니다. `MyBase`은 파생 클래스에서 재정의 되거나 숨겨진 기본 클래스 멤버에 액세스 하는 데 자주 사용 됩니다. 특히 파생 클래스 생성자에서 기본 클래스 생성자를 명시적으로 호출 하는 데 `MyBase.New`를 사용 합니다.

예를 들어 기본 클래스에서 상속 된 메서드를 재정의 하는 파생 클래스를 디자인 한다고 가정 합니다. 재정의 된 메서드는 기본 클래스의 메서드를 호출 하 고 다음 코드 조각과 같이 반환 값을 수정할 수 있습니다.

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

다음 목록에서는 `MyBase`사용에 대 한 제한 사항을 설명 합니다.

- `MyBase`는 직계 기본 클래스 및 상속 된 멤버를 참조 합니다. 클래스의 `Private` 멤버에 액세스 하는 데 사용할 수 없습니다.

- `MyBase`은 실제 개체가 아닌 키워드입니다. `MyBase`를 변수에 할당 하거나 프로시저에 전달 하거나 `Is` 비교에 사용할 수 없습니다.

- `MyBase` 하는 메서드는 직접 실행 기본 클래스에서 정의 하지 않아도 됩니다. 대신 간접적으로 상속 된 기본 클래스에서 정의 될 수 있습니다. `MyBase`으로 정규화 된 참조가 올바르게 컴파일되도록 하려면 일부 기본 클래스에는 호출에 표시 되는 매개 변수의 이름과 형식과 일치 하는 메서드가 포함 되어야 합니다.

- `MyBase`를 사용 하 여 `MustOverride` 기본 클래스 메서드를 호출할 수 없습니다.

- `MyBase`은 자신을 정규화 하는 데 사용할 수 없습니다. 따라서 다음 코드는 유효 하지 않습니다.

  `MyBase.MyBase.BtnOK_Click()`

- `MyBase`는 모듈에서 사용할 수 없습니다.

- 기본 클래스가 다른 어셈블리에 있는 경우 `MyBase`를 사용 하 여 `Friend`으로 표시 된 기본 클래스 멤버에 액세스할 수 없습니다.

자세한 내용 및 다른 예제 [는 방법: 파생 클래스에 의해 숨겨진 변수에 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)를 참조 하세요.

## <a name="the-myclass-keyword"></a>MyClass 키워드

`MyClass` 키워드는 원래 구현 된 클래스의 현재 인스턴스를 참조 하는 개체 변수 처럼 동작 합니다. `MyClass` `Me`와 유사 하지만 `MyClass`의 모든 메서드 및 속성 호출은 메서드 또는 속성이 [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)된 것 처럼 처리 됩니다. 따라서 메서드 또는 속성은 파생 클래스에서 재정의 하는 경우에는 영향을 받지 않습니다.

- `MyClass`은 실제 개체가 아닌 키워드입니다. `MyClass`를 변수에 할당 하거나 프로시저에 전달 하거나 `Is` 비교에 사용할 수 없습니다.

- `MyClass`는 포함 하는 클래스 및 상속 된 멤버를 참조 합니다.

- `MyClass` `Shared` 멤버의 한정자로 사용할 수 있습니다.

- `MyClass`은 `Shared` 메서드 내에서 사용할 수 없지만 인스턴스 메서드 내에서 사용 하 여 클래스의 공유 멤버에 액세스할 수 있습니다.

- `MyClass` 표준 모듈에서 사용할 수 없습니다.

- `MyClass`를 사용 하 여 기본 클래스에 정의 된 메서드를 정규화 하 고 해당 클래스에서 제공 된 메서드를 구현 하지 않을 수 있습니다. 이러한 참조는 `MyBase.`*메서드와*동일한 의미를 갖습니다.

다음 예에서는 `Me`와 `MyClass`를 비교 합니다.

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

`derivedClass`에서 `testMethod`를 재정의 하더라도 `useMyClass`의 `MyClass` 키워드는 재정의 효과를 nullifies 컴파일러는 `testMethod`의 기본 클래스 버전에 대 한 호출을 확인 합니다.

## <a name="see-also"></a>참고 항목

- [Inherits 문](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
