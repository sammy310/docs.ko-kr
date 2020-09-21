---
title: NameOf 연산자
description: Visual Basic에서 NameOf 연산자를 사용 하는 방법에 대해 알아봅니다.
ms.date: 10/27/2019
f1_keywords:
- NameOf
- vb.NameOf
helpviewer_keywords:
- NameOf operator [Visual Basic]
ms.openlocfilehash: 0e72c4cb0c10113e53067ea4a743ca5ee77bcc95
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828905"
---
# <a name="nameof-operator---visual-basic"></a>NameOf 연산자-Visual Basic

`NameOf` 연산자는 변수, 형식 또는 멤버의 이름을 문자열 상수로 가져옵니다.

```vb
Console.WriteLine(NameOf(System.Collections.Generic))  ' output: Generic
Console.WriteLine(NameOf(List(Of Integer)))  ' output: List
Console.WriteLine(NameOf(List(Of Integer).Count))  ' output: Count
Console.WriteLine(NameOf(List(Of Integer).Add))  ' output: Add

Dim numbers As New List(Of Integer) From { 1, 2, 3 }
Console.WriteLine(NameOf(numbers))  ' output: numbers
Console.WriteLine(NameOf(numbers.Count))  ' output: Count
Console.WriteLine(NameOf(numbers.Add))  ' output: Add
```

이전 예제와 같이 형식 및 네임스페이스의 경우 생성되는 이름은 일반적으로 [정규화된](~/_csharplang/spec/basic-concepts.md#fully-qualified-names) 이름이 아닙니다.

`NameOf` 연산자는 컴파일 시간에 평가되며 런타임에는 영향을 주지 않습니다.

`NameOf` 연산자를 사용하여 인수 검사 코드를 더 쉽게 유지 관리할 수 있습니다.

```vb
Private _name As String

Public Property Name As String
    Get
        Return _name
    End Get
    Set
        If value Is Nothing Then
            Throw New ArgumentNullException(NameOf(value), $"{NameOf(name)} cannot be null.")
        End If
    End Set
End Property
```

`NameOf`연산자는 Visual Basic 14 이상에서 사용할 수 있습니다.

## <a name="see-also"></a>참조

- [Visual Basic 언어 참조](../index.md)
- [연산자(Visual Basic)](index.md)
