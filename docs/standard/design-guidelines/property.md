---
description: '자세한 정보: 속성 디자인'
title: 속성 디자인
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
ms.openlocfilehash: b2f776a5fb651f8b2e61b750a556704fa6c8c366
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731801"
---
# <a name="property-design"></a><span data-ttu-id="7ce00-103">속성 디자인</span><span class="sxs-lookup"><span data-stu-id="7ce00-103">Property Design</span></span>

<span data-ttu-id="7ce00-104">속성은 기술적으로 메서드와 매우 유사하지만 사용 시나리오 측면에서는 전혀 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-104">Although properties are technically very similar to methods, they are quite different in terms of their usage scenarios.</span></span> <span data-ttu-id="7ce00-105">속성은 스마트 필드로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-105">They should be seen as smart fields.</span></span> <span data-ttu-id="7ce00-106">속성에는 필드의 호출 구문과 메서드의 유연성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-106">They have the calling syntax of fields, and the flexibility of methods.</span></span>

 <span data-ttu-id="7ce00-107">✔️ 호출자가 속성의 값을 변경할 수 없어야 하는 경우 가져오기 전용 속성을 만드세요.</span><span class="sxs-lookup"><span data-stu-id="7ce00-107">✔️ DO create get-only properties if the caller should not be able to change the value of the property.</span></span>

 <span data-ttu-id="7ce00-108">속성의 형식이 변경 가능한 참조 형식이면 속성이 가져오기 전용인 경우에도 속성 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-108">Keep in mind that if the type of the property is a mutable reference type, the property value can be changed even if the property is get-only.</span></span>

 <span data-ttu-id="7ce00-109">❌ 설정 전용 속성 또는 setter의 접근성이 getter보다 더 광범위한 속성을 제공하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7ce00-109">❌ DO NOT provide set-only properties or properties with the setter having broader accessibility than the getter.</span></span>

 <span data-ttu-id="7ce00-110">예를 들어 퍼블릭 setter 및 보호된 getter가 있는 속성을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7ce00-110">For example, do not use properties with a public setter and a protected getter.</span></span>

 <span data-ttu-id="7ce00-111">속성 getter를 제공할 수 없는 경우 대신 메서드로 기능을 구현하세요.</span><span class="sxs-lookup"><span data-stu-id="7ce00-111">If the property getter cannot be provided, implement the functionality as a method instead.</span></span> <span data-ttu-id="7ce00-112">메서드 이름을 `Set`으로 시작하고 속성의 이름을 지정한 항목을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-112">Consider starting the method name with `Set` and follow with what you would have named the property.</span></span> <span data-ttu-id="7ce00-113">예를 들어 <xref:System.AppDomain>에는 `CachePath`라는 설정 전용 속성 대신 `SetCachePath`라는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-113">For example, <xref:System.AppDomain> has a method called `SetCachePath` instead of having a set-only property called `CachePath`.</span></span>

 <span data-ttu-id="7ce00-114">✔️ 모든 속성에 적절한 기본값을 제공하여 기본값으로 인해 보안 허점이나 매우 비효율적인 코드가 생성되지 않도록 하세요.</span><span class="sxs-lookup"><span data-stu-id="7ce00-114">✔️ DO provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or terribly inefficient code.</span></span>

 <span data-ttu-id="7ce00-115">✔️ 개체의 상태가 일시적으로 잘못되게 되더라도 속성을 원하는 순서대로 설정할 수 있도록 하세요.</span><span class="sxs-lookup"><span data-stu-id="7ce00-115">✔️ DO allow properties to be set in any order even if this results in a temporary invalid state of the object.</span></span>

 <span data-ttu-id="7ce00-116">일반적으로 동일한 개체에서 다른 속성의 값을 지정하면 한 속성의 일부 값이 잘못될 수 있는 지점에서 둘 이상의 속성이 서로 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-116">It is common for two or more properties to be interrelated to a point where some values of one property might be invalid given the values of other properties on the same object.</span></span> <span data-ttu-id="7ce00-117">이러한 경우 잘못된 상태에서 발생한 예외는 서로 관련된 속성이 실제로 개체에서 함께 사용될 때까지 연기되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-117">In such cases, exceptions resulting from the invalid state should be postponed until the interrelated properties are actually used together by the object.</span></span>

 <span data-ttu-id="7ce00-118">✔️ 속성 setter에서 예외가 throw되는 경우 이전 값을 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="7ce00-118">✔️ DO preserve the previous value if a property setter throws an exception.</span></span>

 <span data-ttu-id="7ce00-119">❌ 속성 getter에서 예외를 throw하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-119">❌ AVOID throwing exceptions from property getters.</span></span>

 <span data-ttu-id="7ce00-120">속성 getter는 간단한 작업이어야 하며 사전 조건이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-120">Property getters should be simple operations and should not have any preconditions.</span></span> <span data-ttu-id="7ce00-121">getter에서 예외가 throw될 수 있으면 메서드로 다시 디자인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-121">If a getter can throw an exception, it should probably be redesigned to be a method.</span></span> <span data-ttu-id="7ce00-122">인수 유효성 검사의 결과로 예외가 예상되는 인덱서에는 이 규칙이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-122">Notice that this rule does not apply to indexers, where we do expect exceptions as a result of validating the arguments.</span></span>

### <a name="indexed-property-design"></a><span data-ttu-id="7ce00-123">인덱싱된 속성 디자인</span><span class="sxs-lookup"><span data-stu-id="7ce00-123">Indexed Property Design</span></span>

 <span data-ttu-id="7ce00-124">인덱싱된 속성은 매개 변수를 포함할 수 있고 배열 인덱싱과 유사한 특수 구문으로 호출할 수 있는 특수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-124">An indexed property is a special property that can have parameters and can be called with special syntax similar to array indexing.</span></span>

 <span data-ttu-id="7ce00-125">인덱싱된 속성을 일반적으로 인덱서라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-125">Indexed properties are commonly referred to as indexers.</span></span> <span data-ttu-id="7ce00-126">인덱서는 논리 컬렉션의 항목에 대한 액세스 권한을 제공하는 API에서만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-126">Indexers should be used only in APIs that provide access to items in a logical collection.</span></span> <span data-ttu-id="7ce00-127">예를 들어 문자열은 문자의 컬렉션이며 <xref:System.String?displayProperty=nameWithType>의 인덱서는 해당 문자에 액세스하기 위해 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-127">For example, a string is a collection of characters, and the indexer on <xref:System.String?displayProperty=nameWithType> was added to access its characters.</span></span>

 <span data-ttu-id="7ce00-128">✔️ 내부 배열에 저장된 데이터에 대한 액세스 권한을 제공하려면 인덱서를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-128">✔️ CONSIDER using indexers to provide access to data stored in an internal array.</span></span>

 <span data-ttu-id="7ce00-129">✔️ 항목의 컬렉션을 나타내는 형식에서 인덱서를 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-129">✔️ CONSIDER providing indexers on types representing collections of items.</span></span>

 <span data-ttu-id="7ce00-130">❌ 둘 이상의 매개 변수가 있는 인덱싱된 속성을 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-130">❌ AVOID using indexed properties with more than one parameter.</span></span>

 <span data-ttu-id="7ce00-131">여러 매개 변수가 필요한 디자인에서는 속성이 실제로 논리 컬렉션에 대한 접근자를 나타내는지를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-131">If the design requires multiple parameters, reconsider whether the property really represents an accessor to a logical collection.</span></span> <span data-ttu-id="7ce00-132">그렇지 않은 경우 메서드를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-132">If it does not, use methods instead.</span></span> <span data-ttu-id="7ce00-133">메서드 이름은 `Get` 또는 `Set`으로 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-133">Consider starting the method name with `Get` or `Set`.</span></span>

 <span data-ttu-id="7ce00-134">❌ <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> 또는 열거형 이외의 매개 변수 형식을 사용하는 인덱서는 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-134">❌ AVOID indexers with parameter types other than <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, or an enum.</span></span>

 <span data-ttu-id="7ce00-135">다른 형식의 매개 변수가 필요한 디자인에서는 API가 실제로 논리 컬렉션에 대한 접근자를 나타내는지를 강력히 다시 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-135">If the design requires other types of parameters, strongly reevaluate whether the API really represents an accessor to a logical collection.</span></span> <span data-ttu-id="7ce00-136">그렇지 않은 경우 메서드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7ce00-136">If it does not, use a method.</span></span> <span data-ttu-id="7ce00-137">메서드 이름은 `Get` 또는 `Set`으로 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-137">Consider starting the method name with `Get` or `Set`.</span></span>

 <span data-ttu-id="7ce00-138">✔️ 명백하게 더 좋은 이름(예: `System.String`의 <xref:System.String.Chars%2A> 속성 참조)이 없는 경우 인덱싱된 속성에 이름 `Item`을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7ce00-138">✔️ DO use the name `Item` for indexed properties unless there is an obviously better name (e.g., see the <xref:System.String.Chars%2A> property on `System.String`).</span></span>

 <span data-ttu-id="7ce00-139">C#에서는 인덱서 이름이 기본적으로 Item으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-139">In C#, indexers are by default named Item.</span></span> <span data-ttu-id="7ce00-140"><xref:System.Runtime.CompilerServices.IndexerNameAttribute>를 사용하여 이 이름을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-140">The <xref:System.Runtime.CompilerServices.IndexerNameAttribute> can be used to customize this name.</span></span>

 <span data-ttu-id="7ce00-141">❌ 의미 체계가 동일한 인덱서와 메서드를 둘 다 제공하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7ce00-141">❌ DO NOT provide both an indexer and methods that are semantically equivalent.</span></span>

 <span data-ttu-id="7ce00-142">❌ 한 형식에서 오버로드된 인덱서 패밀리를 둘 이상 제공하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7ce00-142">❌ DO NOT provide more than one family of overloaded indexers in one type.</span></span>

 <span data-ttu-id="7ce00-143">이 규칙은 C# 컴파일러에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-143">This is enforced by the C# compiler.</span></span>

 <span data-ttu-id="7ce00-144">❌ 기본값이 아닌 인덱싱된 속성을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7ce00-144">❌ DO NOT use nondefault indexed properties.</span></span>

 <span data-ttu-id="7ce00-145">이 규칙은 C# 컴파일러에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-145">This is enforced by the C# compiler.</span></span>

### <a name="property-change-notification-events"></a><span data-ttu-id="7ce00-146">속성 변경 알림 이벤트</span><span class="sxs-lookup"><span data-stu-id="7ce00-146">Property Change Notification Events</span></span>

 <span data-ttu-id="7ce00-147">경우에 따라 속성 값의 변경을 사용자에게 알리는 이벤트를 제공하면 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-147">Sometimes it is useful to provide an event notifying the user of changes in a property value.</span></span> <span data-ttu-id="7ce00-148">예를 들어 `Text` 속성 값이 변경된 후 `System.Windows.Forms.Control`에서 `TextChanged` 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-148">For example, `System.Windows.Forms.Control` raises a `TextChanged` event after the value of its `Text` property has changed.</span></span>

 <span data-ttu-id="7ce00-149">✔️ 상위 수준 API(일반적으로 디자이너 구성 요소)에서 속성 값이 수정되면 변경 알림 이벤트를 발생시키는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-149">✔️ CONSIDER raising change notification events when property values in high-level APIs (usually designer components) are modified.</span></span>

 <span data-ttu-id="7ce00-150">개체의 속성이 변경될 때 사용자가 알아야 하는 좋은 시나리오가 있는 경우 개체는 속성에 대해 변경 알림 이벤트를 발생시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-150">If there is a good scenario for a user to know when a property of an object is changing, the object should raise a change notification event for the property.</span></span>

 <span data-ttu-id="7ce00-151">그러나 기본 형식이나 컬렉션과 같은 하위 수준 API에 대해 이러한 이벤트를 발생시키면 오버헤드가 될 가능성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-151">However, it is unlikely to be worth the overhead to raise such events for low-level APIs such as base types or collections.</span></span> <span data-ttu-id="7ce00-152">예를 들어 새 항목이 목록에 추가되고 `Count` 속성이 변경되면 <xref:System.Collections.Generic.List%601>에서 이러한 이벤트를 발생시키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-152">For example, <xref:System.Collections.Generic.List%601> would not raise such events when a new item is added to the list and the `Count` property changes.</span></span>

 <span data-ttu-id="7ce00-153">✔️ 속성 값이 외부의 힘에 의해 변경되는 경우에는 변경 알림 이벤트를 발생시키는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-153">✔️ CONSIDER raising change notification events when the value of a property changes via external forces.</span></span>

 <span data-ttu-id="7ce00-154">속성 값이 일부 외부의 힘(개체에서 메서드를 호출하는 것 이외의 방식)을 통해 변경되는 경우 이벤트 발생은 값이 변경되고 있고 변경되었음을 개발자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-154">If a property value changes via some external force (in a way other than by calling methods on the object), raise events indicate to the developer that the value is changing and has changed.</span></span> <span data-ttu-id="7ce00-155">좋은 예로 텍스트 상자 컨트롤의 `Text` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-155">A good example is the `Text` property of a text box control.</span></span> <span data-ttu-id="7ce00-156">사용자가 `TextBox`에 텍스트를 입력하면 속성 값이 자동으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ce00-156">When the user types text in a `TextBox`, the property value automatically changes.</span></span>

 <span data-ttu-id="7ce00-157">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="7ce00-157">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="7ce00-158">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="7ce00-158">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="7ce00-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ce00-159">See also</span></span>

- [<span data-ttu-id="7ce00-160">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="7ce00-160">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="7ce00-161">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="7ce00-161">Framework Design Guidelines</span></span>](index.md)
