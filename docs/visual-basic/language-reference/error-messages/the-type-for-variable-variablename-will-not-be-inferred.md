---
title: "'<variablename>' 변수가 바깥쪽 범위의 필드에 바인딩되어 있으므로 변수의 형식을 유추할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: bcd142785d8ee736c6a1b41950fae80e4d26fa18
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838821"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>변수 형식이 '\<variablename >'는 바깥쪽 범위의 필드에 바인딩되어 있으므로 유추 되지 것입니다
변수 형식이 '\<variablename >'는 바깥쪽 범위의 필드에 바인딩되어 있으므로 유추 되지 것입니다. 이름을 변경 하거나 '\<variablename >', 또는 정규화 된 이름 (예: 'Me.variablename' 또는 'MyBase.variablename')를 사용 합니다.  
  
 코드에서 루프 제어 변수를 클래스 또는 다른 바깥쪽 범위의 필드와 동일한 이름이 있습니다. 제어 변수 없이 사용 되기 때문에 `As` 절 바깥쪽 범위의 필드에 바인딩되어 및 컴파일러에 대 한 새 변수를 만들 하지 않거나 해당 형식을 유추 합니다.  
  
 다음 예에서 `Index`, 제어 변수는 `For` 문이 바인딩되는 `Index` 필드에 `Customer` 클래스입니다. 컴파일러 제어 변수의 새 변수를 만들지 않습니다 `Index` 또는 해당 형식을 유추 합니다.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC42110  
  
### <a name="to-address-this-warning"></a>이 경고를 해결하려면  
  
-   클래스의 필드 이름을 수도 없는 식별자에 해당 이름을 변경 하 여 루프 제어 변수의 로컬을 확인 합니다.  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   바인딩되도록 합니다 루프 제어 변수의 클래스 필드를 접두사로 사용 하 여 `Me.` 변수 이름에 있습니다.  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   지역 형식 유추에 의존 하는 대신 사용 하 여는 `As` 루프 제어 변수의 형식을 지정 하는 절.  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a>예제  
 다음 코드 위치에 있는 첫 번째 수정 앞의 예제를 보여 줍니다.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>참고자료

- [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [방법: 개체의 현재 인스턴스 참조](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Me, My, MyBase 및 MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
