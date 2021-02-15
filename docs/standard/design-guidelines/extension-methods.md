---
description: '자세한 정보: 확장명 메서드'
title: 확장 메서드
ms.date: 10/22/2008
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
ms.openlocfilehash: 2f71ec86252045687558bd61337164ac3afbcd20
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642060"
---
# <a name="extension-methods"></a><span data-ttu-id="9ae35-103">확장 메서드</span><span class="sxs-lookup"><span data-stu-id="9ae35-103">Extension Methods</span></span>

<span data-ttu-id="9ae35-104">확장 메서드는 인스턴스 메서드 호출 구문을 사용하여 정적 메서드를 호출할 수 있는 언어 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-104">Extension methods are a language feature that allows static methods to be called using instance method call syntax.</span></span> <span data-ttu-id="9ae35-105">이러한 메서드는 메서드가 작동해야 하는 인스턴스를 나타내는 매개 변수를 하나 이상 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-105">These methods must take at least one parameter, which represents the instance the method is to operate on.</span></span>

 <span data-ttu-id="9ae35-106">이러한 확장 메서드를 정의하는 클래스를 “스폰서” 클래스라고 하며 이 클래스는 정적으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-106">The class that defines such extension methods is referred to as the "sponsor" class, and it must be declared as static.</span></span> <span data-ttu-id="9ae35-107">확장 메서드를 사용하려면 스폰서 클래스를 정의하는 네임스페이스를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-107">To use extension methods, one must import the namespace defining the sponsor class.</span></span>

 <span data-ttu-id="9ae35-108">❌ 확장 메서드, 특히 소유하지 않는 형식을 경솔하게 정의하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-108">❌ AVOID frivolously defining extension methods, especially on types you don't own.</span></span>

 <span data-ttu-id="9ae35-109">형식의 소스 코드를 소유하는 경우 일반적인 인스턴스 메서드를 대신 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-109">If you do own source code of a type, consider using regular instance methods instead.</span></span> <span data-ttu-id="9ae35-110">소유하지 않는 경우 메서드를 추가하려면 매우 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-110">If you don't own, and you want to add a method, be very careful.</span></span> <span data-ttu-id="9ae35-111">확장 메서드를 자유롭게 사용하면 이러한 메서드를 사용하도록 설계되지 않은 형식의 API가 복잡해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-111">Liberal use of extension methods has the potential of cluttering APIs of types that were not designed to have these methods.</span></span>

 <span data-ttu-id="9ae35-112">✔️ 다음과 같은 시나리오에서는 확장 메서드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-112">✔️ CONSIDER using extension methods in any of the following scenarios:</span></span>

- <span data-ttu-id="9ae35-113">모든 인터페이스 구현과 관련된 도우미 기능을 제공하려는 경우 핵심 인터페이스 측면에서 기능을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-113">To provide helper functionality relevant to every implementation of an interface, if said functionality can be written in terms of the core interface.</span></span> <span data-ttu-id="9ae35-114">다른 방법으로는 구체적 구현을 인터페이스에 할당할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-114">This is because concrete implementations cannot otherwise be assigned to interfaces.</span></span> <span data-ttu-id="9ae35-115">예를 들어 `LINQ to Objects` 연산자는 모든 <xref:System.Collections.Generic.IEnumerable%601> 형식에 대해 확장 메서드로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-115">For example, the `LINQ to Objects` operators are implemented as extension methods for all <xref:System.Collections.Generic.IEnumerable%601> types.</span></span> <span data-ttu-id="9ae35-116">따라서 `IEnumerable<>` 구현은 자동으로 LINQ를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-116">Thus, any `IEnumerable<>` implementation is automatically LINQ-enabled.</span></span>

- <span data-ttu-id="9ae35-117">인스턴스 메서드가 일부 형식에 대해 종속성을 도입하는데 이러한 종속성이 종속성 관리 규칙을 위반하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-117">When an instance method would introduce a dependency on some type, but such a dependency would break dependency management rules.</span></span> <span data-ttu-id="9ae35-118">예를 들어 <xref:System.Uri?displayProperty=nameWithType>에 대한 <xref:System.String>의 종속성은 바람직하지 않을 수 있으므로 `System.Uri`를 반환하는 `String.ToUri()` 인스턴스 메서드는 종속성 관리 관점에서 잘못된 디자인이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-118">For example, a dependency from <xref:System.String> to <xref:System.Uri?displayProperty=nameWithType> is probably not desirable, and so `String.ToUri()` instance method returning `System.Uri` would be the wrong design from a dependency management perspective.</span></span> <span data-ttu-id="9ae35-119">`System.Uri`를 반환하는 정적 확장 메서드 `Uri.ToUri(this string str)`가 훨씬 더 나은 디자인입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-119">A static extension method `Uri.ToUri(this string str)` returning `System.Uri` would be a much better design.</span></span>

 <span data-ttu-id="9ae35-120">❌ <xref:System.Object?displayProperty=nameWithType>에서 확장 메서드를 정의하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-120">❌ AVOID defining extension methods on <xref:System.Object?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="9ae35-121">VB 사용자는 확장 메서드 구문을 사용하여 개체 참조에서 이러한 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-121">VB users will not be able to call such methods on object references using the extension method syntax.</span></span> <span data-ttu-id="9ae35-122">VB에서 참조를 개체로 선언하면 모든 메서드 호출이 런타임에 바인딩(호출된 실제 멤버가 런타임에 결정)되고 확장 메서드에 대한 바인딩은 컴파일 시간에 결정(초기 바인딩)되므로 VB는 이러한 메서드 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-122">VB does not support calling such methods because, in VB, declaring a reference as Object forces all method invocations on it to be late bound (actual member called is determined at runtime), while bindings to extension methods are determined at compile-time (early bound).</span></span>

 <span data-ttu-id="9ae35-123">이 지침은 동일한 바인딩 동작이 있거나 확장 메서드가 지원되지 않는 다른 언어에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-123">Note that the guideline applies to other languages where the same binding behavior is present, or where extension methods are not supported.</span></span>

 <span data-ttu-id="9ae35-124">❌ 인터페이스에 메서드를 추가하거나 종속성 관리를 위한 경우가 아니라면 확장 형식과 동일한 네임스페이스에 확장 메서드를 넣지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9ae35-124">❌ DO NOT put extension methods in the same namespace as the extended type unless it is for adding methods to interfaces or for dependency management.</span></span>

 <span data-ttu-id="9ae35-125">❌ 서로 다른 네임스페이스에 있는 경우에도 동일한 시그니처로 둘 이상의 확장 메서드를 정의하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-125">❌ AVOID defining two or more extension methods with the same signature, even if they reside in different namespaces.</span></span>

 <span data-ttu-id="9ae35-126">✔️ 형식이 인터페이스인 경우와 확장 메서드를 대부분의 경우나 모든 경우에 사용하려는 경우 확장 형식과 동일한 네임스페이스에서 확장 메서드를 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-126">✔️ CONSIDER defining extension methods in the same namespace as the extended type if the type is an interface and if the extension methods are meant to be used in most or all cases.</span></span>

 <span data-ttu-id="9ae35-127">❌ 일반적으로 다른 기능과 연결된 네임스페이스에서는 기능을 구현하는 확장 메서드를 정의하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9ae35-127">❌ DO NOT define extension methods implementing a feature in namespaces normally associated with other features.</span></span> <span data-ttu-id="9ae35-128">대신 확장 메서드가 속한 기능과 연결된 네임스페이스에서 정의하세요.</span><span class="sxs-lookup"><span data-stu-id="9ae35-128">Instead, define them in the namespace associated with the feature they belong to.</span></span>

 <span data-ttu-id="9ae35-129">❌ 확장 메서드 전용 네임스페이스의 일반 이름(예: “확장”)을 지정하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ae35-129">❌ AVOID generic naming of namespaces dedicated to extension methods (e.g., "Extensions").</span></span> <span data-ttu-id="9ae35-130">대신 설명이 포함된 이름(예: “라우팅”)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9ae35-130">Use a descriptive name (e.g., "Routing") instead.</span></span>

 <span data-ttu-id="9ae35-131">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="9ae35-131">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="9ae35-132">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="9ae35-132">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="9ae35-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ae35-133">See also</span></span>

- [<span data-ttu-id="9ae35-134">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="9ae35-134">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="9ae35-135">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="9ae35-135">Framework Design Guidelines</span></span>](index.md)
