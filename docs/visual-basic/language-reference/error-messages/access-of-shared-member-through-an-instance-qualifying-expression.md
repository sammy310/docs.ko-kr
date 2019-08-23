---
title: 인스턴스를 통한 공유 멤버 액세스입니다. 정규화 식을 계산하지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 3174d463744303e8c90ed0b2e1a4d86ed08fbcfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947705"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>인스턴스를 통한 공유 멤버 액세스입니다. 정규화 식을 계산하지 않습니다.
클래스 또는 구조체의 인스턴스 변수는 해당 클래스 또는 구조체에 정의 `Shared` 된 변수, 속성, 프로시저 또는 이벤트에 액세스 하는 데 사용 됩니다. 이 경고는 인스턴스 변수를 사용 하 여 상수, 열거형 또는 중첩 된 클래스 또는 구조체와 같은 클래스 또는 구조체의 암시적으로 공유 되는 멤버에 액세스 하는 경우에도 발생할 수 있습니다.  
  
 멤버를 공유 하는 목적은 해당 멤버의 복사본을 하나만 만들고 해당 복사본을 선언 된 클래스 또는 구조체의 모든 인스턴스에서 사용할 수 있도록 하는 것입니다. 해당 클래스 또는 구조체의 개별 인스턴스를 포함 `Shared` 하는 변수를 통하지 않고 클래스 또는 구조체의 이름을 통해 멤버에 액세스 하는 것과 일치 합니다.  
  
 인스턴스 변수를 통해 `Shared` 멤버에액세스하면멤버가임을감안하여코드를이해하기어렵게만들수있습니다.`Shared` 또한 이러한 액세스 권한이 공유 멤버의 인스턴스를 반환 하는 `Function` 프로시저와 같이 다른 동작을 수행 하는 식의 일부인 경우 식 및 다른 작업을 수행 하는 다른 작업을 무시 Visual Basic.  
  
 자세한 내용 및 예제는 [공유](../../../visual-basic/language-reference/modifiers/shared.md)를 참조 하세요.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC42025  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 다음 예제와 같이 멤버를 정의 하는 클래스 또는 `Shared` 구조체의 이름을 사용 하 여 해당 멤버에 액세스 합니다.  
  
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
> 두 프로그래밍 요소의 이름이 같을 경우 범위의 효과에 대 한 경고를 생성 합니다. 이전 예제에서를 사용 `Dim testClass as testClass = Nothing`하 여 인스턴스를 선언 하는 경우 컴파일러는 클래스 이름을 통해에 대 `testClass.sayHello()` 한 호출을 메서드 액세스로 처리 하 고 경고가 발생 하지 않습니다.  
  
## <a name="see-also"></a>참고자료

- [공유](../../../visual-basic/language-reference/modifiers/shared.md)
- [Visual Basic 범위](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
