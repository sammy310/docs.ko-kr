---
title: 예외 및 성능
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: afa4e748599781a5979823320d8913ff5357d415
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741650"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="ea49a-102">예외 및 성능</span><span class="sxs-lookup"><span data-stu-id="ea49a-102">Exceptions and Performance</span></span>
<span data-ttu-id="ea49a-103">예외와 관련 된 일반적인 문제 중 하나는 정기적으로 실패 하는 코드에 예외가 사용 되는 경우 구현의 성능이 허용 되지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="ea49a-104">이는 유효한 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-104">This is a valid concern.</span></span> <span data-ttu-id="ea49a-105">멤버가 예외를 throw 하는 경우 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="ea49a-106">그러나 오류 코드를 사용할 수 없도록 하는 예외 지침을 엄격 하 게 준수 하는 동시에 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="ea49a-107">이 섹션에서 설명 하는 두 가지 패턴은이 작업을 수행 하는 방법을 제안 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-107">Two patterns described in this section suggest ways to do this.</span></span>

 <span data-ttu-id="ea49a-108">예외는 성능에 부정적인 영향을 줄 수 있으므로 오류 코드를 사용 하지 ❌.</span><span class="sxs-lookup"><span data-stu-id="ea49a-108">❌ DO NOT use error codes because of concerns that exceptions might affect performance negatively.</span></span>

 <span data-ttu-id="ea49a-109">성능을 향상 시키려면 다음 두 섹션에서 설명 하는 Doer 패턴 또는 Try-catch 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>

## <a name="tester-doer-pattern"></a><span data-ttu-id="ea49a-110">Doer 패턴</span><span class="sxs-lookup"><span data-stu-id="ea49a-110">Tester-Doer Pattern</span></span>
 <span data-ttu-id="ea49a-111">경우에 따라 멤버를 두 개로 분리 하 여 예외 throw 멤버의 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="ea49a-112"><xref:System.Collections.Generic.ICollection%601> 인터페이스의 <xref:System.Collections.Generic.ICollection%601.Add%2A> 메서드를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 <span data-ttu-id="ea49a-113">컬렉션이 읽기 전용인 경우 throw 되는 메서드 `Add`입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="ea49a-114">이는 메서드 호출이 자주 실패할 것으로 예상 되는 시나리오에서 성능 문제를 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="ea49a-115">문제를 완화 하는 방법 중 하나는 값을 추가 하기 전에 컬렉션을 쓸 수 있는지 여부를 테스트 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 <span data-ttu-id="ea49a-116">조건을 테스트 하는 데 사용 되는 멤버입니다 .이 예제에서 `IsReadOnly`속성은 테스터 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="ea49a-117">잠재적으로 throw 되는 작업을 수행 하는 데 사용 되는 멤버입니다 .이 예제에서 `Add` 메서드를 doer 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>

 <span data-ttu-id="ea49a-118">예외와 관련 된 성능 문제를 방지 하기 위해 일반적인 시나리오에서 예외를 throw 할 수 있는 멤버의 Doer 패턴을 고려 합니다. ✔️</span><span class="sxs-lookup"><span data-stu-id="ea49a-118">✔️ CONSIDER the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

## <a name="try-parse-pattern"></a><span data-ttu-id="ea49a-119">Try-Parse 패턴</span><span class="sxs-lookup"><span data-stu-id="ea49a-119">Try-Parse Pattern</span></span>
 <span data-ttu-id="ea49a-120">매우 성능에 민감한 Api의 경우 이전 섹션에서 설명한 Doer 패턴 보다 훨씬 더 빠른 패턴을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="ea49a-121">패턴은 멤버 이름을 조정 하 여 잘 정의 된 테스트 사례를 멤버 의미 체계의 일부로 만드는 작업을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="ea49a-122">예를 들어 <xref:System.DateTime>는 문자열의 구문 분석이 실패 하는 경우 예외를 throw 하는 <xref:System.DateTime.Parse%2A> 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="ea49a-123">또한 구문 분석을 시도 하는 해당 <xref:System.DateTime.TryParse%2A> 메서드를 정의 하지만 구문 분석이 실패 하 고 `out` 매개 변수를 사용 하 여 성공적으로 구문 분석 한 결과를 반환 하는 경우에는 false를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>

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

 <span data-ttu-id="ea49a-124">이 패턴을 사용 하는 경우에는 엄격한 용어로 try 기능을 정의 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="ea49a-125">잘 정의 된 시도 이외의 이유로 멤버가 실패 하면 해당 멤버는 여전히 해당 예외를 throw 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>

 <span data-ttu-id="ea49a-126">예외와 관련 된 성능 문제를 방지 하기 위해 일반적인 시나리오에서 예외를 throw 할 수 있는 멤버의 시도 구문 분석 패턴을 고려 ✔️.</span><span class="sxs-lookup"><span data-stu-id="ea49a-126">✔️ CONSIDER the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

 <span data-ttu-id="ea49a-127">이 패턴을 구현 하는 메서드에 대해 접두사 "Try" 및 부울 반환 형식을 사용 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-127">✔️ DO use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>

 <span data-ttu-id="ea49a-128">✔️는 Try-catch 패턴을 사용 하 여 각 멤버에 대 한 예외 throw 멤버를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea49a-128">✔️ DO provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>

 <span data-ttu-id="ea49a-129">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="ea49a-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="ea49a-130">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="ea49a-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="ea49a-131">참조</span><span class="sxs-lookup"><span data-stu-id="ea49a-131">See also</span></span>

- [<span data-ttu-id="ea49a-132">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ea49a-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="ea49a-133">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ea49a-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
