---
title: '방법: 대리자 메서드 호출'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: f319727c007b93c7b334af0598f1b9f7c034144d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410723"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>방법: 대리자 메서드 호출(Visual Basic)

이 예제에서는 메서드를 대리자와 연결한 다음 대리자를 통해 해당 메서드를 호출 하는 방법을 보여 줍니다.

### <a name="create-the-delegate-and-matching-procedures"></a>대리자 및 일치 프로시저 만들기

1. 이라는 대리자를 만듭니다 `MySubDelegate` .

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. 대리자와 동일한 시그니처를 사용 하 여 메서드를 포함 하는 클래스를 선언 합니다.

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. 대리자의 인스턴스를 만들고 기본 제공 메서드를 호출 하 여 대리자와 연결 된 메서드를 호출 하는 메서드를 정의 `Invoke` 합니다.

    ```vb
    Protected Sub DelegateTest()
        Dim c1 As New class1
        ' Create an instance of the delegate.
        Dim msd As MySubDelegate = AddressOf c1.Sub1
        ' Call the method.
        msd.Invoke(10)
    End Sub
    ```

## <a name="see-also"></a>참고 항목

- [Delegate 문](../../../language-reference/statements/delegate-statement.md)
- [대리자](index.md)
- [이벤트](../events/index.md)
- [다중 스레드 애플리케이션](../../../../standard/threading/using-threads-and-threading.md)
