---
title: 확장명 메서드
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: KrzysztofCwalina
ms.openlocfilehash: bd5f67c3bd766625e7c22b3ca9986cfbca8854bf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026421"
---
# <a name="extension-methods"></a><span data-ttu-id="27bdd-102">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="27bdd-102">Extension Methods</span></span>
<span data-ttu-id="27bdd-103">확장 메서드는 정적 메서드를 인스턴스 메서드 호출 구문을 사용 하 여 호출할 수 있도록 언어 기능.</span><span class="sxs-lookup"><span data-stu-id="27bdd-103">Extension methods are a language feature that allows static methods to be called using instance method call syntax.</span></span> <span data-ttu-id="27bdd-104">이러한 메서드는 메서드를의 동작에 인스턴스를 나타내는 하나 이상의 매개 변수를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-104">These methods must take at least one parameter, which represents the instance the method is to operate on.</span></span>  
  
 <span data-ttu-id="27bdd-105">이러한 확장 메서드를 정의 하는 클래스를 "스폰서" 클래스 라고 하 고 정적으로 선언 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-105">The class that defines such extension methods is referred to as the "sponsor" class, and it must be declared as static.</span></span> <span data-ttu-id="27bdd-106">확장 메서드를 사용 하려면 하나 스폰서 클래스를 정의 하는 네임 스페이스를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-106">To use extension methods, one must import the namespace defining the sponsor class.</span></span>  
  
 <span data-ttu-id="27bdd-107">**X AVOID** frivolously 소유 하지 않은 형식에서 특히 확장 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-107">**X AVOID** frivolously defining extension methods, especially on types you don’t own.</span></span>  
  
 <span data-ttu-id="27bdd-108">형식의 소스 코드를 소유 않은 경우에 일반 인스턴스 메서드를 대신 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-108">If you do own source code of a type, consider using regular instance methods instead.</span></span> <span data-ttu-id="27bdd-109">소유 하지 않습니다 하 고 메서드를 추가 하려는 경우 매우 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-109">If you don’t own, and you want to add a method, be very careful.</span></span> <span data-ttu-id="27bdd-110">확장 메서드의 자유롭게 사용 하 여 이러한 메서드를 하도록 설계 되지 않았습니다 하는 형식의 Api 어지럽히지의 잠재력을 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-110">Liberal use of extension methods has the potential of cluttering APIs of types that were not designed to have these methods.</span></span>  
  
 <span data-ttu-id="27bdd-111">**✓ CONSIDER** 확장 메서드를 사용 하 여 다음과 같은 시나리오 중 하나:</span><span class="sxs-lookup"><span data-stu-id="27bdd-111">**✓ CONSIDER** using extension methods in any of the following scenarios:</span></span>  
  
- <span data-ttu-id="27bdd-112">도우미를 제공 하는 핵심 인터페이스 측면에서 기능을 언급 하는 경우 인터페이스의 모든 구현 관련 기능을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-112">To provide helper functionality relevant to every implementation of an interface, if said functionality can be written in terms of the core interface.</span></span> <span data-ttu-id="27bdd-113">구체적인 구현은 인터페이스가 고, 그렇지 할당할 수 없습니다 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-113">This is because concrete implementations cannot otherwise be assigned to interfaces.</span></span> <span data-ttu-id="27bdd-114">예를 들어 합니다 `LINQ to Objects` 연산자는 모두에 대 한 확장 메서드로 구현 됩니다 <xref:System.Collections.Generic.IEnumerable%601> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-114">For example, the `LINQ to Objects` operators are implemented as extension methods for all <xref:System.Collections.Generic.IEnumerable%601> types.</span></span> <span data-ttu-id="27bdd-115">따라서 모든 `IEnumerable<>` 구현에서 자동으로 LINQ를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-115">Thus, any `IEnumerable<>` implementation is automatically LINQ-enabled.</span></span>  
  
- <span data-ttu-id="27bdd-116">일부 형식에 종속 되지만 이러한 종속성 인스턴스 메서드는 제공 하는 경우 종속성 관리 규칙 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-116">When an instance method would introduce a dependency on some type, but such a dependency would break dependency management rules.</span></span> <span data-ttu-id="27bdd-117">예를 들어, 종속 <xref:System.String> 를 <xref:System.Uri?displayProperty=nameWithType> 바람직하지 않을 것 등 `String.ToUri()` 반환 되는 인스턴스 메서드 `System.Uri` 종속성 관리 측면에서 잘못 된 디자인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-117">For example, a dependency from <xref:System.String> to <xref:System.Uri?displayProperty=nameWithType> is probably not desirable, and so `String.ToUri()` instance method returning `System.Uri` would be the wrong design from a dependency management perspective.</span></span> <span data-ttu-id="27bdd-118">정적 확장 메서드 `Uri.ToUri(this string str)` 반환 `System.Uri` 훨씬 더 나은 디자인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-118">A static extension method `Uri.ToUri(this string str)` returning `System.Uri` would be a much better design.</span></span>  
  
 <span data-ttu-id="27bdd-119">**X AVOID** 에서 확장 메서드를 정의 <xref:System.Object?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-119">**X AVOID** defining extension methods on <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="27bdd-120">VB 사용자 확장 메서드 구문을 사용 하 여 개체 참조에서 이러한 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-120">VB users will not be able to call such methods on object references using the extension method syntax.</span></span> <span data-ttu-id="27bdd-121">VB vb의 경우 바인딩된 개체를 가져오면 되도록 런타임에 대 한 모든 메서드 호출으로 대 한 참조를 선언 하기 때문에 이러한 메서드 호출을 지원 하지 않습니다 (실제 멤버는 런타임에 결정 됨), 확장 메서드 바인딩 컴파일 시간 (초기에 결정 되는 동안 바인딩된).</span><span class="sxs-lookup"><span data-stu-id="27bdd-121">VB does not support calling such methods because, in VB, declaring a reference as Object forces all method invocations on it to be late bound (actual member called is determined at runtime), while bindings to extension methods are determined at compile-time (early bound).</span></span>  
  
 <span data-ttu-id="27bdd-122">지침에 적용 됩니다. 동일한 바인딩 동작 있는지 다른 언어 또는 확장 메서드가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-122">Note that the guideline applies to other languages where the same binding behavior is present, or where extension methods are not supported.</span></span>  
  
 <span data-ttu-id="27bdd-123">**X DO NOT** 종속성 관리 또는 인터페이스에 메서드 추가 하지 않은 확장된 유형으로 동일한 네임 스페이스에 확장 메서드를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-123">**X DO NOT** put extension methods in the same namespace as the extended type unless it is for adding methods to interfaces or for dependency management.</span></span>  
  
 <span data-ttu-id="27bdd-124">**X AVOID** 다른 네임 스페이스에 상주 하는 경우에 동일한 서명으로 두 개 이상의 확장 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-124">**X AVOID** defining two or more extension methods with the same signature, even if they reside in different namespaces.</span></span>  
  
 <span data-ttu-id="27bdd-125">**✓ CONSIDER** 형식이 인터페이스 및 확장 메서드는 대부분 또는 모든 경우에 사용 하려는 경우 확장된 유형으로 동일한 네임 스페이스의 확장 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-125">**✓ CONSIDER** defining extension methods in the same namespace as the extended type if the type is an interface and if the extension methods are meant to be used in most or all cases.</span></span>  
  
 <span data-ttu-id="27bdd-126">**X DO NOT** 다른 기능과 함께 일반적으로 관련 된 네임 스페이스에는 기능을 구현 하는 확장 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-126">**X DO NOT** define extension methods implementing a feature in namespaces normally associated with other features.</span></span> <span data-ttu-id="27bdd-127">대신, 자신이 속한 기능과 관련 된 네임 스페이스에서 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-127">Instead, define them in the namespace associated with the feature they belong to.</span></span>  
  
 <span data-ttu-id="27bdd-128">**X AVOID** 확장 메서드 (예: "확장")에 네임 스페이스의 일반 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-128">**X AVOID** generic naming of namespaces dedicated to extension methods (e.g., "Extensions").</span></span> <span data-ttu-id="27bdd-129">설명이 포함 된 이름을 사용 하 여 (예를 들어, "라우팅") 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="27bdd-129">Use a descriptive name (e.g., "Routing") instead.</span></span>  
  
 <span data-ttu-id="27bdd-130">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="27bdd-130">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="27bdd-131">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="27bdd-131">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27bdd-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="27bdd-132">See also</span></span>

- [<span data-ttu-id="27bdd-133">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="27bdd-133">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="27bdd-134">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="27bdd-134">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
