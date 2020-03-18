---
title: 대리자 및 람다 식
description: 대리자가 특정 메서드 시그니처를 지정하며, 직접 호출하거나 다른 메서드에 전달한 다음 호출할 수 있는 형식을 정의하는 방법을 알아봅니다.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: 0abcc73e31eab89c422513acf778bc8bd092e788
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "75345549"
---
# <a name="delegates-and-lambdas"></a><span data-ttu-id="2ce4b-103">대리자 및 람다 식</span><span class="sxs-lookup"><span data-stu-id="2ce4b-103">Delegates and lambdas</span></span>

<span data-ttu-id="2ce4b-104">대리자는 특정 메서드 시그니처를 지정하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-104">Delegates define a type, which specify a particular method signature.</span></span> <span data-ttu-id="2ce4b-105">이 시그니처를 충족하는 메서드(정적 또는 인스턴스)를 해당 형식의 변수에 할당한 다음 직접 호출하거나(적절한 인수 사용) 다른 메서드에 인수로 전달한 다음 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-105">A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called.</span></span> <span data-ttu-id="2ce4b-106">다음 예제에서는 대리자 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-106">The following example demonstrates delegate use.</span></span>

```csharp
using System;
using System.Linq;

public class Program
{
    public delegate string Reverse(string s);

    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Reverse rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

* <span data-ttu-id="2ce4b-107">`public delegate string Reverse(string s);` 줄에서는 특정 시그니처의 대리자 형식(이 경우 문자열 매개 변수를 사용하고 문자열 매개 변수를 반환하는 메서드)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-107">The `public delegate string Reverse(string s);` line creates a delegate type of a certain signature, in this case a method that takes a string parameter and then returns a string parameter.</span></span>
* <span data-ttu-id="2ce4b-108">정의된 대리자 형식과 동일한 서명을 가진 `static string ReverseString(string s)` 메서드는 대리자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-108">The `static string ReverseString(string s)` method, which has the exact same signature as the defined delegate type, implements the delegate.</span></span>
* <span data-ttu-id="2ce4b-109">`Reverse rev = ReverseString;` 줄에서는 해당 대리자 형식의 변수에 메서드를 할당할 수 있는 것이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-109">The `Reverse rev = ReverseString;` line shows that you can assign a method to a variable of the corresponding delegate type.</span></span>
* <span data-ttu-id="2ce4b-110">`Console.WriteLine(rev("a string"));` 줄에서는 대리자 유형의 변수를 사용하여 대리자를 호출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-110">The `Console.WriteLine(rev("a string"));` line demonstrates how to use a variable of a delegate type to invoke the delegate.</span></span>

<span data-ttu-id="2ce4b-111">개발 프로세스를 간소화하기 위해 .NET에는 프로그래머가 새 형식을 만들 필요 없이 다시 사용할 수 있는 대리자 형식 집합이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-111">In order to streamline the development process, .NET includes a set of delegate types that programmers can reuse and not have to create new types.</span></span> <span data-ttu-id="2ce4b-112">`Func<>`, `Action<>` 및 `Predicate<>`이며, 새 대리자 형식을 정의할 필요 없이 .NET API의 여러 위치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-112">These are `Func<>`, `Action<>` and `Predicate<>`, and they can be used in various places throughout the .NET APIs without the need to define new delegate types.</span></span> <span data-ttu-id="2ce4b-113">물론, 세 가지 형식 간에는 대체로 의도된 사용 방법과 관계가 있는 몇 가지 차이점이 있으며 해당 시그니처에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-113">Of course, there are some differences between the three as you will see in their signatures which mostly have to do with the way they were meant to be used:</span></span>

* <span data-ttu-id="2ce4b-114">`Action<>`은 대리자의 인수를 사용하여 작업을 수행해야 할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-114">`Action<>` is used when there is a need to perform an action using the arguments of the delegate.</span></span>
* <span data-ttu-id="2ce4b-115">`Func<>`는 일반적으로 변환을 수행해야 할 때 사용됩니다. 즉, 대리자의 인수를 다른 결과로 변환해야 할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-115">`Func<>` is used usually when you have a transformation on hand, that is, you need to transform the arguments of the delegate into a different result.</span></span> <span data-ttu-id="2ce4b-116">대표적인 예로 프로젝션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-116">Projections are a prime example of this.</span></span>
* <span data-ttu-id="2ce4b-117">`Predicate<>`는 인수가 대리자의 조건을 충족하는지 확인해야 할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-117">`Predicate<>` is used when you need to determine if the argument satisfies the condition of the delegate.</span></span> <span data-ttu-id="2ce4b-118">`Func<T, bool>`로 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-118">It can also be written as a `Func<T, bool>`.</span></span>

<span data-ttu-id="2ce4b-119">이제 위의 예제를 가져와서 사용자 지정 형식 대신 `Func<>` 대리자를 사용하여 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-119">We can now take our example above and rewrite it using the `Func<>` delegate instead of a custom type.</span></span> <span data-ttu-id="2ce4b-120">프로그램은 동일하게 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-120">The program will continue running exactly the same.</span></span>

```csharp
using System;
using System.Linq;

public class Program
{
    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Func<string, string> rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

<span data-ttu-id="2ce4b-121">이 간단한 예제에서는 `Main` 메서드 외부에서 정의된 메서드를 사용하는 것이 불필요해 보입니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-121">For this simple example, having a method defined outside of the `Main` method seems a bit superfluous.</span></span> <span data-ttu-id="2ce4b-122">.NET Framework 2.0에서 **익명 대리자** 개념이 도입된 것은 이 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-122">It is because of this that .NET Framework 2.0 introduced the concept of **anonymous delegates**.</span></span> <span data-ttu-id="2ce4b-123">익명 대리자 지원을 사용하면 추가 형식이나 메서드를 지정할 필요 없이 “인라인” 대리자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-123">With their support you are able to create "inline" delegates without having to specify any additional type or method.</span></span> <span data-ttu-id="2ce4b-124">필요한 위치에 대리자 정의를 인라인으로 추가하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-124">You simply inline the definition of the delegate where you need it.</span></span>

<span data-ttu-id="2ce4b-125">예를 들어 이번에는 익명 대리자를 사용하여 짝수 목록만 필터링한 다음 콘솔에 출력하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-125">For an example, we are going to switch it up and use our anonymous delegate to filter out a list of only even numbers and then print them to the console.</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(
          delegate (int no)
          {
              return (no % 2 == 0);
          }
        );

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

<span data-ttu-id="2ce4b-126">보시는 것처럼 대리자 본문은 다른 모든 대리자와 마찬가지로 단순히 식 집합일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-126">As you can see, the body of the delegate is just a set of expressions, as any other delegate.</span></span> <span data-ttu-id="2ce4b-127">그러나 별도의 정의가 아니라 _메서드 호출에서_임시로<xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-127">But instead of it being a separate definition, we’ve introduced it _ad hoc_ in our call to the <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="2ce4b-128">그러나 이 방법의 경우에도 제거할 수 있는 많은 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-128">However, even with this approach, there is still much code that we can throw away.</span></span> <span data-ttu-id="2ce4b-129">이때 **람다 식**이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-129">This is where **lambda expressions** come into play.</span></span>

<span data-ttu-id="2ce4b-130">람다 식 또는 줄여서 “람다”는 처음에 C# 3.0에서 LINQ(Language-Integrated Query)의 핵심 구성 요소 중 하나로 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-130">Lambda expressions, or just "lambdas" for short, were introduced first in C# 3.0, as one of the core building blocks of Language Integrated Query (LINQ).</span></span> <span data-ttu-id="2ce4b-131">람다 식은 단지 대리자 사용에 더 편리한 구문일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-131">They are just a more convenient syntax for using delegates.</span></span> <span data-ttu-id="2ce4b-132">시그니처와 메서드 본문을 선언하지만 대리자에 할당되지 않은 경우 고유한 공식 ID가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-132">They declare a signature and a method body, but don’t have an formal identity of their own, unless they are assigned to a delegate.</span></span> <span data-ttu-id="2ce4b-133">대리자와 달리 이벤트 등록의 왼쪽 항으로 또는 다양한 LINQ 절과 메서드에서 직접 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-133">Unlike delegates, they can be directly assigned as the left-hand side of event registration or in various LINQ clauses and methods.</span></span>

<span data-ttu-id="2ce4b-134">람다 식은 대리자를 지정하는 또 다른 방법이므로 익명 대리자 대신 람다 식을 사용하도록 위의 샘플을 다시 작성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-134">Since a lambda expression is just another way of specifying a delegate, we should be able to rewrite the above sample to use a lambda expression instead of an anonymous delegate.</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(i => i % 2 == 0);

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

<span data-ttu-id="2ce4b-135">위의 예제에서 사용된 람다 식은 `i => i % 2 == 0`입니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-135">In the preceding example, the lambda expression used is `i => i % 2 == 0`.</span></span> <span data-ttu-id="2ce4b-136">대리자 사용에 **매우** 편리한 구문일 뿐이므로 이면에서 수행되는 동작은 익명 대리자의 경우와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-136">Again, it is just a **very** convenient syntax for using delegates, so what happens under the covers is similar to what happens with the anonymous delegate.</span></span>

<span data-ttu-id="2ce4b-137">다시 말해, 람다는 단순히 대리자이므로 다음 코드 조각과 같이 문제 없이 이벤트 처리기로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-137">Again, lambdas are just delegates, which means that they can be used as an event handler without any problems, as the following code snippet illustrates.</span></span>

```csharp
public MainWindow()
{
    InitializeComponent();

    Loaded += (o, e) =>
    {
        this.Title = "Loaded";
    };
}
```

<span data-ttu-id="2ce4b-138">이 컨텍스트의 `+=` 연산자는 [이벤트](../../docs/csharp/language-reference/keywords/event.md)를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-138">The `+=` operator in this context is used to subscribe to an [event](../../docs/csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="2ce4b-139">자세한 내용은 [이벤트를 구독 및 구독 취소하는 방법](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-139">For more information, see [How to subscribe to and unsubscribe from events](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="2ce4b-140">추가 정보 및 리소스</span><span class="sxs-lookup"><span data-stu-id="2ce4b-140">Further reading and resources</span></span>

* [<span data-ttu-id="2ce4b-141">대리자</span><span class="sxs-lookup"><span data-stu-id="2ce4b-141">Delegates</span></span>](../../docs/csharp/programming-guide/delegates/index.md)
* [<span data-ttu-id="2ce4b-142">익명 함수</span><span class="sxs-lookup"><span data-stu-id="2ce4b-142">Anonymous Functions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [<span data-ttu-id="2ce4b-143">람다 식</span><span class="sxs-lookup"><span data-stu-id="2ce4b-143">Lambda expressions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
