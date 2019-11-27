---
title: 제네릭 컬렉션용 인터페이스의 가변성 사용
ms.date: 07/20/2015
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
ms.openlocfilehash: 6ee133dfd61d7d7a88243ca592642ff21e0c2223
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349016"
---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a><span data-ttu-id="94a83-102">제네릭 컬렉션에 대 한 인터페이스에서 가변성 사용 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94a83-102">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>

<span data-ttu-id="94a83-103">공변(covariant) 인터페이스는 메서드가 인터페이스에 지정된 것보다 더 많은 수의 파생된 형식을 반환하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="94a83-103">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="94a83-104">반공변(contravariant) 인터페이스는 메서드가 인터페이스에 지정된 것보다 더 적은 파생된 형식의 매개 변수를 수락하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="94a83-104">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>

<span data-ttu-id="94a83-105">.NET Framework 4에서는 몇 가지 기존 인터페이스가 공변(covariant) 및 반공변(contravariant)이 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="94a83-105">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="94a83-106">여기에는 <xref:System.Collections.Generic.IEnumerable%601> 및 <xref:System.IComparable%601>이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="94a83-106">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="94a83-107">따라서 파생된 형식의 컬렉션에 대한 기본 형식의 제네릭 컬렉션과 함께 작동하는 메서드를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a83-107">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>

<span data-ttu-id="94a83-108">.NET Framework의 variant 인터페이스 목록은 [제네릭 인터페이스의 가변성 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="94a83-108">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>

## <a name="converting-generic-collections"></a><span data-ttu-id="94a83-109">제네릭 컬렉션 변환</span><span class="sxs-lookup"><span data-stu-id="94a83-109">Converting Generic Collections</span></span>

<span data-ttu-id="94a83-110">다음 예제에서는 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스에서 공변성(Covariance) 지원의 이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94a83-110">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="94a83-111">`PrintFullName` 메서드는 `IEnumerable(Of Person)` 형식의 컬렉션을 매개 변수로 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="94a83-111">The `PrintFullName` method accepts a collection of the `IEnumerable(Of Person)` type as a parameter.</span></span> <span data-ttu-id="94a83-112">그러나 `IEnumerable(Of Person)`는 `Employee`을 상속하므로 `Person` 형식의 컬렉션에 대해 이를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a83-112">However, you can reuse it for a collection of the `IEnumerable(Of Person)` type because `Employee` inherits `Person`.</span></span>

```vb
' Simple hierarchy of classes.
Public Class Person
    Public Property FirstName As String
    Public Property LastName As String
End Class

Public Class Employee
    Inherits Person
End Class

' The method has a parameter of the IEnumerable(Of Person) type.
Public Sub PrintFullName(ByVal persons As IEnumerable(Of Person))
    For Each person As Person In persons
        Console.WriteLine(
            "Name: " & person.FirstName & " " & person.LastName)
    Next
End Sub

Sub Main()
    Dim employees As IEnumerable(Of Employee) = New List(Of Employee)

    ' You can pass IEnumerable(Of Employee),
    ' although the method expects IEnumerable(Of Person).

    PrintFullName(employees)

End Sub
```

## <a name="comparing-generic-collections"></a><span data-ttu-id="94a83-113">제네릭 컬렉션 비교</span><span class="sxs-lookup"><span data-stu-id="94a83-113">Comparing Generic Collections</span></span>

<span data-ttu-id="94a83-114">다음 예제에서는 <xref:System.Collections.Generic.IComparer%601> 인터페이스에서 반공변성(Contravariance) 지원의 이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94a83-114">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="94a83-115">`PersonComparer` 클래스는 `IComparer(Of Person)` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="94a83-115">The `PersonComparer` class implements the `IComparer(Of Person)` interface.</span></span> <span data-ttu-id="94a83-116">그러나 `Employee`는 `Employee`을 상속하므로 `Person` 형식 개체의 시퀀스를 비교하기 위해 이 클래스를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a83-116">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>

```vb
' Simple hierarchy of classes.
Public Class Person
    Public Property FirstName As String
    Public Property LastName As String
End Class

Public Class Employee
    Inherits Person
End Class
' The custom comparer for the Person type
' with standard implementations of Equals()
' and GetHashCode() methods.
Class PersonComparer
    Implements IEqualityComparer(Of Person)

    Public Function Equals1(
        ByVal x As Person,
        ByVal y As Person) As Boolean _
        Implements IEqualityComparer(Of Person).Equals

        If x Is y Then Return True
        If x Is Nothing OrElse y Is Nothing Then Return False
        Return (x.FirstName = y.FirstName) AndAlso
            (x.LastName = y.LastName)
    End Function
    Public Function GetHashCode1(
        ByVal person As Person) As Integer _
        Implements IEqualityComparer(Of Person).GetHashCode

        If person Is Nothing Then Return 0
        Dim hashFirstName =
            If(person.FirstName Is Nothing,
            0, person.FirstName.GetHashCode())
        Dim hashLastName = person.LastName.GetHashCode()
        Return hashFirstName Xor hashLastName
    End Function
End Class

Sub Main()
    Dim employees = New List(Of Employee) From {
        New Employee With {.FirstName = "Michael", .LastName = "Alexander"},
        New Employee With {.FirstName = "Jeff", .LastName = "Price"}
    }

    ' You can pass PersonComparer,
    ' which implements IEqualityComparer(Of Person),
    ' although the method expects IEqualityComparer(Of Employee)

    Dim noduplicates As IEnumerable(Of Employee) = employees.Distinct(New PersonComparer())

    For Each employee In noduplicates
        Console.WriteLine(employee.FirstName & " " & employee.LastName)
    Next
End Sub
```

## <a name="see-also"></a><span data-ttu-id="94a83-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="94a83-117">See also</span></span>

- [<span data-ttu-id="94a83-118">제네릭 인터페이스의 가변성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94a83-118">Variance in Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
