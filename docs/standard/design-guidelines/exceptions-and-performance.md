---
description: '자세한 정보: 예외 및 성능'
title: 예외 및 성능
ms.date: 10/22/2008
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: 72b35ccca5514e56dcc04fc0a07d1f9887c4a2f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642125"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="ff7c1-103">예외 및 성능</span><span class="sxs-lookup"><span data-stu-id="ff7c1-103">Exceptions and Performance</span></span>

<span data-ttu-id="ff7c1-104">예외와 관련된 한 가지 일반적인 문제는 정기적으로 실패하는 코드에 예외를 사용할 경우 구현 성능이 저하될 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-104">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="ff7c1-105">이는 유효한 우려입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-105">This is a valid concern.</span></span> <span data-ttu-id="ff7c1-106">멤버가 예외를 throw하는 경우 성능이 현저하게 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-106">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="ff7c1-107">그러나 오류 코드 사용을 허용하지 않는 예외 지침을 엄격하게 준수하면 성능을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-107">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="ff7c1-108">이 섹션에서 설명하는 두 가지 패턴은 이렇게 하는 방법을 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-108">Two patterns described in this section suggest ways to do this.</span></span>

 <span data-ttu-id="ff7c1-109">❌ 예외로 인해 성능이 저하될 수 있으므로 오류 코드를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-109">❌ DO NOT use error codes because of concerns that exceptions might affect performance negatively.</span></span>

 <span data-ttu-id="ff7c1-110">성능을 향상하려면 다음 두 섹션에서 설명하는 Tester-Doer 패턴이나 Try-Parse 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-110">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>

## <a name="tester-doer-pattern"></a><span data-ttu-id="ff7c1-111">Tester-Doer 패턴</span><span class="sxs-lookup"><span data-stu-id="ff7c1-111">Tester-Doer Pattern</span></span>

 <span data-ttu-id="ff7c1-112">경우에 따라 예외 throw 멤버의 성능은 멤버를 둘로 구분하여 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-112">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="ff7c1-113"><xref:System.Collections.Generic.ICollection%601> 인터페이스의 <xref:System.Collections.Generic.ICollection%601.Add%2A> 메서드를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-113">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 <span data-ttu-id="ff7c1-114">`Add` 메서드는 컬렉션이 읽기 전용인 경우에 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-114">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="ff7c1-115">따라서 메서드 호출이 자주 실패할 것으로 예상되는 시나리오에서는 성능 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-115">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="ff7c1-116">문제를 완화하는 방법 중 하나는 값을 추가하기 전에 컬렉션이 쓰기 가능한지를 테스트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-116">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 <span data-ttu-id="ff7c1-117">조건을 테스트하는 데 사용되는 멤버를 tester라고 하며, 이 예제에서는 `IsReadOnly` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-117">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="ff7c1-118">잠재적으로 throw되는 작업을 수행하는 데 사용되는 멤버를 doer라고 하며, 이 예제에서는 `Add` 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-118">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>

 <span data-ttu-id="ff7c1-119">✔️ 예외와 관련된 성능 문제를 방지하려면 일반적인 시나리오에서 예외를 throw할 수 있는 멤버에 Tester-Doer 패턴을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-119">✔️ CONSIDER the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

## <a name="try-parse-pattern"></a><span data-ttu-id="ff7c1-120">Try-Parse 패턴</span><span class="sxs-lookup"><span data-stu-id="ff7c1-120">Try-Parse Pattern</span></span>

 <span data-ttu-id="ff7c1-121">성능이 매우 중요한 API에서는 이전 섹션에서 설명한 Tester-Doer 패턴보다 훨씬 더 빠른 패턴을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-121">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="ff7c1-122">이 패턴은 멤버 이름 조정을 요청하여 잘 정의된 테스트 사례를 멤버 의미 체계의 일부로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-122">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="ff7c1-123">예를 들어 <xref:System.DateTime>은 문자열의 구문 분석이 실패할 경우 예외를 throw하는 <xref:System.DateTime.Parse%2A> 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-123">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="ff7c1-124">구문 분석을 시도하는 해당 <xref:System.DateTime.TryParse%2A> 메서드도 정의하지만 구문 분석이 실패할 경우 false를 반환하고 `out` 매개 변수를 사용하여 성공한 구문 분석의 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-124">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>

```csharp
public struct DateTime
{
    public static DateTime Parse(string dateTime)
    {
        ...
    }
    public static bool TryParse(string dateTime, out DateTime result)
    {
        ...
    }
}
```

 <span data-ttu-id="ff7c1-125">이 패턴을 사용할 때는 엄격한 조건으로 try 기능을 정의하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-125">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="ff7c1-126">잘 정의된 try 이외의 이유로 멤버가 실패할 경우 멤버는 해당 예외를 계속 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-126">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>

 <span data-ttu-id="ff7c1-127">✔️ 예외와 관련된 성능 문제를 방지하려면 일반적인 시나리오에서 예외를 throw할 수 있는 멤버에 Try-Parse 패턴을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-127">✔️ CONSIDER the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

 <span data-ttu-id="ff7c1-128">✔️ 이 패턴을 구현하는 메서드에 접두사 “Try” 및 부울 반환 형식을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-128">✔️ DO use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>

 <span data-ttu-id="ff7c1-129">✔ Try-Parse 패턴을 사용하는 각 멤버에 대해 예외 throw 멤버를 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="ff7c1-129">✔️ DO provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>

 <span data-ttu-id="ff7c1-130">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="ff7c1-130">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="ff7c1-131">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="ff7c1-131">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="ff7c1-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff7c1-132">See also</span></span>

- [<span data-ttu-id="ff7c1-133">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ff7c1-133">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="ff7c1-134">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ff7c1-134">Design Guidelines for Exceptions</span></span>](exceptions.md)
