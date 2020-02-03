---
title: 중첩 형식
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
ms.openlocfilehash: dd13116b13ac8e2d7a3af6ef014eb4f393909515
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743704"
---
# <a name="nested-types"></a><span data-ttu-id="5bbe7-102">중첩 형식</span><span class="sxs-lookup"><span data-stu-id="5bbe7-102">Nested Types</span></span>
<span data-ttu-id="5bbe7-103">중첩 형식은 바깥쪽 형식 이라고 하는 다른 형식의 범위 내에 정의 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-103">A nested type is a type defined within the scope of another type, which is called the enclosing type.</span></span> <span data-ttu-id="5bbe7-104">중첩 형식에는 바깥쪽 형식의 모든 멤버에 대 한 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-104">A nested type has access to all members of its enclosing type.</span></span> <span data-ttu-id="5bbe7-105">예를 들어 바깥쪽 형식에 정의 된 private 필드와 바깥쪽 형식의 모든 상위 항목에 정의 된 보호 된 필드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-105">For example, it has access to private fields defined in the enclosing type and to protected fields defined in all ascendants of the enclosing type.</span></span>

 <span data-ttu-id="5bbe7-106">일반적으로 중첩 형식은 자주 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-106">In general, nested types should be used sparingly.</span></span> <span data-ttu-id="5bbe7-107">여기에는 여러 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-107">There are several reasons for this.</span></span> <span data-ttu-id="5bbe7-108">일부 개발자는 이러한 개념을 완벽 하 게 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-108">Some developers are not fully familiar with the concept.</span></span> <span data-ttu-id="5bbe7-109">예를 들어 이러한 개발자는 중첩 형식의 변수를 선언 하는 구문에 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-109">These developers might, for example, have problems with the syntax of declaring variables of nested types.</span></span> <span data-ttu-id="5bbe7-110">중첩 형식은 바깥쪽 형식과 매우 긴밀 하 게 결합 되어 있으므로 범용 형식에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-110">Nested types are also very tightly coupled with their enclosing types, and as such are not suited to be general-purpose types.</span></span>

 <span data-ttu-id="5bbe7-111">중첩 형식은 바깥쪽 형식의 구현 세부 정보를 모델링 하는 데 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-111">Nested types are best suited for modeling implementation details of their enclosing types.</span></span> <span data-ttu-id="5bbe7-112">최종 사용자는 중첩 형식의 변수를 선언 하는 것은 거의 필요 하지 않으며 중첩 형식을 명시적으로 인스턴스화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-112">The end user should rarely have to declare variables of a nested type and almost never should have to explicitly instantiate nested types.</span></span> <span data-ttu-id="5bbe7-113">예를 들어 컬렉션의 열거자는 해당 컬렉션의 중첩 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-113">For example, the enumerator of a collection can be a nested type of that collection.</span></span> <span data-ttu-id="5bbe7-114">열거자는 일반적으로 바깥쪽 형식에 의해 인스턴스화되고 많은 언어에서 foreach 문을 지원 하므로 최종 사용자가 열거자 변수를 거의 선언 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-114">Enumerators are usually instantiated by their enclosing type, and because many languages support the foreach statement, enumerator variables rarely have to be declared by the end user.</span></span>

 <span data-ttu-id="5bbe7-115">중첩 형식과 해당 외부 형식 사이의 관계를 사용 하 여 멤버 액세스 가능성을 적절 하 게 사용 하는 경우에는 중첩 형식을 사용 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-115">✔️ DO use nested types when the relationship between the nested type and its outer type is such that member-accessibility semantics are desirable.</span></span>

 <span data-ttu-id="5bbe7-116">공용 중첩 형식을 논리적 그룹화 구문으로 사용 하지 ❌ 이에 대 한 네임 스페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-116">❌ DO NOT use public nested types as a logical grouping construct; use namespaces for this.</span></span>

 <span data-ttu-id="5bbe7-117">❌ 공개적으로 노출 된 중첩 형식을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-117">❌ AVOID publicly exposed nested types.</span></span> <span data-ttu-id="5bbe7-118">단, 중첩 형식의 변수를 서브클래싱 또는 다른 고급 사용자 지정 시나리오와 같은 드문 시나리오 에서만 선언 해야 하는 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-118">The only exception to this is if variables of the nested type need to be declared only in rare scenarios such as subclassing or other advanced customization scenarios.</span></span>

 <span data-ttu-id="5bbe7-119">포함 하는 형식 외부에서 형식을 참조할 가능성이 있는 경우에는 중첩 형식을 사용 하지 ❌.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-119">❌ DO NOT use nested types if the type is likely to be referenced outside of the containing type.</span></span>

 <span data-ttu-id="5bbe7-120">예를 들어 클래스에 정의 된 메서드에 전달 된 열거형은 클래스에서 중첩 형식으로 정의 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-120">For example, an enum passed to a method defined on a class should not be defined as a nested type in the class.</span></span>

 <span data-ttu-id="5bbe7-121">클라이언트 코드에서 인스턴스화해야 하는 경우에는 중첩 형식을 사용 하지 ❌.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-121">❌ DO NOT use nested types if they need to be instantiated by client code.</span></span>  <span data-ttu-id="5bbe7-122">형식에 public 생성자가 있는 경우 중첩 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-122">If a type has a public constructor, it should probably not be nested.</span></span>

 <span data-ttu-id="5bbe7-123">형식을 인스턴스화할 수 있는 경우 형식에 프레임 워크의 위치가 있음을 나타내는 것 처럼 보일 수 있습니다. 즉, 외부 형식을 사용 하지 않고 작업을 만들어 사용 하 고 사용 하 여 제거할 수 있으므로 중첩 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-123">If a type can be instantiated, that seems to indicate the type has a place in the framework on its own (you can create it, work with it, and destroy it without ever using the outer type), and thus should not be nested.</span></span> <span data-ttu-id="5bbe7-124">외부 형식에 관계 없이 외부 형식의 외부에서 내부 형식을 널리 재사용 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-124">Inner types should not be widely reused outside of the outer type without any relationship whatsoever to the outer type.</span></span>

 <span data-ttu-id="5bbe7-125">중첩 형식을 인터페이스의 멤버로 정의 하지 ❌.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-125">❌ DO NOT define a nested type as a member of an interface.</span></span> <span data-ttu-id="5bbe7-126">많은 언어에서 이러한 구문을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bbe7-126">Many languages do not support such a construct.</span></span>

 <span data-ttu-id="5bbe7-127">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="5bbe7-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="5bbe7-128">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="5bbe7-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="5bbe7-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bbe7-129">See also</span></span>

- [<span data-ttu-id="5bbe7-130">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="5bbe7-130">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="5bbe7-131">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="5bbe7-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
