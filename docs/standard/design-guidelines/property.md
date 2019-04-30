---
title: 속성 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
author: KrzysztofCwalina
ms.openlocfilehash: e4ed4fd39a9ebd63b9d5dbff38dc15647d65934f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026318"
---
# <a name="property-design"></a><span data-ttu-id="d9a5d-102">속성 디자인</span><span class="sxs-lookup"><span data-stu-id="d9a5d-102">Property Design</span></span>
<span data-ttu-id="d9a5d-103">속성 메서드 기술적으로 매우 유사 하지만, 사용 시나리오는 큰 차이가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-103">Although properties are technically very similar to methods, they are quite different in terms of their usage scenarios.</span></span> <span data-ttu-id="d9a5d-104">스마트 필드로 보여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-104">They should be seen as smart fields.</span></span> <span data-ttu-id="d9a5d-105">필드가 호출 구문 및 메서드의 유연성을가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-105">They have the calling syntax of fields, and the flexibility of methods.</span></span>  
  
 <span data-ttu-id="d9a5d-106">**✓ DO** 호출자 속성의 값을 변경할 수 없어야 하는 경우 가져오기 전용 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-106">**✓ DO** create get-only properties if the caller should not be able to change the value of the property.</span></span>  
  
 <span data-ttu-id="d9a5d-107">염두에서에 둡니다 경우 형식의 속성 변경 가능한 참조 형식인, 경우에 속성이 가져오기 전용 속성 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-107">Keep in mind that if the type of the property is a mutable reference type, the property value can be changed even if the property is get-only.</span></span>  
  
 <span data-ttu-id="d9a5d-108">**X DO NOT** getter 보다 광범위 한 액세스 가능성을 가진 setter에 설정 전용 속성 또는 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-108">**X DO NOT** provide set-only properties or properties with the setter having broader accessibility than the getter.</span></span>  
  
 <span data-ttu-id="d9a5d-109">예를 들어, public setter 및 getter를 보호를 사용 하 여 속성을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-109">For example, do not use properties with a public setter and a protected getter.</span></span>  
  
 <span data-ttu-id="d9a5d-110">속성 getter를 제공할 수 없습니다, 하는 경우 대신 하는 방법으로 기능을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-110">If the property getter cannot be provided, implement the functionality as a method instead.</span></span> <span data-ttu-id="d9a5d-111">메서드 이름의 시작 하는 것이 좋습니다. `Set` 고 뒤에 새로운는 명명 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-111">Consider starting the method name with `Set` and follow with what you would have named the property.</span></span> <span data-ttu-id="d9a5d-112">예를 들어 <xref:System.AppDomain> 라는 메서드가 `SetCachePath` 호출 집합 전용 속성을 대신 `CachePath`합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-112">For example, <xref:System.AppDomain> has a method called `SetCachePath` instead of having a set-only property called `CachePath`.</span></span>  
  
 <span data-ttu-id="d9a5d-113">**✓ DO** 기본값 보안상 또는 치명적인 오류가 비효율적인 코드에서 발생 하지 않습니다 보장 하는 모든 속성에 대 한 적절 한 기본값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-113">**✓ DO** provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or terribly inefficient code.</span></span>  
  
 <span data-ttu-id="d9a5d-114">**✓ DO** 속성을 개체의 임시 잘못 된 상태에이 인해 경우에 순서에 관계 없이 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-114">**✓ DO** allow properties to be set in any order even if this results in a temporary invalid state of the object.</span></span>  
  
 <span data-ttu-id="d9a5d-115">여기서 한 속성 값 일부 잘못 된 것 같습니다 지점으로 상호 관련 되도록 두 개 이상의 속성에 대 한 일반적 동일한 개체에서 다른 속성의 값이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-115">It is common for two or more properties to be interrelated to a point where some values of one property might be invalid given the values of other properties on the same object.</span></span> <span data-ttu-id="d9a5d-116">이러한 경우 개체에서 상호 관련 된 속성을 함께 사용 실제로 때까지 잘못 된 상태에서 발생 한 예외를 연기 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-116">In such cases, exceptions resulting from the invalid state should be postponed until the interrelated properties are actually used together by the object.</span></span>  
  
 <span data-ttu-id="d9a5d-117">**✓ DO** 속성 setter 예외를 throw 하는 경우 이전 값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-117">**✓ DO** preserve the previous value if a property setter throws an exception.</span></span>  
  
 <span data-ttu-id="d9a5d-118">**X AVOID** 속성 getter에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-118">**X AVOID** throwing exceptions from property getters.</span></span>  
  
 <span data-ttu-id="d9a5d-119">속성 getter 간단한 작업 해야 하 고 사전 조건이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-119">Property getters should be simple operations and should not have any preconditions.</span></span> <span data-ttu-id="d9a5d-120">Getter 예외를 throw 하 고, 메서드가 되도록 아마도 재설계 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-120">If a getter can throw an exception, it should probably be redesigned to be a method.</span></span> <span data-ttu-id="d9a5d-121">예외는 인수 유효성 검사의 결과로 기대할 수 있는 인덱서를이 규칙이 적용 되지 않습니다 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-121">Notice that this rule does not apply to indexers, where we do expect exceptions as a result of validating the arguments.</span></span>  
  
### <a name="indexed-property-design"></a><span data-ttu-id="d9a5d-122">인덱싱된 속성 디자인</span><span class="sxs-lookup"><span data-stu-id="d9a5d-122">Indexed Property Design</span></span>  
 <span data-ttu-id="d9a5d-123">인덱싱된 속성은 특수 속성으로는 매개 변수를 가질 수 있으며 배열 인덱싱 유사한 특수 구문을 사용 하 여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-123">An indexed property is a special property that can have parameters and can be called with special syntax similar to array indexing.</span></span>  
  
 <span data-ttu-id="d9a5d-124">인덱싱된 속성은 일반적으로 인덱서 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-124">Indexed properties are commonly referred to as indexers.</span></span> <span data-ttu-id="d9a5d-125">인덱서는 논리적 컬렉션의 항목에 대 한 액세스를 제공 하는 Api 에서만에서 사용할 수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-125">Indexers should be used only in APIs that provide access to items in a logical collection.</span></span> <span data-ttu-id="d9a5d-126">예를 들어 문자열은 문자 및 인덱서를 컬렉션인 <xref:System.String?displayProperty=nameWithType> 해당 문자 액세스에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-126">For example, a string is a collection of characters, and the indexer on <xref:System.String?displayProperty=nameWithType> was added to access its characters.</span></span>  
  
 <span data-ttu-id="d9a5d-127">**✓ CONSIDER** 인덱서를 사용 하 여 내부 배열에 저장 된 데이터에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-127">**✓ CONSIDER** using indexers to provide access to data stored in an internal array.</span></span>  
  
 <span data-ttu-id="d9a5d-128">**✓ CONSIDER** 컬렉션 항목을 나타내는 형식에 인덱서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-128">**✓ CONSIDER** providing indexers on types representing collections of items.</span></span>  
  
 <span data-ttu-id="d9a5d-129">**X AVOID** 를 사용 하 여 인덱싱된 속성 둘 이상의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-129">**X AVOID** using indexed properties with more than one parameter.</span></span>  
  
 <span data-ttu-id="d9a5d-130">디자인에 여러 매개 변수가 필요한 경우 속성은 논리적 컬렉션에 실제로 접근자를 나타내는지 여부를 다시 고려해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-130">If the design requires multiple parameters, reconsider whether the property really represents an accessor to a logical collection.</span></span> <span data-ttu-id="d9a5d-131">표시 되지 않는 메서드를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-131">If it does not, use methods instead.</span></span> <span data-ttu-id="d9a5d-132">메서드 이름을 사용 하 여 시작 하는 것이 좋습니다 `Get` 또는 `Set`합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-132">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="d9a5d-133">**X AVOID** 외의 다른 매개 변수 형식 가진 인덱서 <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, 또는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-133">**X AVOID** indexers with parameter types other than <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, or an enum.</span></span>  
  
 <span data-ttu-id="d9a5d-134">디자인에 필요한 다른 유형의 매개 변수를 강력한 다시 평가 API를 논리 컬렉션에 실제로 접근자를 나타내는지 여부를 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-134">If the design requires other types of parameters, strongly reevaluate whether the API really represents an accessor to a logical collection.</span></span> <span data-ttu-id="d9a5d-135">표시 되지 않는 경우 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-135">If it does not, use a method.</span></span> <span data-ttu-id="d9a5d-136">메서드 이름을 사용 하 여 시작 하는 것이 좋습니다 `Get` 또는 `Set`합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-136">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="d9a5d-137">**✓ DO** 이름을 사용 하 여 `Item` 에 대 한는 분명히 더 나은 이름일 경우를 제외 인덱싱된 속성 (예:, 참조는 <xref:System.String.Chars%2A> 속성을 `System.String`).</span><span class="sxs-lookup"><span data-stu-id="d9a5d-137">**✓ DO** use the name `Item` for indexed properties unless there is an obviously better name (e.g., see the <xref:System.String.Chars%2A> property on `System.String`).</span></span>  
  
 <span data-ttu-id="d9a5d-138">C#에서는 인덱서 항목 이름이 기본적으로는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-138">In C#, indexers are by default named Item.</span></span> <span data-ttu-id="d9a5d-139"><xref:System.Runtime.CompilerServices.IndexerNameAttribute> 이 이름에 맞게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-139">The <xref:System.Runtime.CompilerServices.IndexerNameAttribute> can be used to customize this name.</span></span>  
  
 <span data-ttu-id="d9a5d-140">**X DO NOT** 인덱서 및 메서드는 의미가 동일한 형식으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-140">**X DO NOT** provide both an indexer and methods that are semantically equivalent.</span></span>  
  
 <span data-ttu-id="d9a5d-141">**X DO NOT** 둘 이상의 제품군의 한 가지 형식으로 오버 로드 된 인덱서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-141">**X DO NOT** provide more than one family of overloaded indexers in one type.</span></span>  
  
 <span data-ttu-id="d9a5d-142">이 C# 컴파일러에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-142">This is enforced by the C# compiler.</span></span>  
  
 <span data-ttu-id="d9a5d-143">**X DO NOT** 인덱싱된 속성을 사용 하 여 기본이 아닌 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-143">**X DO NOT** use nondefault indexed properties.</span></span>  
  
 <span data-ttu-id="d9a5d-144">이 C# 컴파일러에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-144">This is enforced by the C# compiler.</span></span>  
  
### <a name="property-change-notification-events"></a><span data-ttu-id="d9a5d-145">속성 변경 알림 이벤트</span><span class="sxs-lookup"><span data-stu-id="d9a5d-145">Property Change Notification Events</span></span>  
 <span data-ttu-id="d9a5d-146">경우에 따라 속성 값의 변경 내용을 사용자에 게 알리는 이벤트를 제공 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-146">Sometimes it is useful to provide an event notifying the user of changes in a property value.</span></span> <span data-ttu-id="d9a5d-147">예를 들어 `System.Windows.Forms.Control` 발생을 `TextChanged` 이벤트 후의 값 해당 `Text` 속성이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-147">For example, `System.Windows.Forms.Control` raises a `TextChanged` event after the value of its `Text` property has changed.</span></span>  
  
 <span data-ttu-id="d9a5d-148">**✓ CONSIDER** 를 발생 시키는 변경 알림 이벤트 고급 수준의 Api (일반적으로 디자이너 구성 요소)의 속성 값이 수정 된 경우.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-148">**✓ CONSIDER** raising change notification events when property values in high-level APIs (usually designer components) are modified.</span></span>  
  
 <span data-ttu-id="d9a5d-149">개체의 속성을 변경 하는 경우 알아야 사용자의 좋은 시나리오의 경우 개체 속성 변경 알림 이벤트를 발생 시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-149">If there is a good scenario for a user to know when a property of an object is changing, the object should raise a change notification event for the property.</span></span>  
  
 <span data-ttu-id="d9a5d-150">그러나 기본 형식 또는 컬렉션 등의 하위 수준 Api에 대 한 이러한 이벤트를 발생 시키기 위해 때문에 오버 헤드가 수 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-150">However, it is unlikely to be worth the overhead to raise such events for low-level APIs such as base types or collections.</span></span> <span data-ttu-id="d9a5d-151">예를 들어 <xref:System.Collections.Generic.List%601> 새 항목을 목록에 추가 되 면 이러한 이벤트를 발생 시 키 지는 및 `Count` 속성 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-151">For example, <xref:System.Collections.Generic.List%601> would not raise such events when a new item is added to the list and the `Count` property changes.</span></span>  
  
 <span data-ttu-id="d9a5d-152">**✓ CONSIDER** 알림 이벤트 속성의 값이 외부 강제를 통해 변경 될 때 변경 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-152">**✓ CONSIDER** raising change notification events when the value of a property changes via external forces.</span></span>  
  
 <span data-ttu-id="d9a5d-153">외부 요인 (방식 이외의 다른 개체에서 메서드를 호출 하 여)를 통해 속성 값을 변경 하는 경우 이벤트는 값을 변경 되 고이 변경 하는 개발자에 게 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-153">If a property value changes via some external force (in a way other than by calling methods on the object), raise events indicate to the developer that the value is changing and has changed.</span></span> <span data-ttu-id="d9a5d-154">좋은 예로 `Text` 텍스트 상자 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-154">A good example is the `Text` property of a text box control.</span></span> <span data-ttu-id="d9a5d-155">사용자의 텍스트를 입력 하는 경우는 `TextBox`, 속성 값이 자동으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a5d-155">When the user types text in a `TextBox`, the property value automatically changes.</span></span>  
  
 <span data-ttu-id="d9a5d-156">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="d9a5d-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d9a5d-157">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="d9a5d-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a5d-158">참고자료</span><span class="sxs-lookup"><span data-stu-id="d9a5d-158">See also</span></span>

- [<span data-ttu-id="d9a5d-159">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d9a5d-159">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="d9a5d-160">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d9a5d-160">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
