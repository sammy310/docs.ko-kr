---
title: 이벤트 기반 비동기 패턴 구현
description: .NET에서 EAP(이벤트 기반 비동기 패턴)를 구현하는 방법을 알아봅니다. EAP는 비동기 기능을 포함하는 클래스를 패키징하는 표준 방법입니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
ms.openlocfilehash: e36ae21e1e03c8c5c688b7446f660ab1bb666a94
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904379"
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="adb9c-104">이벤트 기반 비동기 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="adb9c-104">Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="adb9c-105">상당한 지연을 일으킬 수 있는 몇 가지 작업을 사용하여 클래스를 작성하는 경우 [이벤트 기반 비동기 패턴](event-based-asynchronous-pattern-overview.md)을 구현하여 비동기 기능을 부여하는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-105">If you are writing a class with some operations that may incur noticeable delays, consider giving it asynchronous functionality by implementing the [Event-based Asynchronous Pattern](event-based-asynchronous-pattern-overview.md).</span></span>

<span data-ttu-id="adb9c-106">이벤트 기반 비동기 패턴은 비동기 기능을 포함하는 클래스를 패키지하는 표준화된 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-106">The Event-based Asynchronous Pattern provides a standardized way to package a class that has asynchronous features.</span></span> <span data-ttu-id="adb9c-107"><xref:System.ComponentModel.AsyncOperationManager>와 같은 도우미 클래스를 구현한 경우 클래스는 ASP.NET, 콘솔 애플리케이션 및 Windows Forms 애플리케이션을 비롯한 모든 애플리케이션 모델에서 올바르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-107">If implemented with helper classes like <xref:System.ComponentModel.AsyncOperationManager>, your class will work correctly under any application model, including ASP.NET, Console applications, and Windows Forms applications.</span></span>

<span data-ttu-id="adb9c-108">이벤트 기반 비동기 패턴을 구현하는 예제는 [방법: 이벤트 기반 비동기 패턴을 지 원하는 구성 요소 구현](component-that-supports-the-event-based-asynchronous-pattern.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-108">For an example that implements the Event-based Asynchronous Pattern, see [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="adb9c-109">간단한 비동기 작업의 경우 <xref:System.ComponentModel.BackgroundWorker> 구성 요소가 적합하다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-109">For simple asynchronous operations, you may find the <xref:System.ComponentModel.BackgroundWorker> component suitable.</span></span> <span data-ttu-id="adb9c-110"><xref:System.ComponentModel.BackgroundWorker>에 대한 자세한 내용은 [방법: 백그라운드에서 작업 실행](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-110">For more information about <xref:System.ComponentModel.BackgroundWorker>, see [How to: Run an Operation in the Background](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>

<span data-ttu-id="adb9c-111">다음 목록에서는 이 항목에서 설명하는 이벤트 기반 비동기 패턴의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-111">The following list describes the features of the Event-based Asynchronous Pattern discussed in this topic.</span></span>

- <span data-ttu-id="adb9c-112">이벤트 기반 비동기 패턴 구현 기회</span><span class="sxs-lookup"><span data-stu-id="adb9c-112">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

- <span data-ttu-id="adb9c-113">비동기 메서드 명명</span><span class="sxs-lookup"><span data-stu-id="adb9c-113">Naming Asynchronous Methods</span></span>

- <span data-ttu-id="adb9c-114">선택적으로 취소 지원</span><span class="sxs-lookup"><span data-stu-id="adb9c-114">Optionally Support Cancellation</span></span>

- <span data-ttu-id="adb9c-115">선택적으로 IsBusy 속성 지원</span><span class="sxs-lookup"><span data-stu-id="adb9c-115">Optionally Support the IsBusy Property</span></span>

- <span data-ttu-id="adb9c-116">선택적으로 진행률 보고 지원 제공</span><span class="sxs-lookup"><span data-stu-id="adb9c-116">Optionally Provide Support for Progress Reporting</span></span>

- <span data-ttu-id="adb9c-117">선택적으로 증분 결과를 반환하기 위한 지원 제공</span><span class="sxs-lookup"><span data-stu-id="adb9c-117">Optionally Provide Support for Returning Incremental Results</span></span>

- <span data-ttu-id="adb9c-118">메서드의 Out 및 Ref 매개 변수 처리</span><span class="sxs-lookup"><span data-stu-id="adb9c-118">Handling Out and Ref Parameters in Methods</span></span>

## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="adb9c-119">이벤트 기반 비동기 패턴 구현 기회</span><span class="sxs-lookup"><span data-stu-id="adb9c-119">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="adb9c-120">다음과 같은 경우에 이벤트 기반 비동기 패턴의 구현을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-120">Consider implementing the Event-based Asynchronous Pattern when:</span></span>

- <span data-ttu-id="adb9c-121">클래스의 클라이언트에 비동기 작업에 사용할 수 있는 <xref:System.Threading.WaitHandle> 및 <xref:System.IAsyncResult> 개체가 필요하지 않습니다. 즉, 폴링 및 <xref:System.Threading.WaitHandle.WaitAll%2A> 또는 <xref:System.Threading.WaitHandle.WaitAny%2A>가 클라이언트에서 빌드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-121">Clients of your class do not need <xref:System.Threading.WaitHandle> and <xref:System.IAsyncResult> objects available for asynchronous operations, meaning that polling and <xref:System.Threading.WaitHandle.WaitAll%2A> or <xref:System.Threading.WaitHandle.WaitAny%2A> will need to be built up by the client.</span></span>

- <span data-ttu-id="adb9c-122">익숙한 이벤트/대리자 모델을 사용하여 클라이언트에서 비동기 작업이 관리되기를 원할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-122">You want asynchronous operations to be managed by the client with the familiar event/delegate model.</span></span>

<span data-ttu-id="adb9c-123">모든 작업은 비동기 구현의 후보가 될 수 있지만 긴 대기 시간을 발생시키는 작업을 비동기 방식으로 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-123">Any operation is a candidate for an asynchronous implementation, but those you expect to incur long latencies should be considered.</span></span> <span data-ttu-id="adb9c-124">클라이언트가 메서드를 호출하며 추가 개입 없이도 완료 시 알림이 제공되는 작업이 특히 적합할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-124">Especially appropriate are operations in which clients call a method and are notified on completion, with no further intervention required.</span></span> <span data-ttu-id="adb9c-125">또한 연속적으로 실행되고, 클라이언트에 주기적으로 진행 상황, 증분 결과 또는 상태 변경을 알리는 작업이 적합할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-125">Also appropriate are operations which run continuously, periodically notifying clients of progress, incremental results, or state changes.</span></span>

<span data-ttu-id="adb9c-126">이벤트 기반 비동기 패턴을 지원해야 하는 경우를 결정하는 방법에 대한 자세한 내용은 [이벤트 기반 비동기 패턴 구현 시기 결정](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-126">For more information on deciding when to support the Event-based Asynchronous Pattern, see [Deciding When to Implement the Event-based Asynchronous Pattern](deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="naming-asynchronous-methods"></a><span data-ttu-id="adb9c-127">비동기 메서드 명명</span><span class="sxs-lookup"><span data-stu-id="adb9c-127">Naming Asynchronous Methods</span></span>

<span data-ttu-id="adb9c-128">비동기 메서드를 제공하려는 각 동기 메서드 *MethodName*에 대해 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-128">For each synchronous method *MethodName* for which you want to provide an asynchronous counterpart:</span></span>

<span data-ttu-id="adb9c-129">다음 작업을 수행하는 _MethodName_**Async** 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-129">Define a _MethodName_**Async** method that:</span></span>

- <span data-ttu-id="adb9c-130">`void`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-130">Returns `void`.</span></span>

- <span data-ttu-id="adb9c-131">*MethodName* 메서드와 동일한 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-131">Takes the same parameters as the *MethodName* method.</span></span>

- <span data-ttu-id="adb9c-132">여러 호출을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-132">Accepts multiple invocations.</span></span>

<span data-ttu-id="adb9c-133">필요에 따라 _MethodName_**Async**와 동일하지만 `userState`라는 추가 개체 값 매개 변수가 있는 _MethodName_**Async** 오버로드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-133">Optionally define a _MethodName_**Async** overload, identical to _MethodName_**Async**, but with an additional object-valued parameter called `userState`.</span></span> <span data-ttu-id="adb9c-134">메서드의 여러 동시 호출을 관리할 준비가 되었으면 이 작업을 수행합니다. 그러면 메서드 호출을 구분하기 위해 모든 이벤트 처리기에 `userState` 값이 다시 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-134">Do this if you're prepared to manage multiple concurrent invocations of your method, in which case the `userState` value will be delivered back to all event handlers to distinguish invocations of the method.</span></span> <span data-ttu-id="adb9c-135">나중에 검색할 수 있게 사용자 상태를 저장하기 위한 장소로 이 작업을 수행하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-135">You may also choose to do this simply as a place to store user state for later retrieval.</span></span>

<span data-ttu-id="adb9c-136">별개의 각 _MethodName_**Async** 메서드 시그니처에 대해 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-136">For each separate _MethodName_**Async** method signature:</span></span>

1. <span data-ttu-id="adb9c-137">해당 메서드와 같은 클래스에서 다음 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-137">Define the following event in the same class as the method:</span></span>

    ```vb
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler
    ```

    ```csharp
    public event MethodNameCompletedEventHandler MethodNameCompleted;
    ```

2. <span data-ttu-id="adb9c-138">다음 대리자 및 <xref:System.ComponentModel.AsyncCompletedEventArgs>를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-138">Define the following delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span></span> <span data-ttu-id="adb9c-139">이러한 항목은 클래스 자체의 외부이면서 동일한 네임스페이스에서 정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-139">These will likely be defined outside of the class itself, but in the same namespace.</span></span>

    ```vb
    Public Delegate Sub MethodNameCompletedEventHandler( _
        ByVal sender As Object, _
        ByVal e As MethodNameCompletedEventArgs)

    Public Class MethodNameCompletedEventArgs
        Inherits System.ComponentModel.AsyncCompletedEventArgs
    Public ReadOnly Property Result() As MyReturnType
    End Property
    ```

    ```csharp
    public delegate void MethodNameCompletedEventHandler(object sender,
        MethodNameCompletedEventArgs e);

    public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs
    {
        public MyReturnType Result { get; }
    }
    ```

    - <span data-ttu-id="adb9c-140">필드에서는 데이터 바인딩이 불가능하므로 _MethodName_**CompletedEventArgs** 클래스가 해당 멤버를 필드가 아닌 읽기 전용 속성으로 노출하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-140">Ensure that the _MethodName_**CompletedEventArgs** class exposes its members as read-only properties, and not fields, as fields prevent data binding.</span></span>

    - <span data-ttu-id="adb9c-141">결과를 생성하지 않는 메서드에 대해서는 어떤 <xref:System.ComponentModel.AsyncCompletedEventArgs> 파생 클래스도 정의하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-141">Do not define any <xref:System.ComponentModel.AsyncCompletedEventArgs>-derived classes for methods that do not produce results.</span></span> <span data-ttu-id="adb9c-142"><xref:System.ComponentModel.AsyncCompletedEventArgs> 자체의 인스턴스를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-142">Simply use an instance of <xref:System.ComponentModel.AsyncCompletedEventArgs> itself.</span></span>

      > [!NOTE]
      > <span data-ttu-id="adb9c-143">적절한 경우 대리자 및 <xref:System.ComponentModel.AsyncCompletedEventArgs> 형식을 얼마든지 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-143">It is perfectly acceptable, when feasible and appropriate, to reuse delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> types.</span></span> <span data-ttu-id="adb9c-144">이 경우 지정된 대리자 및 <xref:System.ComponentModel.AsyncCompletedEventArgs>가 단일 메서드에 연결되지 않으므로 해당 명명 체계가 메서드 이름과 일치하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-144">In this case, the naming will not be as consistent with the method name, since a given delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> won't be tied to a single method.</span></span>

## <a name="optionally-support-cancellation"></a><span data-ttu-id="adb9c-145">선택적으로 취소 지원</span><span class="sxs-lookup"><span data-stu-id="adb9c-145">Optionally Support Cancellation</span></span>

<span data-ttu-id="adb9c-146">클래스가 비동기 작업 취소를 지원하는 경우 아래 설명된 대로 취소가 클라이언트에 노출되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-146">If your class will support canceling asynchronous operations, cancellation should be exposed to the client as described below.</span></span> <span data-ttu-id="adb9c-147">취소 지원을 정의하기 전에 도달해야 하는 두 가지 의사 결정 지점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-147">Note that there are two decision points that need to be reached before defining your cancellation support:</span></span>

- <span data-ttu-id="adb9c-148">예상되는 추가 항목을 포함하여 클래스에 취소를 지원하는 비동기 작업이 하나만 포함되나요?</span><span class="sxs-lookup"><span data-stu-id="adb9c-148">Does your class, including future anticipated additions to it, have only one asynchronous operation that supports cancellation?</span></span>

- <span data-ttu-id="adb9c-149">취소를 지원하는 비동기 작업이 보류 중인 여러 작업을 취소할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="adb9c-149">Can the asynchronous operations that support cancellation support multiple pending operations?</span></span> <span data-ttu-id="adb9c-150">즉, _MethodName_**Async** 메서드가 `userState` 매개 변수를 사용하며 하나의 호출이 끝나기를 기다리지 않고 여러 번 호출할 수 있도록 허용하나요?</span><span class="sxs-lookup"><span data-stu-id="adb9c-150">That is, does the _MethodName_**Async** method take a `userState` parameter, and does it allow multiple invocations before waiting for any to finish?</span></span>

<span data-ttu-id="adb9c-151">아래 표에 나오는 이러한 두 가지 질문에 대한 답변을 사용하여 취소 메서드의 시그니처를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-151">Use the answers to these two questions in the table below to determine what the signature for your cancellation method should be.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="adb9c-152">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="adb9c-152">Visual Basic</span></span>

||<span data-ttu-id="adb9c-153">다중 동시 작업 지원</span><span class="sxs-lookup"><span data-stu-id="adb9c-153">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="adb9c-154">한 번에 하나의 작업</span><span class="sxs-lookup"><span data-stu-id="adb9c-154">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="adb9c-155">전체 클래스에서 단일 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="adb9c-155">One Async Operation in entire class</span></span>|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|
|<span data-ttu-id="adb9c-156">클래스의 여러 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="adb9c-156">Multiple Async Operations in class</span></span>|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|

### <a name="c"></a><span data-ttu-id="adb9c-157">C\#</span><span class="sxs-lookup"><span data-stu-id="adb9c-157">C\#</span></span>

||<span data-ttu-id="adb9c-158">다중 동시 작업 지원</span><span class="sxs-lookup"><span data-stu-id="adb9c-158">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="adb9c-159">한 번에 하나의 작업</span><span class="sxs-lookup"><span data-stu-id="adb9c-159">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="adb9c-160">전체 클래스에서 단일 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="adb9c-160">One Async Operation in entire class</span></span>|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|
|<span data-ttu-id="adb9c-161">클래스의 여러 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="adb9c-161">Multiple Async Operations in class</span></span>|`void CancelAsync(object userState);`|`void CancelAsync();`|

<span data-ttu-id="adb9c-162">`CancelAsync(object userState)` 메서드를 정의하는 경우 클라이언트는 단일 비동기 메서드의 모든 호출 간에서 뿐만 아니라 개체에 대해 호출된 모든 비동기 메서드 간을 구분할 수 있도록 하는 상태 값을 선택할 때 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-162">If you define the `CancelAsync(object userState)` method, clients must be careful when choosing their state values to make them capable of distinguishing among all asynchronous methods invoked on the object, and not just between all invocations of a single asynchronous method.</span></span>

<span data-ttu-id="adb9c-163">Visual Studio의 IntelliSense와 같은 디자인 환경에서 메서드를 보다 쉽게 검색할 수 있도록 하기 위해 단일 비동기 작업 버전을 _MethodName_**AsyncCancel**로 명명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-163">The decision to name the single-async-operation version _MethodName_**AsyncCancel** is based on being able to more easily discover the method in a design environment like Visual Studio's IntelliSense.</span></span> <span data-ttu-id="adb9c-164">이렇게 하면 관련된 멤버가 그룹화되고 비동기 기능과 관련이 없는 다른 멤버에서 구분될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-164">This groups the related members and distinguishes them from other members that have nothing to do with asynchronous functionality.</span></span> <span data-ttu-id="adb9c-165">후속 버전에 추가되는 비동기 작업이 있을 수 있다고 예상될 경우 `CancelAsync`를 정의하는 것이 더 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-165">If you expect that there may be additional asynchronous operations added in subsequent versions, it is better to define `CancelAsync`.</span></span>

<span data-ttu-id="adb9c-166">위 표의 여러 메서드를 같은 클래스에는 정의하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-166">Do not define multiple methods from the table above in the same class.</span></span> <span data-ttu-id="adb9c-167">그렇게 하는 것은 의미가 없으며 메서드가 증가하면 클래스 인터페이스만 복잡해집니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-167">That will not make sense, or it will clutter the class interface with a proliferation of methods.</span></span>

<span data-ttu-id="adb9c-168">이러한 메서드는 일반적으로 즉시 반환되며 작업이 실제로 취소될 수도 있고 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-168">These methods typically will return immediately, and the operation may or may not actually cancel.</span></span> <span data-ttu-id="adb9c-169">_MethodName_**Completed** 이벤트에 대한 이벤트 처리기에서 _MethodName_**CompletedEventArgs** 개체는 클라이언트가 취소 발생 여부를 확인하는 데 사용할 수 있는 `Cancelled` 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-169">In the event handler for the _MethodName_**Completed** event, the _MethodName_**CompletedEventArgs** object contains a `Cancelled` field, which clients can use to determine whether the cancellation occurred.</span></span>

<span data-ttu-id="adb9c-170">[최선의 이벤트 기반 비동기 패턴 구현 방법](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)에 설명된 취소 의미 체계를 준수하세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-170">Abide by the cancellation semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-support-the-isbusy-property"></a><span data-ttu-id="adb9c-171">선택적으로 IsBusy 속성 지원</span><span class="sxs-lookup"><span data-stu-id="adb9c-171">Optionally Support the IsBusy Property</span></span>

<span data-ttu-id="adb9c-172">클래스가 여러 동시 호출을 지원하지 않으면 `IsBusy` 속성 노출을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-172">If your class does not support multiple concurrent invocations, consider exposing an `IsBusy` property.</span></span> <span data-ttu-id="adb9c-173">이 방법을 사용하면 개발자들은 _MethodName_**Async** 메서드에서 예외를 catch하지 않고도 _MethodName_**Async** 메서드가 실행 중인지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-173">This allows developers to determine whether a _MethodName_**Async** method is running without catching an exception from the _MethodName_**Async** method.</span></span>

<span data-ttu-id="adb9c-174">[최선의 이벤트 기반 비동기 패턴 구현 방법](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)에 설명된 `IsBusy` 의미 체계를 준수하세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-174">Abide by the `IsBusy` semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-progress-reporting"></a><span data-ttu-id="adb9c-175">선택적으로 진행률 보고 지원 제공</span><span class="sxs-lookup"><span data-stu-id="adb9c-175">Optionally Provide Support for Progress Reporting</span></span>

<span data-ttu-id="adb9c-176">일반적으로 비동기 작업이 작업 중에 진행률을 보고하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-176">It is frequently desirable for an asynchronous operation to report progress during its operation.</span></span> <span data-ttu-id="adb9c-177">이벤트 기반 비동기 패턴은 이러한 작업에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-177">The Event-based Asynchronous Pattern provides a guideline for doing so.</span></span>

- <span data-ttu-id="adb9c-178">필요에 따라 비동기 작업에서 발생되고 적절한 스레드에 대해 호출될 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-178">Optionally define an event to be raised by the asynchronous operation and invoked on the appropriate thread.</span></span> <span data-ttu-id="adb9c-179"><xref:System.ComponentModel.ProgressChangedEventArgs> 개체는 0에서 100 사이여야 하는 정수 값 진행률 표시기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-179">The <xref:System.ComponentModel.ProgressChangedEventArgs> object carries an integer-valued progress indicator that is expected to be between 0 and 100.</span></span>

- <span data-ttu-id="adb9c-180">다음과 같이 이벤트에 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-180">Name this event as follows:</span></span>

  - <span data-ttu-id="adb9c-181">`ProgressChanged`: 클래스에 비동기 작업이 여러 개 있는 경우(또는 이후 버전에서 여러 비동기 작업을 포함하도록 확장될 예정임)</span><span class="sxs-lookup"><span data-stu-id="adb9c-181">`ProgressChanged` if the class has multiple asynchronous operations (or is expected to grow to include multiple asynchronous operations in future versions);</span></span>

  - <span data-ttu-id="adb9c-182">_MethodName_**ProgressChanged**: 클래스에 비동기 작업이 하나만 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="adb9c-182">_MethodName_**ProgressChanged** if the class has a single asynchronous operation.</span></span>

  <span data-ttu-id="adb9c-183">이 명명 옵션은 선택적으로 취소 지원 섹션에 설명된 대로 취소 메서드의 경우와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-183">This naming choice parallels that made for the cancellation method, as described in the Optionally Support Cancellation section.</span></span>

<span data-ttu-id="adb9c-184">이 이벤트는 <xref:System.ComponentModel.ProgressChangedEventHandler> 대리자 시그니처와 <xref:System.ComponentModel.ProgressChangedEventArgs> 클래스를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-184">This event should use the <xref:System.ComponentModel.ProgressChangedEventHandler> delegate signature and the <xref:System.ComponentModel.ProgressChangedEventArgs> class.</span></span> <span data-ttu-id="adb9c-185">또는 추가 도메인 관련 진행률 표시기를 제공할 수 있는 경우(예를 들어 다운로드 작업에 대해 읽은 바이트 수 및 총 바이트 수) <xref:System.ComponentModel.ProgressChangedEventArgs>의 파생 클래스를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-185">Alternatively, if a more domain-specific progress indicator can be provided (for instance, bytes read and total bytes for a download operation), then you should define a derived class of <xref:System.ComponentModel.ProgressChangedEventArgs>.</span></span>

<span data-ttu-id="adb9c-186">클래스가 지원하는 비동기 메서드의 수와 관계없이 해당 클래스에 대한 `ProgressChanged` or _MethodName_**ProgressChanged** 이벤트는 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-186">Note that there is only one `ProgressChanged` or _MethodName_**ProgressChanged** event for the class, regardless of the number of asynchronous methods it supports.</span></span> <span data-ttu-id="adb9c-187">클라이언트는 여러 동시 작업에 대한 진행률 업데이트 내용을 구분하기 위해 _MethodName_**Async** 메서드에 전달되는 `userState` 개체를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-187">Clients are expected to use the `userState` object that is passed to the _MethodName_**Async** methods to distinguish among progress updates on multiple concurrent operations.</span></span>

<span data-ttu-id="adb9c-188">여러 작업이 진행률을 지원하고 각각이 다른 진행률 표시기를 반환하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-188">There may be situations in which multiple operations support progress and each returns a different indicator for progress.</span></span> <span data-ttu-id="adb9c-189">이 경우 단일 `ProgressChanged` 이벤트로는 적절하지 않으며 여러 `ProgressChanged` 이벤트를 지원하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-189">In this case, a single `ProgressChanged` event is not appropriate, and you may consider supporting multiple `ProgressChanged` events.</span></span> <span data-ttu-id="adb9c-190">이 경우 각 _MethodName_**Async** 메서드에 대해 _MethodName_**ProgressChanged** 명명 패턴을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-190">In this case use a naming pattern of _MethodName_**ProgressChanged** for each _MethodName_**Async** method.</span></span>

<span data-ttu-id="adb9c-191">[최선의 이벤트 기반 비동기 패턴 구현 방법](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)에 설명된 진행률 보고 의미 체계를 준수하세요.</span><span class="sxs-lookup"><span data-stu-id="adb9c-191">Abide by the progress-reporting semantics described [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-returning-incremental-results"></a><span data-ttu-id="adb9c-192">선택적으로 증분 결과를 반환하기 위한 지원 제공</span><span class="sxs-lookup"><span data-stu-id="adb9c-192">Optionally Provide Support for Returning Incremental Results</span></span>

<span data-ttu-id="adb9c-193">경우에 따라 비동기 작업이 완료되기 전에 증분 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-193">Sometimes an asynchronous operation can return incremental results prior to completion.</span></span> <span data-ttu-id="adb9c-194">이 시나리오를 지원하는 데 사용할 수 있는 옵션에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-194">There are a number of options that can be used to support this scenario.</span></span> <span data-ttu-id="adb9c-195">몇 가지 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-195">Some examples follow.</span></span>

### <a name="single-operation-class"></a><span data-ttu-id="adb9c-196">단일 작업 클래스</span><span class="sxs-lookup"><span data-stu-id="adb9c-196">Single-operation Class</span></span>

<span data-ttu-id="adb9c-197">클래스가 단일 비동기 작업만 지원하며 해당 작업이 증분 결과를 반환할 수 있으면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-197">If your class only supports a single asynchronous operation, and that operation is able to return incremental results, then:</span></span>

- <span data-ttu-id="adb9c-198">증분 결과 데이터를 전달하도록 <xref:System.ComponentModel.ProgressChangedEventArgs> 형식을 확장하고 확장된 데이터로 _MethodName_**ProgressChanged** 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-198">Extend the <xref:System.ComponentModel.ProgressChangedEventArgs> type to carry the incremental result data, and define a _MethodName_**ProgressChanged** event with this extended data.</span></span>

- <span data-ttu-id="adb9c-199">보고할 증분 결과가 있을 때 이 _MethodName_**ProgressChanged** 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-199">Raise this _MethodName_**ProgressChanged** event when there is an incremental result to report.</span></span>

<span data-ttu-id="adb9c-200">이 솔루션은 _MethodName_**ProgressChanged** 이벤트처럼 “모든 작업”에 대한 증분 결과를 반환하기 위해 동일한 이벤트가 발생하는 문제가 없으므로 단일 비동기 작업 클래스에 특수하게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-200">This solution applies specifically to a single-async-operation class because there is no problem with the same event occurring to return incremental results on "all operations", as the _MethodName_**ProgressChanged** event does.</span></span>

### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a><span data-ttu-id="adb9c-201">유형이 같은 증분 결과를 갖는 다중 작업 클래스</span><span class="sxs-lookup"><span data-stu-id="adb9c-201">Multiple-operation Class with Homogeneous Incremental Results</span></span>

<span data-ttu-id="adb9c-202">이 경우 클래스는 각각이 증분 결과를 반환할 수 있는 여러 비동기 메서드를 지원하며 이러한 모든 증분 결과가 모두 동일한 형식의 데이터를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-202">In this case, your class supports multiple asynchronous methods, each capable of returning incremental results, and these incremental results all have the same type of data.</span></span>

<span data-ttu-id="adb9c-203">모든 증분 결과에 동일한 <xref:System.EventArgs> 구조체가 작동하므로 단일 작업 클래스에 대해 위에서 설명된 모델을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-203">Follow the model described above for single-operation classes, as the same <xref:System.EventArgs> structure will work for all incremental results.</span></span> <span data-ttu-id="adb9c-204">_MethodName_**ProgressChanged** 이벤트 대신 다중 비동기 메서드에 적용되는 `ProgressChanged` 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-204">Define a `ProgressChanged` event instead of a _MethodName_**ProgressChanged** event, since it applies to multiple asynchronous methods.</span></span>

### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a><span data-ttu-id="adb9c-205">유형이 다른 증분 결과를 갖는 다중 작업 클래스</span><span class="sxs-lookup"><span data-stu-id="adb9c-205">Multiple-operation Class with Heterogeneous Incremental Results</span></span>

<span data-ttu-id="adb9c-206">클래스가 각각이 다른 데이터 형식을 반환하는 여러 비동기 메서드를 지원하는 경우 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-206">If your class supports multiple asynchronous methods, each returning a different type of data, you should:</span></span>

- <span data-ttu-id="adb9c-207">진행률 보고에서 증분 결과 보고를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-207">Separate your incremental result reporting from your progress reporting.</span></span>

- <span data-ttu-id="adb9c-208">각 비동기 메서드가 해당 메서드의 증분 결과 데이터를 처리할 수 있도록 적절한 <xref:System.EventArgs>를 사용하여 별도의 _MethodName_**ProgressChanged** 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-208">Define a separate _MethodName_**ProgressChanged** event with appropriate <xref:System.EventArgs> for each asynchronous method to handle that method's incremental result data.</span></span>

<span data-ttu-id="adb9c-209">[최선의 이벤트 기반 비동기 패턴 구현 방법](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)에 설명된 대로 적절한 스레드에서 해당 이벤트 처리기를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-209">Invoke that event handler on the appropriate thread as described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="handling-out-and-ref-parameters-in-methods"></a><span data-ttu-id="adb9c-210">메서드의 Out 및 Ref 매개 변수 처리</span><span class="sxs-lookup"><span data-stu-id="adb9c-210">Handling Out and Ref Parameters in Methods</span></span>

<span data-ttu-id="adb9c-211">일반적으로 `out` 및 `ref`의 사용이 .NET Framework에서는 권장되지 않지만 이러한 매개 변수가 있을 때 따라야 하는 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-211">Although the use of `out` and `ref` is, in general, discouraged in the .NET Framework, here are the rules to follow when they are present:</span></span>

<span data-ttu-id="adb9c-212">동기 메서드를 *MethodName*으로 명명한 경우:</span><span class="sxs-lookup"><span data-stu-id="adb9c-212">Given a synchronous method *MethodName*:</span></span>

- <span data-ttu-id="adb9c-213">*MethodName*에 대한 `out` 매개 변수는 _MethodName_**Async**에 속하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-213">`out` parameters to *MethodName* should not be part of _MethodName_**Async**.</span></span> <span data-ttu-id="adb9c-214">좀 더 적절한 이름이 없는 경우 *MethodName*의 동일한 매개 변수와 이름이 같은 _MethodName_**CompletedEventArgs**에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-214">Instead, they should be part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

- <span data-ttu-id="adb9c-215">*MethodName*에 대한 `ref` 매개 변수가 _MethodName_**Async**에 속해야 하고 좀 더 적절한 이름이 없는 경우 *MethodName*의 동일한 매개 변수와 이름이 같은 _MethodName_**CompletedEventArgs**에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-215">`ref` parameters to *MethodName* should appear as part of _MethodName_**Async**, and as part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

<span data-ttu-id="adb9c-216">예를 들어 다음이 지정될 경우</span><span class="sxs-lookup"><span data-stu-id="adb9c-216">For example, given:</span></span>

```vb
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer
```

```csharp
public int MethodName(string arg1, ref string arg2, out string arg3);
```

<span data-ttu-id="adb9c-217">비동기 메서드 및 해당 <xref:System.ComponentModel.AsyncCompletedEventArgs> 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="adb9c-217">Your asynchronous method and its <xref:System.ComponentModel.AsyncCompletedEventArgs> class would look like this:</span></span>

```vb
Public Sub MethodNameAsync(ByVal arg1 As String, ByVal arg2 As String)

Public Class MethodNameCompletedEventArgs
    Inherits System.ComponentModel.AsyncCompletedEventArgs
    Public ReadOnly Property Result() As Integer
    End Property
    Public ReadOnly Property Arg2() As String
    End Property
    Public ReadOnly Property Arg3() As String
    End Property
End Class
```

```csharp
public void MethodNameAsync(string arg1, string arg2);

public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs
{
    public int Result { get; };
    public string Arg2 { get; };
    public string Arg3 { get; };
}
```

## <a name="see-also"></a><span data-ttu-id="adb9c-218">참조</span><span class="sxs-lookup"><span data-stu-id="adb9c-218">See also</span></span>

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [<span data-ttu-id="adb9c-219">방법: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현</span><span class="sxs-lookup"><span data-stu-id="adb9c-219">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="adb9c-220">방법: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="adb9c-220">How to: Run an Operation in the Background</span></span>](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="adb9c-221">방법: 백그라운드 작업을 사용하는 양식 구현</span><span class="sxs-lookup"><span data-stu-id="adb9c-221">How to: Implement a Form That Uses a Background Operation</span></span>](../../framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="adb9c-222">이벤트 기반 비동기 패턴 구현 시기 결정</span><span class="sxs-lookup"><span data-stu-id="adb9c-222">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="adb9c-223">최선의 이벤트 기반 비동기 패턴 구현 방법</span><span class="sxs-lookup"><span data-stu-id="adb9c-223">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="adb9c-224">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="adb9c-224">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
