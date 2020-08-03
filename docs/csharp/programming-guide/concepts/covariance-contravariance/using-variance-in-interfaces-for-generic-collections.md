---
title: 제네릭 컬렉션용 인터페이스의 가변성 사용(C#)
description: 제네릭 컬렉션용 공변(covariant) 및 반공변(contravariant) 인터페이스를 사용하는 방법에 대해 알아봅니다. 제네릭 컬렉션을 변환하고 비교하는 예제를 참조하세요.
ms.date: 07/20/2015
ms.assetid: a44f0708-10fa-4c76-82cd-daa6e6b31e8e
ms.openlocfilehash: c2ce849e32520cb91422ff36173e418a010476bd
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105673"
---
# <a name="using-variance-in-interfaces-for-generic-collections-c"></a><span data-ttu-id="f3873-104">제네릭 컬렉션용 인터페이스의 가변성 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="f3873-104">Using Variance in Interfaces for Generic Collections (C#)</span></span>
<span data-ttu-id="f3873-105">공변(covariant) 인터페이스는 메서드가 인터페이스에 지정된 것보다 더 많은 수의 파생된 형식을 반환하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f3873-105">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="f3873-106">반공변(contravariant) 인터페이스는 메서드가 인터페이스에 지정된 것보다 더 적은 파생된 형식의 매개 변수를 수락하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f3873-106">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>  
  
 <span data-ttu-id="f3873-107">.NET Framework 4에서는 몇 가지 기존 인터페이스가 공변(covariant) 및 반공변(contravariant)이 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f3873-107">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="f3873-108">여기에는 <xref:System.Collections.Generic.IEnumerable%601> 및 <xref:System.IComparable%601>이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3873-108">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="f3873-109">따라서 파생된 형식의 컬렉션에 대한 기본 형식의 제네릭 컬렉션과 함께 작동하는 메서드를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3873-109">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>  
  
 <span data-ttu-id="f3873-110">.NET의 variant 인터페이스 목록은 [제네릭 인터페이스의 가변성(C#)](./variance-in-generic-interfaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3873-110">For a list of variant interfaces in .NET, see [Variance in Generic Interfaces (C#)](./variance-in-generic-interfaces.md).</span></span>  
  
## <a name="converting-generic-collections"></a><span data-ttu-id="f3873-111">제네릭 컬렉션 변환</span><span class="sxs-lookup"><span data-stu-id="f3873-111">Converting Generic Collections</span></span>  
 <span data-ttu-id="f3873-112">다음 예제에서는 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스에서 공변성(Covariance) 지원의 이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3873-112">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="f3873-113">`PrintFullName` 메서드는 `IEnumerable<Person>` 형식의 컬렉션을 매개 변수로 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="f3873-113">The `PrintFullName` method accepts a collection of the `IEnumerable<Person>` type as a parameter.</span></span> <span data-ttu-id="f3873-114">그러나 `Employee`는 `Person`을 상속하므로 `IEnumerable<Employee>` 형식의 컬렉션에 대해 이를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3873-114">However, you can reuse it for a collection of the `IEnumerable<Employee>` type because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
class Program  
{  
    // The method has a parameter of the IEnumerable<Person> type.  
    public static void PrintFullName(IEnumerable<Person> persons)  
    {  
        foreach (Person person in persons)  
        {  
            Console.WriteLine("Name: {0} {1}",  
            person.FirstName, person.LastName);  
        }  
    }  
  
    public static void Test()  
    {  
        IEnumerable<Employee> employees = new List<Employee>();  
  
        // You can pass IEnumerable<Employee>,
        // although the method expects IEnumerable<Person>.  
  
        PrintFullName(employees);  
  
    }  
}  
```  
  
## <a name="comparing-generic-collections"></a><span data-ttu-id="f3873-115">제네릭 컬렉션 비교</span><span class="sxs-lookup"><span data-stu-id="f3873-115">Comparing Generic Collections</span></span>  
 <span data-ttu-id="f3873-116">다음 예제에서는 <xref:System.Collections.Generic.IComparer%601> 인터페이스에서 반공변성(Contravariance) 지원의 이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3873-116">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="f3873-117">`PersonComparer` 클래스가 `IComparer<Person>` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f3873-117">The `PersonComparer` class implements the `IComparer<Person>` interface.</span></span> <span data-ttu-id="f3873-118">그러나 `Employee`는 `Person`을 상속하므로 `Employee` 형식 개체의 시퀀스를 비교하기 위해 이 클래스를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3873-118">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
// The custom comparer for the Person type  
// with standard implementations of Equals()  
// and GetHashCode() methods.  
class PersonComparer : IEqualityComparer<Person>  
{  
    public bool Equals(Person x, Person y)  
    {
        if (Object.ReferenceEquals(x, y)) return true;  
        if (Object.ReferenceEquals(x, null) ||  
            Object.ReferenceEquals(y, null))  
            return false;
        return x.FirstName == y.FirstName && x.LastName == y.LastName;  
    }  
    public int GetHashCode(Person person)  
    {  
        if (Object.ReferenceEquals(person, null)) return 0;  
        int hashFirstName = person.FirstName == null  
            ? 0 : person.FirstName.GetHashCode();  
        int hashLastName = person.LastName.GetHashCode();  
        return hashFirstName ^ hashLastName;  
    }  
}  
  
class Program  
{  
  
    public static void Test()  
    {  
        List<Employee> employees = new List<Employee> {  
               new Employee() {FirstName = "Michael", LastName = "Alexander"},  
               new Employee() {FirstName = "Jeff", LastName = "Price"}  
            };  
  
        // You can pass PersonComparer,
        // which implements IEqualityComparer<Person>,  
        // although the method expects IEqualityComparer<Employee>.  
  
        IEnumerable<Employee> noduplicates =  
            employees.Distinct<Employee>(new PersonComparer());  
  
        foreach (var employee in noduplicates)  
            Console.WriteLine(employee.FirstName + " " + employee.LastName);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3873-119">참조</span><span class="sxs-lookup"><span data-stu-id="f3873-119">See also</span></span>

- [<span data-ttu-id="f3873-120">제네릭 인터페이스의 가변성(C#)</span><span class="sxs-lookup"><span data-stu-id="f3873-120">Variance in Generic Interfaces (C#)</span></span>](./variance-in-generic-interfaces.md)
