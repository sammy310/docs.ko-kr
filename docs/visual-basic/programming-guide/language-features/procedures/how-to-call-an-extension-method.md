---
title: '방법: 확장명 메서드 (Visual Basic) 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 5cb0684637a716dfec947740ba345c62eaabddd7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863677"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>방법: 확장명 메서드 (Visual Basic) 호출
확장 메서드를 사용 하면 기존 클래스에 메서드를 추가할 수 있습니다. 확장 메서드는 선언 되 고 범위로, 후 확장 하는 형식의 인스턴스 메서드처럼 호출할 수 있습니다. 확장 메서드를 작성 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 확장명 메서드 작성](./how-to-write-an-extension-method.md)합니다.  
  
 확장 메서드를 다음 지침을 참조 하세요 `PrintAndPunctuate`, 두 번째 매개 변수에서 보내지는 뒤에 원하는 값으로 호출 하는 문자열 인스턴스가 표시 됩니다 `punc`합니다.  
  
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
  
 메서드 호출 될 때 범위에 있어야 합니다.  
  
### <a name="to-call-an-extension-method"></a>확장 메서드를 호출 합니다.  
  
1. 확장 메서드의 첫 번째 매개 변수의 데이터 형식이 있는 변수를 선언 합니다. 에 대 한 `PrintAndPunctuate`, 필요한를 <xref:System.String> 변수:  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2. 변수는 확장 메서드를 호출 하 고 해당 값이 첫 번째 매개 변수에 바인딩된 `aString`합니다. 다음 호출 문을 표시 됩니다 `Ready?`합니다.  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     이 확장 메서드를 호출 하는 등의 하나를 호출 하 여 <xref:System.String> 인스턴스 매개 변수 하나 필요로 하는 메서드:  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3. 다른 문자열 변수를 선언 하 고 모든 문자열을 사용 하 여 작동 하는지 확인 하려면 다시 메서드를 호출 합니다.  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     결과이 시간은: `or not!!!`합니다.  
  
## <a name="example"></a>예제  
 다음 코드 작성의 전체 예제 이며 간단한 확장 메서드를 사용 합니다.  
  
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
  
## <a name="see-also"></a>참고자료

- [방법: 확장명 메서드 작성](./how-to-write-an-extension-method.md)
- [확장명 메서드](./extension-methods.md)
- [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
