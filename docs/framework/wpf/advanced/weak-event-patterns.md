---
title: 약한 이벤트 패턴
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 61e7f6d29cf9275004238ca776d5af9bf027004f
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859912"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="5ca71-102">약한 이벤트 패턴</span><span class="sxs-lookup"><span data-stu-id="5ca71-102">Weak Event Patterns</span></span>
<span data-ttu-id="5ca71-103">응용 프로그램에서 있기 이벤트 소스에 연결 된 처리기를 조정 하 여 원본에 처리기를 연결 하는 수신기 개체를 사용 하 여 소멸 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="5ca71-104">이 경우 메모리 누수가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="5ca71-105">특정 이벤트에 대 한 전용된 관리자 클래스를 제공 하 고 해당 이벤트에 대 한 수신기에서 인터페이스를 구현 하 여이 문제를 해결 하기 위해 사용할 수 있는 디자인 패턴을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-105">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="5ca71-106">이 디자인 패턴 이라고 합니다 *약한 이벤트 패턴*합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="5ca71-107">약한 이벤트 패턴을 구현 하는 이유</span><span class="sxs-lookup"><span data-stu-id="5ca71-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="5ca71-108">이벤트를 수신 대기 메모리 누수가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="5ca71-109">이벤트를 수신 하는 일반적인 방법은 원본에서 이벤트 처리기를 연결 하는 언어별 구문을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="5ca71-110">예를 들어, C#에 구문은: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="5ca71-111">이 기술은 이벤트 수신기에 이벤트 원본에서 강력한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="5ca71-112">일반적으로 수신기에 대 한 이벤트 처리기를 연결 하면 해당 수신기 개체 수명이 원본의 개체 수명에 영향을 받습니다 (하지 않는 한 이벤트 처리기가 명시적으로 제거)입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="5ca71-113">하지만 속해 있는지 여부 현재 응용 프로그램 및 원본의 수명을가 아닌 시각적 트리 같은 개체 수명의 수신기에 대 한 다른 요인에 의해 제어 하려는 경우에 따라 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="5ca71-114">일반적인 이벤트 패턴 메모리 누수를 발생 시키는 소스 개체 수명을 수신기의 개체 수명을 넘어가는, 때마다: 수신기 것 보다 더 이상 활성 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="5ca71-115">약한 이벤트 패턴에는이 메모리 누수 문제를 해결 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="5ca71-116">수신기가 이벤트를 등록 해야 하지만 수신기를 명시적으로 알지 등록을 취소 하는 경우 때마다 약한 이벤트 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="5ca71-117">수신기의 유용한 개체 수명을 초과 하는 원본의 개체 수명을 때마다 약한 이벤트 패턴에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="5ca71-118">(이 예에서 *유용* 사용자에 의해 결정 됩니다.) 약한 이벤트 패턴에 수신기를를 등록 하 고 어떤 방식으로든에서 수신기의 개체 수명 특성을 영향을 주지 않고 이벤트를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="5ca71-119">실제로 소스에서 대 한 암시적된 참조가 수신기가 가비지 수집 대상이 있는지을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="5ca71-120">참조가 있으므로 명명 약한 이벤트 패턴 및 관련된 Api의 약한 참조가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-120">The reference is a weak reference, thus the naming of the weak event pattern and the related APIs.</span></span> <span data-ttu-id="5ca71-121">수신기 가비지 수집 또는 그렇지 않은 경우 제거 되며 원본 존재할 삭제 된 개체에 대 한 처리기 참조를 유지 하지 않고 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="5ca71-122">약한 이벤트 패턴을 구현 해야 하는</span><span class="sxs-lookup"><span data-stu-id="5ca71-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="5ca71-123">약한 이벤트 패턴을 구현 하는 것은 주로 컨트롤 작성자를 위한 흥미로운 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="5ca71-124">컨트롤 작성자 담당 주로 동작을 컨트롤에서 삽입 되는 응용 프로그램에 영향을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="5ca71-125">여기에 컨트롤 개체 수명 동작, 특히 설명한 메모리 누수 문제를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="5ca71-126">특정 시나리오 기본적으로 자체적으로 약한 이벤트 패턴을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="5ca71-127">이러한 시나리오 중 하나는 데이터 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-127">One such scenario is data binding.</span></span> <span data-ttu-id="5ca71-128">이 데이터 바인딩에서 바인딩 대상 수신기 개체를 완전히 독립 소스 개체에 대 한 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="5ca71-129">여러 가지 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 약한 이벤트 패턴의 이벤트 구현 방식에서 적용 한 데이터 바인딩이 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="5ca71-130">약한 이벤트 패턴을 구현 하는 방법</span><span class="sxs-lookup"><span data-stu-id="5ca71-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="5ca71-131">약한 이벤트 패턴을 구현 하는 방법은 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="5ca71-132">다음 표에서 세 가지 방법을 나열 하 고 각 사용 시기에 대 한 몇 가지 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="5ca71-133">접근 방식</span><span class="sxs-lookup"><span data-stu-id="5ca71-133">Approach</span></span>|<span data-ttu-id="5ca71-134">구현 하는 경우</span><span class="sxs-lookup"><span data-stu-id="5ca71-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="5ca71-135">기존 강력 하지 않은 이벤트 관리자 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="5ca71-136">구독 하려는 이벤트에 해당 하는 경우 <xref:System.Windows.WeakEventManager>, 기존 강력 하지 않은 이벤트 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="5ca71-137">WPF와 함께 제공 되는 약한 이벤트 관리자의 목록, 참조의 상속 계층 구조는 <xref:System.Windows.WeakEventManager> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="5ca71-138">포함 된 약한 이벤트 관리자 제한 되므로, 아마도 다른 방법 중 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-138">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="5ca71-139">제네릭 약한 이벤트 관리자 클래스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="5ca71-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="5ca71-140">제네릭 사용 <xref:System.Windows.WeakEventManager%602> 기존 <xref:System.Windows.WeakEventManager> 를 사용할 수 없는 구현 하는 간편한 방법은 원하는 및 없는 관련이 효율성에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="5ca71-141">제네릭 <xref:System.Windows.WeakEventManager%602> 약한 이벤트 관리자를 기존 또는 사용자 지정 보다 덜 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="5ca71-142">예를 들어, 제네릭 클래스는 이벤트의 이름이 지정 된 이벤트를 검색 하기 위해 자세한 리플렉션을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="5ca71-143">제네릭 사용 하 여 이벤트를 등록 하는 코드 또한 <xref:System.Windows.WeakEventManager%602> 더 기존를 사용 하 여 보다 자세한 정보 또는 사용자 지정 <xref:System.Windows.WeakEventManager>합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="5ca71-144">사용자 지정 약한 이벤트 관리자 클래스를 만듭니다</span><span class="sxs-lookup"><span data-stu-id="5ca71-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="5ca71-145">사용자 지정 만들기 <xref:System.Windows.WeakEventManager> 기존 <xref:System.Windows.WeakEventManager> 사용할 수 없는 효율성을 극대화 하려는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="5ca71-146">사용자 지정을 사용 하 여 <xref:System.Windows.WeakEventManager> 구독할 이벤트 보다 효율적 이지만 시작 부분에 더 많은 코드를 작성 하는 비용이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="5ca71-147">타사 약한 이벤트 관리자를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="5ca71-147">Use a third-party weak event manager</span></span>|<span data-ttu-id="5ca71-148">NuGet은 [여러 약한 이벤트 관리자](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) 많은 WPF 프레임 워크는 또한 패턴을 지원 하 고 (예를 들어 참조 [느슨하게 연결 된 이벤트 구독에 대 한 Prism의 설명서](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span><span class="sxs-lookup"><span data-stu-id="5ca71-148">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="5ca71-149">다음 섹션에서는 약한 이벤트 패턴을 구현 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-149">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="5ca71-150">이 토론을 위해 이벤트를 구독할 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-150">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
- <span data-ttu-id="5ca71-151">이벤트 이름은 `SomeEvent`합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-151">The event name is `SomeEvent`.</span></span>  
  
- <span data-ttu-id="5ca71-152">이벤트가 발생 합니다 `EventSource` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-152">The event is raised by the `EventSource` class.</span></span>  
  
- <span data-ttu-id="5ca71-153">이벤트 처리기의 형식: `SomeEventEventHandler` (또는 `EventHandler<SomeEventEventArgs>`).</span><span class="sxs-lookup"><span data-stu-id="5ca71-153">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
- <span data-ttu-id="5ca71-154">형식의 매개 변수를 전달 하는 이벤트 `SomeEventEventArgs` 이벤트 처리기에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-154">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="5ca71-155">기존 강력 하지 않은 이벤트 관리자 클래스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="5ca71-155">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="5ca71-156">관리자를 기존 약한 이벤트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-156">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="5ca71-157">WPF와 함께 제공 되는 약한 이벤트 관리자의 목록, 참조의 상속 계층 구조는 <xref:System.Windows.WeakEventManager> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-157">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="5ca71-158">일반 이벤트를 후크 하는 대신 새로운 약한 이벤트 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-158">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="5ca71-159">예를 들어 다음과 같이 코드 패턴을 사용 하 여 이벤트를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-159">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="5ca71-160">다음 패턴으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-160">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="5ca71-161">마찬가지로 코드에서 이벤트를 구독 취소 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-161">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="5ca71-162">다음 패턴으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-162">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="5ca71-163">제네릭 약한 이벤트 관리자 클래스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="5ca71-163">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="5ca71-164">제네릭 사용 <xref:System.Windows.WeakEventManager%602> 일반 이벤트를 후크 하는 대신 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-164">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="5ca71-165">사용 하는 경우 <xref:System.Windows.WeakEventManager%602> 이벤트 수신기를 등록 이벤트 소스를 제공 하 고 <xref:System.EventArgs> 클래스 및 호출 형식 매개 변수 형식과 <xref:System.Windows.WeakEventManager%602.AddHandler%2A> 다음 코드 에서처럼:</span><span class="sxs-lookup"><span data-stu-id="5ca71-165">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="5ca71-166">약한 이벤트 관리자 클래스를 사용자 지정 만들기</span><span class="sxs-lookup"><span data-stu-id="5ca71-166">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="5ca71-167">다음 클래스 템플릿을 프로젝트에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-167">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="5ca71-168">이 클래스에서 상속 된 <xref:System.Windows.WeakEventManager> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-168">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="5ca71-169">대체는 `SomeEventWeakEventManager` 고유한 이름의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-169">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="5ca71-170">이벤트에 대 한 해당 이름의 앞에서 설명한 3 개의 이름을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-170">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="5ca71-171">(`SomeEvent`하십시오 `EventSource`, 및 `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="5ca71-171">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="5ca71-172">관리 이벤트로 동일한 표시 약한 이벤트 관리자 클래스의 표시 여부 (공개 / 개인, 내부)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-172">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="5ca71-173">일반 이벤트를 후크 하는 대신 새로운 약한 이벤트 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-173">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="5ca71-174">예를 들어 다음과 같이 코드 패턴을 사용 하 여 이벤트를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-174">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="5ca71-175">다음 패턴으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-175">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="5ca71-176">마찬가지로 코드에서 이벤트를 구독 취소 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-176">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="5ca71-177">다음 패턴으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca71-177">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5ca71-178">참고자료</span><span class="sxs-lookup"><span data-stu-id="5ca71-178">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="5ca71-179">라우트된 이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="5ca71-179">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="5ca71-180">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="5ca71-180">Data Binding Overview</span></span>](../data/data-binding-overview.md)
