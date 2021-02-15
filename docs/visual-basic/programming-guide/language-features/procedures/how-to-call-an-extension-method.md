---
description: '자세한 정보: 방법: 확장 메서드 호출 (Visual Basic)'
title: '방법: 확장 메서드 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: ec5217526eb0cb28d172ab917df08a8bfe87fe95
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471385"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>방법: 확장명 메서드 호출(Visual Basic)

확장 메서드를 사용 하 여 기존 클래스에 메서드를 추가할 수 있습니다. 확장 메서드를 선언 하 고 범위로 가져온 후에는 확장 하는 형식의 인스턴스 메서드와 같이 호출할 수 있습니다. 확장 메서드를 작성 하는 방법에 대 한 자세한 내용은 [방법: 확장 메서드 작성](./how-to-write-an-extension-method.md)을 참조 하세요.

 다음 지침은 확장 메서드를 참조 합니다 `PrintAndPunctuate` .이 메서드는이 메서드를 호출 하는 문자열 인스턴스를 표시 하 고 두 번째 매개 변수에 대해에서 전송 된 값을 표시 합니다 `punc` .

```vb
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

메서드는 호출 될 때 범위 내에 있어야 합니다.

### <a name="to-call-an-extension-method"></a>확장 메서드를 호출 하려면

1. 확장 메서드의 첫 번째 매개 변수 데이터 형식이 있는 변수를 선언 합니다. 의 경우 `PrintAndPunctuate` 변수가 필요 합니다 <xref:System.String> .

    ```vb
    Dim example = "Ready"
    ```

2. 해당 변수는 확장 메서드를 호출 하 고, 해당 값은 첫 번째 매개 변수에 바인딩됩니다 `aString` . 다음 호출 문이 표시 됩니다 `Ready?` .

    ```vb
    example.PrintAndPunctuate("?")
    ```

     이 확장 메서드에 대 한 호출은 <xref:System.String> 하나의 매개 변수를 필요로 하는 인스턴스 메서드 중 하나를 호출 하는 것과 같습니다.

    ```vb
    example.EndsWith("dy")
    example.IndexOf("R")
    ```

3. 다른 문자열 변수를 선언 하 고 메서드를 다시 호출 하 여 문자열에서 작동 하는지 확인 합니다.

    ```vb
    Dim example2 = " or not"
    example2.PrintAndPunctuate("!!!")
    ```

     이 시간에 대 한 결과입니다 `or not!!!` .

## <a name="example"></a>예

 다음 코드는 간단한 확장 메서드를 만들고 사용 하는 전체 예제입니다.

```vb
Imports System.Runtime.CompilerServices
Imports ConsoleApplication1.StringExtensions

Module Module1

    Sub Main()

        Dim example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")

        Dim example2 = "Goodbye"
        example2.PrintAndPunctuate("?")
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module

' Output:
' Hello.
' Hello!!!!
' Goodbye?
```

## <a name="see-also"></a>추가 정보

- [방법: 확장 메서드 쓰기](./how-to-write-an-extension-method.md)
- [확장명 메서드](./extension-methods.md)
- [Visual Basic의 범위](../declared-elements/scope.md)
