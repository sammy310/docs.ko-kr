---
title: 이벤트 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
ms.openlocfilehash: b44ee5933f8629b4dddbf3be1b79b2e77b0254f7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741682"
---
# <a name="event-design"></a><span data-ttu-id="4c829-102">이벤트 디자인</span><span class="sxs-lookup"><span data-stu-id="4c829-102">Event Design</span></span>
<span data-ttu-id="4c829-103">이벤트는 가장 일반적으로 사용 되는 콜백 형태입니다 (프레임 워크가 사용자 코드를 호출할 수 있도록 하는 구문).</span><span class="sxs-lookup"><span data-stu-id="4c829-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="4c829-104">다른 콜백 메커니즘에는 대리자, 가상 멤버 및 인터페이스 기반 플러그 인을 사용 하는 멤버가 포함 되어 있습니다. 유용성 연구의 데이터는 대부분의 개발자가 다른 콜백 메커니즘을 사용 하는 것 보다 많은 이벤트를 사용 하는 것이 더 편안 함을 의미 합니다. .</span><span class="sxs-lookup"><span data-stu-id="4c829-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="4c829-105">이벤트는 Visual Studio 및 많은 언어와 잘 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-105">Events are nicely integrated with Visual Studio and many languages.</span></span>

 <span data-ttu-id="4c829-106">이벤트의 두 그룹에는 이벤트의 상태를 변경 하기 전에 발생 하는 이벤트, 사전 이벤트 라는 이벤트, 상태 변경 후 발생 한 이벤트 (사후 이벤트)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="4c829-107">이전 이벤트의 예는 폼을 닫기 전에 발생 하는 `Form.Closing`입니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="4c829-108">사후 이벤트의 예는 폼이 닫힌 후에 발생 하는 `Form.Closed`됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>

 <span data-ttu-id="4c829-109">✔️ "fire" 또는 "트리거" 대신 이벤트에 대해 "발생" 이라는 용어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-109">✔️ DO use the term "raise" for events rather than "fire" or "trigger."</span></span>

 <span data-ttu-id="4c829-110">✔️는 이벤트 처리기로 사용할 새 대리자를 수동으로 만드는 대신 <xref:System.EventHandler%601?displayProperty=nameWithType>를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-110">✔️ DO use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>

 <span data-ttu-id="4c829-111">이벤트는 이벤트 처리 메서드에 데이터를 전달할 필요가 없는 경우를 제외 하 고는 이벤트 인수로 <xref:System.EventArgs> 하위 클래스를 사용 하는 것이 좋습니다 .이 경우 `EventArgs` 형식을 직접 사용할 수 있습니다. ✔️</span><span class="sxs-lookup"><span data-stu-id="4c829-111">✔️ CONSIDER using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>

 <span data-ttu-id="4c829-112">`EventArgs`를 사용 하 여 직접 API를 제공 하는 경우 호환성을 위반 하지 않고 이벤트와 함께 수행할 데이터를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="4c829-113">서브 클래스를 사용 하는 경우 처음에는 완전히 비어 있더라도 필요할 때 하위 클래스에 속성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>

 <span data-ttu-id="4c829-114">✔️는 보호 되는 가상 메서드를 사용 하 여 각 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-114">✔️ DO use a protected virtual method to raise each event.</span></span> <span data-ttu-id="4c829-115">이는 구조체, 봉인 클래스 또는 정적 이벤트가 아니라 봉인 되지 않은 클래스의 비정적 이벤트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>

 <span data-ttu-id="4c829-116">메서드의 목적은 파생 클래스에서 재정의를 사용 하 여 이벤트를 처리 하는 방법을 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="4c829-117">재정의는 파생 클래스에서 기본 클래스 이벤트를 처리 하는 보다 유연 하 고, 빠르고, 자연스럽는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="4c829-118">규칙에 따라 메서드 이름은 "On"으로 시작 하 고 이벤트 이름을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>

 <span data-ttu-id="4c829-119">파생 클래스는 재정의에서 메서드의 기본 구현을 호출 하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="4c829-120">기본 클래스가 제대로 작동 하는 데 필요한 메서드의 처리를 포함 하지 않고이를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>

 <span data-ttu-id="4c829-121">✔️는 이벤트를 발생 시키는 보호 된 메서드에 매개 변수 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-121">✔️ DO take one parameter to the protected method that raises an event.</span></span>

 <span data-ttu-id="4c829-122">매개 변수 이름은 `e`로 지정 해야 하며 이벤트 인수 클래스로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>

 <span data-ttu-id="4c829-123">❌ 비정적 이벤트를 발생 시킬 때 발신자로 null을 전달 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-123">❌ DO NOT pass null as the sender when raising a nonstatic event.</span></span>

 <span data-ttu-id="4c829-124">✔️는 정적 이벤트를 발생 시킬 때 보낸 사람으로 null을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-124">✔️ DO pass null as the sender when raising a static event.</span></span>

 <span data-ttu-id="4c829-125">❌ 이벤트를 발생 시킬 때 null을 이벤트 데이터 매개 변수로 전달 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-125">❌ DO NOT pass null as the event data parameter when raising an event.</span></span>

 <span data-ttu-id="4c829-126">이벤트 처리 메서드에 데이터를 전달 하지 않으려는 경우 `EventArgs.Empty`를 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="4c829-127">개발자는이 매개 변수가 null이 아닌 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-127">Developers expect this parameter not to be null.</span></span>

 <span data-ttu-id="4c829-128">✔️ 최종 사용자가 취소할 수 있는 이벤트를 발생 시키는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-128">✔️ CONSIDER raising events that the end user can cancel.</span></span> <span data-ttu-id="4c829-129">이는 사전 이벤트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-129">This only applies to pre-events.</span></span>

 <span data-ttu-id="4c829-130">최종 사용자가 이벤트를 취소할 수 있도록 하려면 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> 또는 해당 하위 클래스를 이벤트 인수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>

### <a name="custom-event-handler-design"></a><span data-ttu-id="4c829-131">사용자 지정 이벤트 처리기 디자인</span><span class="sxs-lookup"><span data-stu-id="4c829-131">Custom Event Handler Design</span></span>
 <span data-ttu-id="4c829-132">프레임 워크에서 제네릭을 지원 하지 않는 이전 버전의 CLR과 함께 작업 해야 하는 경우와 같이 `EventHandler<T>`를 사용할 수 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="4c829-133">이러한 경우 사용자 지정 이벤트 처리기 대리자를 디자인 하 고 개발 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>

 <span data-ttu-id="4c829-134">✔️는 이벤트 처리기에 void의 반환 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-134">✔️ DO use a return type of void for event handlers.</span></span>

 <span data-ttu-id="4c829-135">이벤트 처리기는 여러 개체에서 여러 이벤트 처리 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="4c829-136">이벤트 처리 메서드가 값을 반환할 수 있는 경우 각 이벤트 호출에 대해 여러 개의 반환 값이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>

 <span data-ttu-id="4c829-137">✔️ `object`을 이벤트 처리기의 첫 번째 매개 변수 형식으로 사용 하 고 `sender`호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-137">✔️ DO use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>

 <span data-ttu-id="4c829-138">✔️ <xref:System.EventArgs?displayProperty=nameWithType> 또는 해당 하위 클래스를 이벤트 처리기의 두 번째 매개 변수 형식으로 사용 하 고 `e`호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-138">✔️ DO use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>

 <span data-ttu-id="4c829-139">이벤트 처리기에는 매개 변수를 세 개 이상 사용할 ❌ 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c829-139">❌ DO NOT have more than two parameters on event handlers.</span></span>

 <span data-ttu-id="4c829-140">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="4c829-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4c829-141">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="4c829-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4c829-142">참조</span><span class="sxs-lookup"><span data-stu-id="4c829-142">See also</span></span>

- [<span data-ttu-id="4c829-143">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4c829-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="4c829-144">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4c829-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
