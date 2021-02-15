---
description: "자세한 정보: BC30685: ' ' <membername> 이 (가) 상속 된 인터페이스 ' <interfacename1> ' 및 ' '에서 모호 합니다. <interfacename2>"
title: "'<membername>'은(는) 상속된 인터페이스 '<interfacename1>' 및 '<interfacename2>'에서 모호합니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: cb8d5da2f95cca5a1668a19dbc1ec313732882ad
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471034"
---
# <a name="bc30685-membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a>BC30685: ' '은 (는) \<membername> 상속 된 인터페이스 ' \<interfacename1> ' 및 ' \<interfacename2> '에서 모호 합니다.

인터페이스는 여러 인터페이스에서 이름이 같은 멤버를 두 개 이상 상속 합니다.

 **오류 ID:** BC30685

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 사용 하려는 기본 인터페이스로 값을 캐스팅 합니다. 예를 들어:

    ```vb
    Interface Left
        Sub MySub()
    End Interface

    Interface Right
        Sub MySub()
    End Interface

    Interface LeftRight
        Inherits Left, Right
    End Interface

    Module test
        Sub Main()
            Dim x As LeftRight
            ' x.MySub()  'x is ambiguous.
            CType(x, Left).MySub() ' Cast to base type.
            CType(x, Right).MySub() ' Call the other base type.
        End Sub
    End Module
    ```

## <a name="see-also"></a>추가 정보

- [인터페이스](../../programming-guide/language-features/interfaces/index.md)
