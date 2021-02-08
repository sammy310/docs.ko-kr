---
description: '자세히 알아보기: BC42026: 식이 포함 하는 속성을 재귀적으로 호출 합니다.<propertyname>'
title: 식이 포함하는 속성 '<propertyname>'을(를) 재귀적으로 호출합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: 4b6abcbab62ae0c4c5b18b0e6946bcfb21857112
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796342"
---
# <a name="bc42026-expression-recursively-calls-the-containing-property-propertyname"></a>BC42026: 식이 포함 하는 속성 ' '을 재귀적으로 호출 합니다. \<propertyname>

`Set`속성 정의 프로시저의 문은 속성 이름에 값을 저장 합니다.

 속성의 값을 유지 하는 권장 방법은 `Private` 속성의 컨테이너에 변수를 정의 하 고 및 프로시저에서 사용 하는 것입니다 `Get` `Set` . `Set`그런 다음이 프로시저는 들어오는 값을이 변수에 저장 해야 합니다 `Private` .

 `Get`프로시저는 프로시저 처럼 동작 `Function` 하므로 문을 발생 시켜 속성 이름에 값을 할당 하 고 컨트롤을 반환할 수 있습니다 `End Get` . 그러나 권장 되는 방법은 `Private` [Return 문의](../statements/return-statement.md)값으로 변수를 포함 하는 것입니다.

 `Set`프로시저는 `Sub` 값을 반환 하지 않는 프로시저 처럼 동작 합니다. 따라서 프로시저 또는 속성 이름에는 프로시저 내에 특별 한 의미가 없으며 `Set` 값을 저장할 수 없습니다.

 다음 예제에서는이 오류를 발생 시킬 수 있는 방법 및 권장 되는 방법을 보여 줍니다.

```vb
Public Class illustrateProperties
' The code in the following property causes this error.
    Public Property badProp() As Char
        Get
            Dim charValue As Char
            ' Insert code to update charValue.
            badProp = charValue
        End Get
        Set(ByVal Value As Char)
            ' The following statement causes this error.
            badProp = Value
            ' The value stored in the local variable badProp
            ' is not used by the Get procedure in this property.
        End Set
    End Property
' The following code uses the recommended approach.
    Private propValue As Char
    Public Property goodProp() As Char
        Get
            ' Insert code to update propValue.
            Return propValue
        End Get
        Set(ByVal Value As Char)
            propValue = Value
        End Set
    End Property
End Class
```

 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.

 **오류 ID:** BC42026

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 앞의 예제에서 설명한 것 처럼 권장 된 방법을 사용 하도록 속성 정의를 다시 작성 합니다.

## <a name="see-also"></a>참고 항목

- [속성 프로시저](../../programming-guide/language-features/procedures/property-procedures.md)
- [Property Statement](../statements/property-statement.md)
- [Set 문](../statements/set-statement.md)
