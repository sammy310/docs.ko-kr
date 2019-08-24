---
title: 사용자 지정 수명
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: be6013d568e3625c5eac7e0c145db7df1c6917e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003165"
---
# <a name="custom-lifetime"></a><span data-ttu-id="8e5e9-102">사용자 지정 수명</span><span class="sxs-lookup"><span data-stu-id="8e5e9-102">Custom lifetime</span></span>

<span data-ttu-id="8e5e9-103">이 샘플에는 공유 WCF 서비스 인스턴스에 대 한 사용자 지정 수명 서비스를 제공 하는 Windows Communication Foundation (WCF) 확장을 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-103">This sample demonstrates how to write a Windows Communication Foundation (WCF) extension to provide custom lifetime services for shared WCF service instances.</span></span>

> [!NOTE]
> <span data-ttu-id="8e5e9-104">이 샘플의 설치 절차 및 빌드 지침은 이 문서의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>

## <a name="shared-instancing"></a><span data-ttu-id="8e5e9-105">공유 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="8e5e9-105">Shared instancing</span></span>

<span data-ttu-id="8e5e9-106">WCF는 서비스 인스턴스에 대 한 여러 인스턴스 만들기 모드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-106">WCF offers several instancing modes for your service instances.</span></span> <span data-ttu-id="8e5e9-107">이 문서에서 다루는 공유 인스턴스 만들기 모드에는 여러 채널 간에 서비스 인스턴스를 공유 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-107">The shared instancing mode covered in this article provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="8e5e9-108">클라이언트는 서비스의 팩터리 메서드에 연결 하 고 통신을 시작 하려면 새 채널을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-108">Clients can contact a factory method in the service and create a new channel to start communication.</span></span> <span data-ttu-id="8e5e9-109">다음 코드 조각에서는 클라이언트 응용 프로그램에서 기존 서비스 인스턴스에 새 채널을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-109">The following code snippet shows how a client application creates a new channel to an existing service instance:</span></span>

```csharp
// Create a header for the shared instance id
MessageHeader shareableInstanceContextHeader = MessageHeader.CreateHeader(
        CustomHeader.HeaderName,
        CustomHeader.HeaderNamespace,
        Guid.NewGuid().ToString());

// Create the channel factory
ChannelFactory<IEchoService> channelFactory =
    new ChannelFactory<IEchoService>("echoservice");

// Create the first channel
IEchoService proxy = channelFactory.CreateChannel();

// Call an operation to create shared service instance
using (new OperationContextScope((IClientChannel)proxy))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy.Echo("Apple"));
}

((IChannel)proxy).Close();

// Create the second channel
IEchoService proxy2 = channelFactory.CreateChannel();

// Call an operation using the same header that will reuse the shared service instance
using (new OperationContextScope((IClientChannel)proxy2))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy2.Echo("Apple"));
}
```

<span data-ttu-id="8e5e9-110">다른 인스턴스 만들기 모드와 달리 공유 인스턴스 만들기 모드에는 서비스 인스턴스를 해제하는 고유한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-110">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="8e5e9-111">에 대 한 채널을 닫을 때 기본적으로는 <xref:System.ServiceModel.InstanceContext>, WCF 서비스 런타임 있는지 확인 합니다 서비스 <xref:System.ServiceModel.InstanceContextMode> 하도록 구성 된 <xref:System.ServiceModel.InstanceContextMode.PerCall> 또는 <xref:System.ServiceModel.InstanceContextMode.PerSession>, 경우에 따라서 인스턴스를 해제 하 고 리소스를 클레임 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-111">By default, when all the channels are closed for an <xref:System.ServiceModel.InstanceContext>, the WCF service runtime checks to see if the service <xref:System.ServiceModel.InstanceContextMode> is configured to <xref:System.ServiceModel.InstanceContextMode.PerCall> or <xref:System.ServiceModel.InstanceContextMode.PerSession>, and if so releases the instance and claims the resources.</span></span> <span data-ttu-id="8e5e9-112">사용자 지정 하는 경우 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 는 WCF를 호출 하는 데 사용 되는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 인스턴스를 해제 하기 전에 공급자 구현의 메서드.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-112">If a custom <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is being used, WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the provider implementation before releasing the instance.</span></span> <span data-ttu-id="8e5e9-113">경우 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 반환 `true` 그렇지 않으면 인스턴스가 해제 되는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 구현은 알릴 책임이 `Dispatcher` 콜백 메서드를 사용 하 여 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-113">If <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> returns `true` the instance is released, otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span> <span data-ttu-id="8e5e9-114">호출 하 여 이렇게는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> 공급자의입니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-114">This is done by calling the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method of the provider.</span></span>

<span data-ttu-id="8e5e9-115">이 샘플에서는 해제 지연 될 수 있습니다 하는 방법을 보여 줍니다.는 <xref:System.ServiceModel.InstanceContext> 20 초 동안 유휴 시간 제한을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-115">This sample demonstrates how you can delay releasing the <xref:System.ServiceModel.InstanceContext> with an idle timeout of 20 seconds.</span></span>

## <a name="extending-the-instancecontext"></a><span data-ttu-id="8e5e9-116">InstanceContext 확장</span><span class="sxs-lookup"><span data-stu-id="8e5e9-116">Extending the InstanceContext</span></span>

<span data-ttu-id="8e5e9-117">Wcf의 경우 <xref:System.ServiceModel.InstanceContext> 서비스 인스턴스 간의 링크로 및 `Dispatcher`합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-117">In WCF, <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="8e5e9-118">WCF를 사용 하면 확장 가능한 개체 패턴을 사용 하 여 새 상태나 동작을 추가 하 여이 런타임 구성 요소를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-118">WCF allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="8e5e9-119">새로운 기능을 사용 하 여 기존 런타임 클래스를 확장 하거나 또는 개체에 새 상태 기능을 추가할 확장명 가능한 개체 패턴 WCF에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-119">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="8e5e9-120">확장명 가능한 개체 패턴에는 세 가지 인터페이스인 <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> 및 <xref:System.ServiceModel.IExtensionCollection%601>이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-120">There are three interfaces in the extensible object pattern: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, and <xref:System.ServiceModel.IExtensionCollection%601>.</span></span>

<span data-ttu-id="8e5e9-121"><xref:System.ServiceModel.IExtensibleObject%601> 인터페이스는 해당 기능을 사용자 지정 하는 확장을 허용 하도록 개체에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-121">The <xref:System.ServiceModel.IExtensibleObject%601> interface is implemented by objects to allow extensions that customize their functionality.</span></span>

<span data-ttu-id="8e5e9-122"><xref:System.ServiceModel.IExtension%601> 인터페이스는 `T` 형식의 클래스 확장일 수 있는 개체에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-122">The <xref:System.ServiceModel.IExtension%601> interface is implemented by objects that can be extensions of classes of type `T`.</span></span>

<span data-ttu-id="8e5e9-123">마지막으로, 합니다 <xref:System.ServiceModel.IExtensionCollection%601> 인터페이스의 컬렉션인 <xref:System.ServiceModel.IExtension%601> 구현의 검색할 수 있도록 구현 <xref:System.ServiceModel.IExtension%601> 형식에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-123">And finally, the <xref:System.ServiceModel.IExtensionCollection%601> interface is a collection of <xref:System.ServiceModel.IExtension%601> implementations that allows for retrieving an implementation of <xref:System.ServiceModel.IExtension%601> by their type.</span></span>

<span data-ttu-id="8e5e9-124">따라서 확장 하기 위해 합니다 <xref:System.ServiceModel.InstanceContext>를 구현 해야 합니다는 <xref:System.ServiceModel.IExtension%601> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-124">Therefore, in order to extend the <xref:System.ServiceModel.InstanceContext>, you must implement the <xref:System.ServiceModel.IExtension%601> interface.</span></span> <span data-ttu-id="8e5e9-125">이 샘플 프로젝트에는 `CustomLeaseExtension` 클래스에이 구현이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-125">In this sample project, the `CustomLeaseExtension` class contains this implementation.</span></span>

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

<span data-ttu-id="8e5e9-126"><xref:System.ServiceModel.IExtension%601> 인터페이스에는 <xref:System.ServiceModel.IExtension%601.Attach%2A> 및 <xref:System.ServiceModel.IExtension%601.Detach%2A>의 두 가지 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-126">The <xref:System.ServiceModel.IExtension%601> interface has two methods <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span></span> <span data-ttu-id="8e5e9-127">이름이 나타내듯이 이 두 메서드는 런타임에서 <xref:System.ServiceModel.InstanceContext> 클래스와 확장을 연결하거나 분리할 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-127">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="8e5e9-128">이 샘플에서는 `Attach` 메서드를 사용하여 확장의 현재 인스턴스에 속한 <xref:System.ServiceModel.InstanceContext> 개체를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-128">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

<span data-ttu-id="8e5e9-129">또한 확장에 필요한 구현을 추가하여 연장된 수명 지원을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-129">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="8e5e9-130">따라서 합니다 `ICustomLease` 인터페이스 원하는 메서드로 선언 및에서 구현 되는 `CustomLeaseExtension` 클래스.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-130">Therefore, the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>

```csharp
interface ICustomLease
{
    bool IsIdle { get; }
    InstanceContextIdleCallback Callback { get; set; }
}

class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease
{
}
```

<span data-ttu-id="8e5e9-131">WCF가 호출 하는 경우는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 에서 메서드를 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 구현에서는이 호출으로 라우팅됩니다 합니다 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드의 `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-131">When WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation, this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="8e5e9-132">그런 다음, `CustomLeaseExtension` 메서드의 전용 상태 참조를 확인 하는지 여부를 <xref:System.ServiceModel.InstanceContext> 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-132">Then, the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="8e5e9-133">유휴 상태인 경우, 반환 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-133">If it is idle, it returns `true`.</span></span> <span data-ttu-id="8e5e9-134">그렇지 않으면 연장된 수명 기간에 대한 타이머를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-134">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>

```csharp
public bool IsIdle
{
  get
  {
    lock (thisLock)
    {
      if (isIdle)
      {
        return true;
      }
      else
      {
        StartTimer();
        return false;
      }
    }
  }
}
```

<span data-ttu-id="8e5e9-135">타이머의 `Elapsed` 이벤트 발송자의 콜백 함수 다른 정리 주기를 시작 하기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-135">In the timer’s `Elapsed` event, the callback function in the Dispatcher is called in order to start another clean-up cycle.</span></span>

```csharp
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)
{
    lock (thisLock)
    {
        StopTimer();
        isIdle = true;
        Utility.WriteMessageToConsole(
            ResourceHelper.GetString("MsgLeaseExpired"));
        callback(owner);
    }
}
```

<span data-ttu-id="8e5e9-136">유휴 상태로 전환 되는 인스턴스에 대 한 새 메시지가 도착 하는 경우 실행 중인 타이머를 갱신할 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-136">There's no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>

<span data-ttu-id="8e5e9-137">이 샘플에서는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>을 구현하여 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드에 대한 호출을 가로채고 이를 `CustomLeaseExtension`에 라우트합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-137">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="8e5e9-138"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 구현은 `CustomLifetimeLease` 클래스에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-138">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="8e5e9-139"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드는 WCF 서비스 인스턴스를 해제 하려고 할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-139">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when WCF is about to release the service instance.</span></span> <span data-ttu-id="8e5e9-140">그러나 ServiceBehavior의 `ISharedSessionInstance` 컬렉션에는 특정 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 구현의 인스턴스가 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-140">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="8e5e9-141">즉, 알 수 없으므로 합니다 <xref:System.ServiceModel.InstanceContext> WCF 확인 시 닫혀는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-141">This means there's no way of knowing if the <xref:System.ServiceModel.InstanceContext> is closed at the time WCF checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="8e5e9-142">따라서이 샘플에서는 스레드 잠금을 요청을 직렬화 하는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-142">Therefore, this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e5e9-143">serialization은 애플리케이션의 성능에 큰 영향을 주므로 스레드 잠금은 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-143">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>

<span data-ttu-id="8e5e9-144">전용 멤버 필드에 사용 됩니다는 `CustomLifetimeLease` 유휴 상태를 추적 하는 클래스 및에서 반환 되는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-144">A private member field is used in the `CustomLifetimeLease` class to track the idle state and is returned by the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="8e5e9-145">때마다 합니다 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드를 호출 합니다 `isIdle` 필드를 반환 하 고 다시 설정 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-145">Each time the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is called, the `isIdle` field is returned and reset to `false`.</span></span>  <span data-ttu-id="8e5e9-146">디스패처에서 `false` 메서드를 호출할 수 있도록 하려면 이 값을 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-146">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>

```csharp
public bool IsIdle(InstanceContext instanceContext)
{
    get
    {
        lock (thisLock)
        {
            //...
            bool idleCopy = isIdle;
            isIdle = false;
            return idleCopy;
        }
    }
}
```

<span data-ttu-id="8e5e9-147">경우는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> 메서드가 반환 `false`, 디스패처 콜백 함수를 사용 하 여 등록을 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-147">If the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> method returns `false`, the Dispatcher registers a callback function by using the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span> <span data-ttu-id="8e5e9-148">이 메서드는 해제되는 <xref:System.ServiceModel.InstanceContext>에 대한 참조를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-148">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="8e5e9-149">따라서 샘플 코드를 쿼리할 수 있습니다 합니다 `ICustomLease` 확장명을 입력 하 고 확인을 `ICustomLease.IsIdle` 확장 된 상태에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-149">Therefore, the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>

```csharp
public void NotifyIdle(InstanceContextIdleCallback callback,
            InstanceContext instanceContext)
{
    lock (thisLock)
    {
       ICustomLease customLease =
           instanceContext.Extensions.Find<ICustomLease>();
       customLease.Callback = callback;
       isIdle = customLease.IsIdle;
       if (isIdle)
       {
             callback(instanceContext);
       }
    }
}
```

<span data-ttu-id="8e5e9-150">전에 `ICustomLease.IsIdle` 속성을 검사, 콜백 속성을이 반드시 설정 해야 `CustomLeaseExtension` 유휴 상태일 때 디스패처를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-150">Before the `ICustomLease.IsIdle` property is checked, the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="8e5e9-151">`ICustomLease.IsIdle`이 `true`를 반환하는 경우에는 `isIdle`에서 전용 멤버 `CustomLifetimeLease`이 `true`로 설정되고 callback 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-151">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="8e5e9-152">코드에서 잠금을 유지 하므로 다른 스레드가이 전용 멤버의 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-152">Because the code holds a lock, other threads can't change the value of this private member.</span></span> <span data-ttu-id="8e5e9-153">디스패처에서 호출 되며 다음에 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>를 반환 합니다 `true` 디스패처에서 인스턴스를 해제 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-153">And the next time Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, it returns `true` and lets Dispatcher release the instance.</span></span>

<span data-ttu-id="8e5e9-154">사용자 지정 확장의 기반이 완성된 후에는 이를 서비스 모델에 후크해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-154">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="8e5e9-155">후크 하는 `CustomLeaseExtension` 구현을 <xref:System.ServiceModel.InstanceContext>, WCF는 제공 합니다 <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> 의 부트스트래핑을 수행 하는 인터페이스 <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-155">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, WCF provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="8e5e9-156">샘플에서 `CustomLeaseInitializer` 클래스는 이 인터페이스를 구현하고 유일한 메서드 초기화에서 `CustomLeaseExtension` 컬렉션에 <xref:System.ServiceModel.InstanceContext.Extensions%2A>의 인스턴스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-156">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="8e5e9-157">이 메서드는 <xref:System.ServiceModel.InstanceContext>를 초기화하는 동안 디스패처에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-157">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 <span data-ttu-id="8e5e9-158">마지막 합니다 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 구현을 사용 하 여를 서비스 모델에 후크 되어를 <xref:System.ServiceModel.Description.IServiceBehavior> 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-158">Finally the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="8e5e9-159">이 구현은 `CustomLeaseTimeAttribute` 클래스에 배치되며 <xref:System.Attribute> 기본 클래스에서도 파생되어 이 동작을 특성으로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-159">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the <xref:System.Attribute> base class to expose this behavior as an attribute.</span></span>

```csharp
public void ApplyDispatchBehavior(ServiceDescription description,
           ServiceHostBase serviceHostBase)
{
    CustomLifetimeLease customLease = new CustomLifetimeLease(timeout);

    foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
    {
        ChannelDispatcher cd = cdb as ChannelDispatcher;

        if (cd != null)
        {
            foreach (EndpointDispatcher ed in cd.Endpoints)
            {
                ed.DispatchRuntime.InstanceContextProvider = customLease;
            }
        }
    }
}
```

<span data-ttu-id="8e5e9-160">`CustomLeaseTime` 특성으로 주석을 달아 이 동작을 샘플 서비스 클래스에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-160">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

<span data-ttu-id="8e5e9-161">샘플을 실행하면 작업 요청 및 응답이 서비스와 클라이언트 콘솔 창 모두에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-161">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="8e5e9-162">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-162">Press ENTER in each console window to shut down the service and client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8e5e9-163">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8e5e9-163">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="8e5e9-164">수행 했는지 확인 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-164">Ensure that you've performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="8e5e9-165">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-165">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="8e5e9-166">단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침을 따릅니다 [Windows Communication Foundation 샘플 실행](running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-166">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e5e9-167">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8e5e9-168">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-168">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="8e5e9-169">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8e5e9-170">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e9-170">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
