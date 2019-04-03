---
title: 인스턴스를 통한 공유 멤버 액세스입니다. 정규화 식을 계산하지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 8e6ddab16c59d7ce95d96b377e3f372f6ebe5278
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843567"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>인스턴스를 통한 공유 멤버 액세스입니다. 정규화 식을 계산하지 않습니다.
클래스 또는 구조체의 인스턴스 변수는 액세스 하는 `Shared` 변수, 속성, 프로시저 또는 해당 클래스 또는 구조체에 정의 된 이벤트입니다. 이 경고는 인스턴스 변수를 사용 하 여 클래스 또는 상수 또는 열거형 또는 중첩 된 클래스 또는 구조체와 같은 구조체의 멤버를 암시적으로 공유를 액세스 하는 경우에 발생할 수 있습니다.  
  
 멤버를 공유의 목적은 해당 멤버의 단일 복사본만 만들고 단일 복사본을 이전에 선언 된 구조체 또는 클래스의 모든 인스턴스를 사용할 수 있도록 합니다. 에 액세스 하려면이 용도와 일치 하는 것을 `Shared` 대신 해당 클래스 또는 구조체의 개별 인스턴스를 보유 하는 변수를 통해 해당 클래스 또는 구조의 이름을 통해 멤버입니다.  
  
 에 액세스 하는 `Shared` 인스턴스 변수를 통해 멤버 멤버가 모호 이해 하기 더 어려운 코드를 만들 수 `Shared`입니다. 또한 이러한 액세스 식의 일부인 경우 수행 하는 다른 작업 등을 `Function` 공유 멤버의 인스턴스를 반환 하는 프로시저, Visual Basic 식 및 수행할 수도 있는 모든 작업을 건너뜁니다.  
  
 자세한 내용 및 예제를 참조 하세요 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC42025  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   클래스 또는 구조체를 정의 하는 이름을 사용 하 여는 `Shared` 멤버는 다음 예와에서 같이 액세스할 수 있습니다.  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
>  동일한 이름을 가진 두 개의 프로그래밍 요소가 범위의 효과 대 한 경고 수 있습니다. 이전 예제를 사용 하 여 인스턴스를 선언 하는 경우 `Dim testClass as testClass = Nothing`, 컴파일러는 호출을 처리 `testClass.sayHello()` 클래스 이름 및 경고 없이 통해 메서드의 액세스 발생 합니다.  
  
## <a name="see-also"></a>참고자료

- [공유](../../../visual-basic/language-reference/modifiers/shared.md)
- [Visual Basic의 범위](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
