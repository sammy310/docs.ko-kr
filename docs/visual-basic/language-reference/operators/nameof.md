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
# <a name="nameof-operator---visual-basic"></a><span data-ttu-id="8ca2a-103">NameOf 연산자-Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8ca2a-103">NameOf operator - Visual Basic</span></span>

<span data-ttu-id="8ca2a-104">`NameOf` 연산자는 변수, 형식 또는 멤버의 이름을 문자열 상수로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8ca2a-104">The `NameOf` operator obtains the name of a variable, type, or member as the string constant:</span></span>

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

<span data-ttu-id="8ca2a-105">이전 예제와 같이 형식 및 네임스페이스의 경우 생성되는 이름은 일반적으로 [정규화된](~/_csharplang/spec/basic-concepts.md#fully-qualified-names) 이름이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8ca2a-105">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="8ca2a-106">`NameOf` 연산자는 컴파일 시간에 평가되며 런타임에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ca2a-106">The `NameOf` operator is evaluated at compile time, and has no effect at run time.</span></span>

<span data-ttu-id="8ca2a-107">`NameOf` 연산자를 사용하여 인수 검사 코드를 더 쉽게 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ca2a-107">You can use the `NameOf` operator to make the argument-checking code more maintainable:</span></span>

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

<span data-ttu-id="8ca2a-108">`NameOf`연산자는 Visual Basic 14 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ca2a-108">The `NameOf` operator is available in Visual Basic 14 and later.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ca2a-109">참조</span><span class="sxs-lookup"><span data-stu-id="8ca2a-109">See also</span></span>

- [<span data-ttu-id="8ca2a-110">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="8ca2a-110">Visual Basic Language Reference</span></span>](../index.md)
- [<span data-ttu-id="8ca2a-111">연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ca2a-111">Operators (Visual Basic)</span></span>](index.md)
