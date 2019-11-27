---
title: Func 및 Action 제네릭 대리자에 가변성 사용
ms.date: 07/20/2015
ms.assetid: 36c3012f-b39c-493b-b90f-079b5912ac1b
ms.openlocfilehash: 2678abd03f55224720d00509dc44f2db16551193
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349043"
---
# <a name="using-variance-for-func-and-action-generic-delegates-visual-basic"></a><span data-ttu-id="d5865-102">Func 및 Action 제네릭 대리자에 가변성 사용 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5865-102">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>

<span data-ttu-id="d5865-103">이러한 예제는 메서드를 다시 사용하고 코드의 유연성을 높이기 위해 `Func` 및 `Action` 제네릭 대리자에서 공변성(covariance) 및 반공변성(contravariance)을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5865-103">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>

<span data-ttu-id="d5865-104">공 분산 및 반공 분산에 대 한 자세한 내용은 [대리자의 가변성 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5865-104">For more information about covariance and contravariance, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>

## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="d5865-105">공변 형식 매개 변수가 있는 대리자 사용</span><span class="sxs-lookup"><span data-stu-id="d5865-105">Using Delegates with Covariant Type Parameters</span></span>

<span data-ttu-id="d5865-106">다음 예제는 `Func` 대리자에서 공변성(covariance) 지원의 이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5865-106">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="d5865-107">`FindByTitle` 메서드는 `String` 형식의 매개 변수를 가져오고 `Employee` 형식의 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d5865-107">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="d5865-108">그러나 `Func(Of String, Person)`는 `Employee`을 상속하므로 이 메서드를 `Person` 대리자에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5865-108">However, you can assign this method to the `Func(Of String, Person)` delegate because `Employee` inherits `Person`.</span></span>

```vb
' Simple hierarchy of classes.
Public Class Person
End Class

Public Class Employee
    Inherits Person
End Class

Class Finder
    Public Shared Function FindByTitle(
        ByVal title As String) As Employee
        ' This is a stub for a method that returns
        ' an employee that has the specified title.
        Return New Employee
    End Function

    Sub Test()
        ' Create an instance of the delegate without using variance.
        Dim findEmployee As Func(Of String, Employee) =
            AddressOf FindByTitle

        ' The delegate expects a method to return Person,
        ' but you can assign it a method that returns Employee.
        Dim findPerson As Func(Of String, Person) =
            AddressOf FindByTitle

        ' You can also assign a delegate
        ' that returns a more derived type to a delegate
        ' that returns a less derived type.
        findPerson = findEmployee
    End Sub
End Class
```

## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="d5865-109">반공변 형식 매개 변수가 있는 대리자 사용</span><span class="sxs-lookup"><span data-stu-id="d5865-109">Using Delegates with Contravariant Type Parameters</span></span>

<span data-ttu-id="d5865-110">다음 예제에서는 제네릭 `Action` 대리자에서 반공변성(contravariance) 지원의 이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5865-110">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="d5865-111">`AddToContacts` 메서드는 `Person` 형식의 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d5865-111">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="d5865-112">그러나 `Action(Of Employee)`는 `Employee`을 상속하므로 이 메서드를 `Person` 대리자에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5865-112">However, you can assign this method to the `Action(Of Employee)` delegate because `Employee` inherits `Person`.</span></span>

```vb
Public Class Person
End Class

Public Class Employee
    Inherits Person
End Class

Class AddressBook
    Shared Sub AddToContacts(ByVal person As Person)
        ' This method adds a Person object
        ' to a contact list.
    End Sub

    Sub Test()
        ' Create an instance of the delegate without using variance.
        Dim addPersonToContacts As Action(Of Person) =
            AddressOf AddToContacts

        ' The Action delegate expects
        ' a method that has an Employee parameter,
        ' but you can assign it a method that has a Person parameter
        ' because Employee derives from Person.
        Dim addEmployeeToContacts As Action(Of Employee) =
            AddressOf AddToContacts

        ' You can also assign a delegate
        ' that accepts a less derived parameter
        ' to a delegate that accepts a more derived parameter.
        addEmployeeToContacts = addPersonToContacts
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="d5865-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5865-113">See also</span></span>

- [<span data-ttu-id="d5865-114">공변성(covariance) 및 반공변성(contravariance)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5865-114">Covariance and Contravariance (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="d5865-115">제네릭</span><span class="sxs-lookup"><span data-stu-id="d5865-115">Generics</span></span>](../../../../standard/generics/index.md)
