---
title: '방법: 대리자 메서드 (Visual Basic) 호출'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: ac3e32010e7c20ba76e39915d694b11ab3a65d40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973331"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>방법: 대리자 메서드 (Visual Basic) 호출
이 예제에서는 대리자를 사용 하 여 메서드를 연결할 대리자를 통해 해당 메서드를 호출 하는 방법을 보여 줍니다.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>대리자 및 일치 하는 프로시저 만들기  
  
1. 명명 된 대리자를 만드는 `MySubDelegate`합니다.  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2. 대리자와 동일한 시그니처가 있는 메서드를 포함 하는 클래스를 선언 합니다.  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3. 대리자의 인스턴스를 만들고 기본 제공을 호출 하 여 대리자를 사용 하 여 연결 된 메서드를 호출 하는 메서드를 정의 `Invoke` 메서드.  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a>참고자료

- [Delegate 문](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [다중 스레드 애플리케이션](../../../../standard/threading/using-threads-and-threading.md)
