---
description: '자세한 정보: 방법: LINQ를 사용 하 여 ArrayList 쿼리 (Visual Basic)'
title: '방법: LINQ를 사용하여 ArrayList 쿼리'
ms.date: 07/20/2015
ms.assetid: 176358a9-d765-4b57-9557-7feb4428138d
ms.openlocfilehash: df7c6e1cee6d8e37074ce209f3bea97a402d8dbe
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428521"
---
# <a name="how-to-query-an-arraylist-with-linq-visual-basic"></a><span data-ttu-id="70540-103">방법: LINQ를 사용 하 여 ArrayList 쿼리 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70540-103">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>

<span data-ttu-id="70540-104">LINQ를 사용하여 <xref:System.Collections.ArrayList> 등의 제네릭이 아닌 <xref:System.Collections.IEnumerable> 컬렉션을 쿼리하는 경우 컬렉션에 있는 개체의 특정 형식을 반영하도록 범위 변수의 형식을 명시적으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70540-104">When using LINQ to query non-generic <xref:System.Collections.IEnumerable> collections such as <xref:System.Collections.ArrayList>, you must explicitly declare the type of the range variable to reflect the specific type of the objects in the collection.</span></span> <span data-ttu-id="70540-105">예를 들어 개체의가 있는 <xref:System.Collections.ArrayList> 경우 `Student` [from 절](../../../language-reference/queries/from-clause.md) 은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70540-105">For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [From Clause](../../../language-reference/queries/from-clause.md) should look like this:</span></span>

```vb
Dim query = From student As Student In arrList
'...
```

<span data-ttu-id="70540-106">범위 변수의 형식을 지정하여 <xref:System.Collections.ArrayList>의 각 항목을 `Student`로 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="70540-106">By specifying the type of the range variable, you are casting each item in the <xref:System.Collections.ArrayList> to a `Student`.</span></span>

<span data-ttu-id="70540-107">명시적 형식 범위 변수를 쿼리 식에 사용하는 것은 <xref:System.Linq.Enumerable.Cast%2A> 메서드 호출과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70540-107">The use of an explicitly typed range variable in a query expression is equivalent to calling the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="70540-108">지정된 캐스트를 수행할 수 없는 경우 <xref:System.Linq.Enumerable.Cast%2A>에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="70540-108"><xref:System.Linq.Enumerable.Cast%2A> throws an exception if the specified cast cannot be performed.</span></span> <span data-ttu-id="70540-109"><xref:System.Linq.Enumerable.Cast%2A> 및 <xref:System.Linq.Enumerable.OfType%2A>은 제네릭이 아닌 <xref:System.Collections.IEnumerable> 형식에서 작동하는 두 가지 표준 쿼리 연산자 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="70540-109"><xref:System.Linq.Enumerable.Cast%2A> and <xref:System.Linq.Enumerable.OfType%2A> are the two Standard Query Operator methods that operate on non-generic <xref:System.Collections.IEnumerable> types.</span></span> <span data-ttu-id="70540-110">Visual Basic에서 <xref:System.Linq.Enumerable.Cast%2A> 데이터 소스에 대해 메서드를 명시적으로 호출 하 여 특정 범위 변수 형식을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70540-110">In Visual Basic, you must explicitly call the <xref:System.Linq.Enumerable.Cast%2A> method on the data source to ensure a specific range variable type.</span></span> <span data-ttu-id="70540-111">자세한 내용은 [쿼리 작업의 형식 관계 (Visual Basic)](type-relationships-in-query-operations.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70540-111">For more information, see [Type Relationships in Query Operations (Visual Basic)](type-relationships-in-query-operations.md).</span></span>

## <a name="example"></a><span data-ttu-id="70540-112">예제</span><span class="sxs-lookup"><span data-stu-id="70540-112">Example</span></span>

<span data-ttu-id="70540-113">다음 예제에서는 <xref:System.Collections.ArrayList>에 대한 단순 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70540-113">The following example shows a simple query over an <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="70540-114">이 예제에서는 코드가 <xref:System.Collections.ArrayList.Add%2A> 메서드를 호출할 때 개체 이니셜라이저를 사용하지만 요구 사항은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="70540-114">Note that this example uses object initializers when the code calls the <xref:System.Collections.ArrayList.Add%2A> method, but this is not a requirement.</span></span>

```vb
Imports System.Collections
Imports System.Linq

Module Module1

    Public Class Student
        Public Property FirstName As String
        Public Property LastName As String
        Public Property Scores As Integer()
    End Class

    Sub Main()

        Dim student1 As New Student With {.FirstName = "Svetlana",
                                     .LastName = "Omelchenko",
                                     .Scores = New Integer() {98, 92, 81, 60}}
        Dim student2 As New Student With {.FirstName = "Claire",
                                    .LastName = "O'Donnell",
                                    .Scores = New Integer() {75, 84, 91, 39}}
        Dim student3 As New Student With {.FirstName = "Cesar",
                                    .LastName = "Garcia",
                                    .Scores = New Integer() {97, 89, 85, 82}}
        Dim student4 As New Student With {.FirstName = "Sven",
                                    .LastName = "Mortensen",
                                    .Scores = New Integer() {88, 94, 65, 91}}

        Dim arrList As New ArrayList()
        arrList.Add(student1)
        arrList.Add(student2)
        arrList.Add(student3)
        arrList.Add(student4)

        ' Use an explicit type for non-generic collections
        Dim query = From student As Student In arrList
                    Where student.Scores(0) > 95
                    Select student

        For Each student As Student In query
            Console.WriteLine(student.LastName & ": " & student.Scores(0))
        Next
        ' Keep the console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()
    End Sub

End Module
' Output:
'   Omelchenko: 98
'   Garcia: 97
```

## <a name="see-also"></a><span data-ttu-id="70540-115">참조</span><span class="sxs-lookup"><span data-stu-id="70540-115">See also</span></span>

- [<span data-ttu-id="70540-116">LINQ to Objects(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70540-116">LINQ to Objects (Visual Basic)</span></span>](linq-to-objects.md)
