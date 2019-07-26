---
title: 기본 속성 액세스가 '<defaultpropertyname>' 인터페이스의 상속된 인터페이스 멤버 '<interfacename1>'과(와) '<defaultpropertyname>' 인터페이스의 상속된 인터페이스 멤버 '<interfacename2>' 사이에서 모호합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: a36cfe8e5496bbfd1941afa8a46086491ae96a2a
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512747"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a>'\<\<I>\< ' 인터페이스와 'defaultpropertyname>'인터페이스의상속된인터페이스멤버'defaultpropertyname>'간에기본속성액세스가모호합니다.\< interfacename2 > '

인터페이스는 두 인터페이스에서 상속 되며, 각 인터페이스는 이름이 같은 기본 속성을 선언 합니다. 컴파일러가 한정자를 사용 하지 않고이 기본 속성에 대 한 액세스를 확인할 수 없습니다. 다음은 이에 대한 예입니다.

```vb
Public Interface Iface1
    Default Property prop(ByVal arg As Integer) As Integer
End Interface
Public Interface Iface2
    Default Property prop(ByVal arg As Integer) As Integer
End Interface
Public Interface Iface3
    Inherits Iface1, Iface2
End Interface
Public Class testClass
    Public Sub accessDefaultProperty()
        Dim testObj As Iface3
        Dim testInt As Integer = testObj(1)
    End Sub
End Class
```

를 지정 `testObj(1)`하면 컴파일러에서이를 기본 속성으로 확인 하려고 시도 합니다. 그러나 상속 된 인터페이스 때문에 두 가지 기본 속성을 사용할 수 있으므로 컴파일러에서이 오류를 신호로 보냅니다.

**오류 ID:** BC30686

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 이름이 같은 멤버는 상속 하지 마십시오. 앞의 예제에서에는 `testObj` 의 `Iface2`멤버가 필요 하지 않은 경우 다음과 같이 선언 합니다.

  ```vb
  Dim testObj As Iface1
  ```

  \-또는-

- 클래스에서 상속 하는 인터페이스를 구현 합니다. 그런 다음 서로 다른 이름을 사용 하 여 상속 된 속성을 각각 구현할 수 있습니다. 그러나이 중 하나만 구현 하는 클래스의 기본 속성이 될 수 있습니다. 다음은 이에 대한 예입니다.

  ```vb
  Public Class useIface3
      Implements Iface3
      Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop
          ' Insert code to define Get and Set procedures for prop1.
      End Property
      Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop
          ' Insert code to define Get and Set procedures for prop2.
      End Property
  End Class
  ```

## <a name="see-also"></a>참고자료

- [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
