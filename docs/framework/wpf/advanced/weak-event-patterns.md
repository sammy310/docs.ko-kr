---
title: 약한 이벤트 패턴
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: c0bf92c9b6046d531e75771a9205e6dffe0fd367
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458487"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="79e80-102">약한 이벤트 패턴</span><span class="sxs-lookup"><span data-stu-id="79e80-102">Weak Event Patterns</span></span>
<span data-ttu-id="79e80-103">응용 프로그램에서 이벤트 소스에 연결 된 처리기가 소스에 처리기를 연결 하는 수신기 개체와 조정 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="79e80-104">이 경우 메모리 누수가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="79e80-105">는 특정 이벤트에 대 한 전용 관리자 클래스를 제공 하 고 해당 이벤트에 대 한 수신기에 인터페이스를 구현 하 여이 문제를 해결 하는 데 사용할 수 있는 디자인 패턴을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-105">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="79e80-106">이 디자인 패턴을 *약한 이벤트 패턴*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="79e80-107">약한 이벤트 패턴을 구현 하는 이유</span><span class="sxs-lookup"><span data-stu-id="79e80-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="79e80-108">이벤트를 수신 대기 하면 메모리 누수가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="79e80-109">이벤트를 수신 하는 일반적인 방법은 소스에서 이벤트에 처리기를 연결 하는 언어 관련 구문을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="79e80-110">예를 들어에서 C#해당 구문은 `source.SomeEvent += new SomeEventHandler(MyEventHandler)`입니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="79e80-111">이 기술은 이벤트 소스에서 이벤트 수신기로의 강력한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="79e80-112">일반적으로 수신기에 대 한 이벤트 처리기를 연결 하면 이벤트 처리기가 명시적으로 제거 되지 않는 한 수신기에 소스의 개체 수명에 의해 영향을 받는 개체 수명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="79e80-113">그러나 특정 상황에서는 수신기의 개체 수명이 다른 요소 (예: 현재 응용 프로그램의 시각적 트리에 속해 있는지 여부, 소스 수명이 아닌 경우)에 의해 제어 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="79e80-114">소스 개체 수명이 수신기의 개체 수명 보다 크게 확장 될 때마다 일반적인 이벤트 패턴은 메모리 누수를 초래 합니다. 수신기는 의도 한 것 보다 오래 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="79e80-115">약한 이벤트 패턴은이 메모리 누수 문제를 해결 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="79e80-116">약한 이벤트 패턴은 수신기가 이벤트에 등록 해야 할 때마다 사용할 수 있지만, 수신기가 등록 취소할 시기를 명시적으로 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="79e80-117">소스의 개체 수명이 수신기의 유용한 개체 수명을 초과할 때마다 weak 이벤트 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="79e80-118">(이 경우에는 *유용* 하 게 결정 됩니다.) Weak 이벤트 패턴을 사용 하면 수신기가 수신기의 개체 수명 특성에 영향을 주지 않고 이벤트를 등록 하 고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="79e80-119">실제로 소스에서 암시 된 참조는 수신기가 가비지 수집에 적합 한지 여부를 결정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="79e80-120">참조는 약한 참조 이므로 weak 이벤트 패턴 및 관련 Api의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-120">The reference is a weak reference, thus the naming of the weak event pattern and the related APIs.</span></span> <span data-ttu-id="79e80-121">수신기를 가비지 수집 하거나 소멸 시킬 수 있으며, 현재 소멸 된 개체에 대 한 수집 되지 않은 처리기 참조를 유지 하지 않고 소스를 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="79e80-122">약한 이벤트 패턴을 구현 해야 하는 사람은 누구 인가요?</span><span class="sxs-lookup"><span data-stu-id="79e80-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="79e80-123">약한 이벤트 패턴을 구현 하는 것은 주로 컨트롤 작성자에 게 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="79e80-124">컨트롤 작성자는 컨트롤이 삽입 되는 응용 프로그램에 미치는 영향 및 컨트롤의 동작 및 포함을 주로 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="79e80-125">여기에는 제어 개체 수명 동작이 포함 됩니다. 특히 설명 된 메모리 누수 문제를 처리 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="79e80-126">특정 시나리오는 기본적으로 약한 이벤트 패턴의 응용 프로그램에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="79e80-127">이러한 시나리오 중 하나는 데이터 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-127">One such scenario is data binding.</span></span> <span data-ttu-id="79e80-128">데이터 바인딩에서 소스 개체는 일반적으로 바인딩의 대상인 수신기 개체와 완전히 독립적으로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="79e80-129">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩의 많은 측면에는 이벤트 구현 방법에 이미 weak 이벤트 패턴이 적용 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="79e80-130">약한 이벤트 패턴을 구현 하는 방법</span><span class="sxs-lookup"><span data-stu-id="79e80-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="79e80-131">약한 이벤트 패턴을 구현 하는 방법에는 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="79e80-132">다음 표에서는 세 가지 방법을 나열 하 고 각각을 사용 해야 하는 경우에 대 한 몇 가지 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="79e80-133">방법</span><span class="sxs-lookup"><span data-stu-id="79e80-133">Approach</span></span>|<span data-ttu-id="79e80-134">구현 시기</span><span class="sxs-lookup"><span data-stu-id="79e80-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="79e80-135">기존 weak 이벤트 관리자 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="79e80-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="79e80-136">구독할 이벤트에 해당 하는 <xref:System.Windows.WeakEventManager>있는 경우 기존 weak 이벤트 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="79e80-137">WPF에 포함 된 weak 이벤트 관리자 목록은 <xref:System.Windows.WeakEventManager> 클래스에서 상속 계층 구조를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="79e80-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="79e80-138">포함 된 weak 이벤트 관리자는 제한적 이므로 다른 방법 중 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-138">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="79e80-139">일반적인 약한 이벤트 관리자 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="79e80-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="79e80-140">기존 <xref:System.Windows.WeakEventManager>를 사용할 수 없는 경우 일반 <xref:System.Windows.WeakEventManager%602>를 사용 합니다 .이 방법을 사용 하면 간편 하 게 구현할 수 있으며 효율성에 대해 염려 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="79e80-141">일반 <xref:System.Windows.WeakEventManager%602>는 기존 또는 사용자 지정 weak 이벤트 관리자 보다 효율성이 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="79e80-142">예를 들어, 제네릭 클래스는 이벤트 이름이 지정 된 경우 이벤트를 검색 하기 위해 더 많은 리플렉션을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="79e80-143">또한 일반적인 <xref:System.Windows.WeakEventManager%602>를 사용 하 여 이벤트를 등록 하는 코드는 기존 또는 사용자 지정 <xref:System.Windows.WeakEventManager>를 사용 하는 것 보다 더 자세한 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="79e80-144">사용자 지정 weak 이벤트 관리자 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="79e80-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="79e80-145">기존 <xref:System.Windows.WeakEventManager>를 사용할 수 없는 경우 사용자 지정 <xref:System.Windows.WeakEventManager>를 만들고 최상의 효율성을 원합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="79e80-146">사용자 지정 <xref:System.Windows.WeakEventManager>를 사용 하 여 이벤트를 구독 하는 것이 더 효율적 이지만 앞으로 더 많은 코드를 작성 하는 비용이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="79e80-147">타사 weak 이벤트 관리자 사용</span><span class="sxs-lookup"><span data-stu-id="79e80-147">Use a third-party weak event manager</span></span>|<span data-ttu-id="79e80-148">NuGet에는 [몇 가지 weak 이벤트 관리자](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) 가 있으며 많은 WPF 프레임 워크 에서도 패턴을 지원 합니다. 예를 들어 느슨하게 연결 된 [이벤트 구독에 대 한 프리즘 설명서](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="79e80-148">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="79e80-149">다음 섹션에서는 weak 이벤트 패턴을 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-149">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="79e80-150">이 논의의 목적을 위해 구독할 이벤트에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-150">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
- <span data-ttu-id="79e80-151">이벤트 이름이 `SomeEvent`입니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-151">The event name is `SomeEvent`.</span></span>  
  
- <span data-ttu-id="79e80-152">이벤트는 `EventSource` 클래스에 의해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-152">The event is raised by the `EventSource` class.</span></span>  
  
- <span data-ttu-id="79e80-153">이벤트 처리기의 형식은 `SomeEventEventHandler` (`EventHandler<SomeEventEventArgs>`)입니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-153">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
- <span data-ttu-id="79e80-154">이벤트는 `SomeEventEventArgs` 형식의 매개 변수를 이벤트 처리기에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-154">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="79e80-155">기존 Weak 이벤트 관리자 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="79e80-155">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="79e80-156">기존 weak 이벤트 관리자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-156">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="79e80-157">WPF에 포함 된 weak 이벤트 관리자 목록은 <xref:System.Windows.WeakEventManager> 클래스에서 상속 계층 구조를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="79e80-157">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="79e80-158">일반적인 이벤트 후크 대신 새로운 weak 이벤트 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-158">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="79e80-159">예를 들어 코드에서 다음 패턴을 사용 하 여 이벤트를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-159">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="79e80-160">패턴을 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-160">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="79e80-161">마찬가지로 코드에서 다음 패턴을 사용 하 여 이벤트를 구독 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-161">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="79e80-162">패턴을 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-162">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="79e80-163">일반적인 약한 이벤트 관리자 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="79e80-163">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="79e80-164">일반적인 이벤트 후크 대신 일반 <xref:System.Windows.WeakEventManager%602> 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-164">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="79e80-165"><xref:System.Windows.WeakEventManager%602>를 사용 하 여 이벤트 수신기를 등록 하는 경우 다음 코드와 같이 클래스에 대 한 형식 매개 변수로 이벤트 소스 및 <xref:System.EventArgs> 형식을 제공 하 고 <xref:System.Windows.WeakEventManager%602.AddHandler%2A>를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-165">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```csharp  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="79e80-166">사용자 지정 Weak 이벤트 관리자 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="79e80-166">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="79e80-167">다음 클래스 템플릿을 프로젝트에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-167">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="79e80-168">이 클래스는 <xref:System.Windows.WeakEventManager> 클래스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-168">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="79e80-169">`SomeEventWeakEventManager` 이름을 자신의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-169">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="79e80-170">앞에서 설명한 세 개의 이름을 이벤트의 해당 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-170">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="79e80-171">(`SomeEvent`, `EventSource`및 `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="79e80-171">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="79e80-172">약한 이벤트 관리자 클래스의 표시 유형 (공개/내부/개인)을 관리 하는 이벤트와 동일한 표시 유형으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-172">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="79e80-173">일반적인 이벤트 후크 대신 새로운 weak 이벤트 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-173">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="79e80-174">예를 들어 코드에서 다음 패턴을 사용 하 여 이벤트를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-174">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="79e80-175">패턴을 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-175">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="79e80-176">마찬가지로 코드에서 다음 패턴을 사용 하 여 이벤트를 구독 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-176">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="79e80-177">패턴을 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="79e80-177">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="79e80-178">참조</span><span class="sxs-lookup"><span data-stu-id="79e80-178">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="79e80-179">라우트된 이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="79e80-179">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="79e80-180">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="79e80-180">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
