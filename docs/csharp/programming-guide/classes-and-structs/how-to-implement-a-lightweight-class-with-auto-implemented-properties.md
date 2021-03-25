---
title: 자동으로 구현된 속성을 사용하여 간단한 클래스를 구현하는 방법 - C# 프로그래밍 가이드
description: C#에서 자동으로 구현된 속성을 캡슐화하는 변경할 수 없는 간단한 클래스를 만드는 방법에 대해 알아봅니다. 구현 방법에는 두 가지가 있습니다.
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 1dc5a8ad-a4f7-4f32-8506-3fc6d8c8bfed
ms.openlocfilehash: 1d80cb2391a94c21360117c8217ecc4514fd666e
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190270"
---
# <a name="how-to-implement-a-lightweight-class-with-auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="c8967-104">자동으로 구현된 속성을 사용하여 간단한 클래스를 구현하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="c8967-104">How to implement a lightweight class with auto-implemented properties (C# Programming Guide)</span></span>

<span data-ttu-id="c8967-105">이 예제에서는 자동 구현 속성 집합을 캡슐화하는 데만 사용되는 변경할 수 없는 간단한 클래스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-105">This example shows how to create an immutable lightweight class that serves only to encapsulate a set of auto-implemented properties.</span></span> <span data-ttu-id="c8967-106">참조 형식 의미 체계를 사용해야 하는 경우 구조체 대신 이러한 종류의 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-106">Use this kind of construct instead of a struct when you must use reference type semantics.</span></span>

<span data-ttu-id="c8967-107">다음과 같은 방법으로 변경할 수 없는 속성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-107">You can make an immutable property in the following ways:</span></span>

- <span data-ttu-id="c8967-108">[get](../../language-reference/keywords/get.md) 접근자만 선언하여 형식의 생성자를 제외한 어떤 위치에서도 속성을 변경할 수 없도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-108">Declare only the [get](../../language-reference/keywords/get.md) accessor, which makes the property immutable everywhere except in the type's constructor.</span></span>

- <span data-ttu-id="c8967-109">`set` 접근자 대신 [init](../../language-reference/keywords/init.md) 접근자를 선언합니다. 이렇게 하면 생성자에서만 또는 [개체 이니셜라이저](object-and-collection-initializers.md)를 사용하여 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-109">Declare an [init](../../language-reference/keywords/init.md) accessor instead of a `set` accessor, which makes the property settable only in the constructor or by using an [object initializer](object-and-collection-initializers.md).</span></span>

- <span data-ttu-id="c8967-110">[set](../../language-reference/keywords/set.md) 접근자를 [프라이빗](../../language-reference/keywords/private.md)으로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-110">Declare the [set](../../language-reference/keywords/set.md) accessor to be [private](../../language-reference/keywords/private.md).</span></span>  <span data-ttu-id="c8967-111">속성은 형식 내에서 설정할 수 있지만 소비자는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-111">The property is settable within the type, but it is immutable to consumers.</span></span>

  <span data-ttu-id="c8967-112">private `set` 접근자를 선언하는 경우 개체 이니셜라이저를 사용하여 속성을 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-112">When you declare a private `set` accessor, you cannot use an object initializer to initialize the property.</span></span> <span data-ttu-id="c8967-113">생성자나 팩터리 메서드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-113">You must use a constructor or a factory method.</span></span>

<span data-ttu-id="c8967-114">다음 예제는 get 접근자만 있는 속성이 get 및 private 집합이 있는 속성과 어떻게 다른지 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-114">The following example shows how a property with only get accessor differs than one with get and private set.</span></span>

```csharp
class Contact
{
    public string Name { get; }
    public string Address { get; private set; }

    public Contact(string contactName, string contactAddress)
    {
        // Both properties are accessible in the constructor.
        Name = contactName;
        Address = contactAddress;
    }

    // Name isn't assignable here. This will generate a compile error.
    //public void ChangeName(string newName) => Name = newName;

    // Address is assignable here.
    public void ChangeAddress(string newAddress) => Address = newAddress
}
```

## <a name="example"></a><span data-ttu-id="c8967-115">예제</span><span class="sxs-lookup"><span data-stu-id="c8967-115">Example</span></span>

<span data-ttu-id="c8967-116">다음 예제에서는 자동 구현 속성을 갖는 변경할 수 없는 클래스를 구현하는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-116">The following example shows two ways to implement an immutable class that has auto-implemented properties.</span></span> <span data-ttu-id="c8967-117">각 방법에서 속성 중 하나는 private `set`으로 선언하고 다른 하나는 `get`으로만 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-117">Each way declares one of the properties with a private `set` and one of the properties with a `get` only.</span></span>  <span data-ttu-id="c8967-118">첫 번째 클래스는 생성자만 사용하여 속성을 초기화하고 두 번째 클래스는 생성자를 호출하는 정적 팩터리 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-118">The first class uses a constructor only to initialize the properties, and the second class uses a static factory method that calls a constructor.</span></span>

```csharp
// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// constructor to initialize its properties.
class Contact
{
    // Read-only property.
    public string Name { get; }

    // Read-write property with a private set accessor.
    public string Address { get; private set; }

    // Public constructor.
    public Contact(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }
}

// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// static method and private constructor to initialize its properties.
public class Contact2
{
    // Read-write property with a private set accessor.
    public string Name { get; private set; }

    // Read-only property.
    public string Address { get; }

    // Private constructor.
    private Contact2(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }

    // Public factory method.
    public static Contact2 CreateContact(string name, string address)
    {
        return new Contact2(name, address);
    }
}

public class Program
{
    static void Main()
    {
        // Some simple data sources.
        string[] names = {"Terry Adams","Fadi Fakhouri", "Hanying Feng",
                            "Cesar Garcia", "Debra Garcia"};
        string[] addresses = {"123 Main St.", "345 Cypress Ave.", "678 1st Ave",
                                "12 108th St.", "89 E. 42nd St."};

        // Simple query to demonstrate object creation in select clause.
        // Create Contact objects by using a constructor.
        var query1 = from i in Enumerable.Range(0, 5)
                    select new Contact(names[i], addresses[i]);

        // List elements cannot be modified by client code.
        var list = query1.ToList();
        foreach (var contact in list)
        {
            Console.WriteLine("{0}, {1}", contact.Name, contact.Address);
        }

        // Create Contact2 objects by using a static factory method.
        var query2 = from i in Enumerable.Range(0, 5)
                        select Contact2.CreateContact(names[i], addresses[i]);

        // Console output is identical to query1.
        var list2 = query2.ToList();

        // List elements cannot be modified by client code.
        // CS0272:
        // list2[0].Name = "Eugene Zabokritski";

        // Keep the console open in debug mode.
        Console.WriteLine("Press any key to exit.");
        Console.ReadKey();
    }
}

/* Output:
    Terry Adams, 123 Main St.
    Fadi Fakhouri, 345 Cypress Ave.
    Hanying Feng, 678 1st Ave
    Cesar Garcia, 12 108th St.
    Debra Garcia, 89 E. 42nd St.
*/
```

<span data-ttu-id="c8967-119">컴파일러는 각 자동 구현 속성에 대해 지원 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-119">The compiler creates backing fields for each auto-implemented property.</span></span> <span data-ttu-id="c8967-120">이 필드는 소스 코드에서 직접 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8967-120">The fields are not accessible directly from source code.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8967-121">참조</span><span class="sxs-lookup"><span data-stu-id="c8967-121">See also</span></span>

- [<span data-ttu-id="c8967-122">속성</span><span class="sxs-lookup"><span data-stu-id="c8967-122">Properties</span></span>](./properties.md)
- [<span data-ttu-id="c8967-123">struct</span><span class="sxs-lookup"><span data-stu-id="c8967-123">struct</span></span>](../../language-reference/builtin-types/struct.md)
- [<span data-ttu-id="c8967-124">개체 이니셜라이저 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="c8967-124">Object and Collection Initializers</span></span>](./object-and-collection-initializers.md)
