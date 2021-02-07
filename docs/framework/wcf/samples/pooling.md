---
description: '다음에 대 한 자세한 정보: 풀링'
title: Pooling
ms.date: 03/30/2017
ms.assetid: 688dfb30-b79a-4cad-a687-8302f8a9ad6a
ms.openlocfilehash: cb770b60a3011f95df5a2fdecea6cdc66b64710f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703850"
---
# <a name="pooling"></a><span data-ttu-id="1042b-103">Pooling</span><span class="sxs-lookup"><span data-stu-id="1042b-103">Pooling</span></span>

<span data-ttu-id="1042b-104">이 샘플에서는 개체 풀링을 지원 하도록 WCF (Windows Communication Foundation)를 확장 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-104">This sample demonstrates how to extend Windows Communication Foundation (WCF) to support object pooling.</span></span> <span data-ttu-id="1042b-105">엔터프라이즈 서비스의 `ObjectPoolingAttribute` 특성과 구문 및 의미 체계가 비슷한 특성을 만드는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-105">The sample demonstrates how to create an attribute that is syntactically and semantically similar to the `ObjectPoolingAttribute` attribute functionality of Enterprise Services.</span></span> <span data-ttu-id="1042b-106">개체 풀링을 통해 애플리케이션의 성능을 크게 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-106">Object pooling can provide a dramatic boost to an application's performance.</span></span> <span data-ttu-id="1042b-107">그러나 제대로 사용하지 않으면 역효과가 일어나기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-107">However, it can have the opposite effect if it is not used properly.</span></span> <span data-ttu-id="1042b-108">개체 풀링은 광범위한 초기화가 필요하며 자주 사용되는 개체를 다시 만드는 오버헤드를 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-108">Object pooling helps reduce the overhead of recreating frequently used objects that require extensive initialization.</span></span> <span data-ttu-id="1042b-109">그러나 풀링된 개체에서 메서드 호출이 완료되기까지 상당한 시간이 걸리는 경우 최대 풀 크기에 도달하는 즉시 개체 풀링은 추가 요청을 큐에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-109">However, if a call to a method on a pooled object takes a considerable amount of time to complete, object pooling queues additional requests as soon as the maximum pool size is reached.</span></span> <span data-ttu-id="1042b-110">따라서 일부 개체 만들기 요청을 처리하지 않고 시간 초과 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-110">Thus it may fail to serve some object creation requests by throwing a timeout exception.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1042b-111">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="1042b-112">WCF 확장을 만드는 첫 번째 단계는 사용할 확장성 지점을 결정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-112">The first step in creating a WCF extension is to decide the extensibility point to use.</span></span>  
  
 <span data-ttu-id="1042b-113">WCF에서 *디스패처* 용어는 들어오는 메시지를 사용자 서비스의 메서드 호출로 변환 하 고 해당 메서드의 반환 값을 나가는 메시지로 변환 하는 런타임 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-113">In WCF the term *dispatcher* refers to a run-time component responsible for converting incoming messages into method invocations on the user’s service and for converting return values from that method to an outgoing message.</span></span> <span data-ttu-id="1042b-114">WCF 서비스는 각 끝점에 대 한 디스패처를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-114">A WCF service creates a dispatcher for each endpoint.</span></span> <span data-ttu-id="1042b-115">WCF 클라이언트는 해당 클라이언트와 연결 된 계약이 이중 계약 인 경우 디스패처를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-115">A WCF client must use a dispatcher if the contract associated with that client is a duplex contract.</span></span>  
  
 <span data-ttu-id="1042b-116">채널 및 엔드포인트 디스패처는 디스패처의 동작을 제어하는 다양한 속성을 노출시켜 채널 및 계약 수준의 확장성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-116">The channel and endpoint dispatchers offer channel-and contract-wide extensibility by exposing various properties that control the behavior of the dispatcher.</span></span> <span data-ttu-id="1042b-117">또한 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.DispatchRuntime%2A> 속성을 사용하면 디스패치 프로세스를 검사, 수정하거나 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-117">The <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.DispatchRuntime%2A> property also enables you to inspect, modify, or customize the dispatching process.</span></span> <span data-ttu-id="1042b-118">이 샘플에서는 서비스 클래스의 인스턴스를 제공하는 개체를 가리키는 <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> 속성을 중점적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-118">This sample focuses on the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property that points to the object that provides the instances of the service class.</span></span>  
  
## <a name="the-iinstanceprovider"></a><span data-ttu-id="1042b-119">IInstanceProvider</span><span class="sxs-lookup"><span data-stu-id="1042b-119">The IInstanceProvider</span></span>  

 <span data-ttu-id="1042b-120">WCF에서 디스패처는 인터페이스를 구현 하는를 사용 하 여 서비스 클래스의 인스턴스 <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> 를 만듭니다 <xref:System.ServiceModel.Dispatcher.IInstanceProvider> .</span><span class="sxs-lookup"><span data-stu-id="1042b-120">In WCF, the dispatcher creates instances of the service class using a <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>, which implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface.</span></span> <span data-ttu-id="1042b-121">이 인터페이스에는 세 개의 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-121">This interface has three methods:</span></span>  
  
- <span data-ttu-id="1042b-122"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>: 메시지가 도착하면 디스패처는 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> 메서드를 호출하여 메시지를 처리할 서비스 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-122"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>: When a message arrives the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> method to create an instance of the service class to process the message.</span></span> <span data-ttu-id="1042b-123">이 메서드의 호출 빈도는 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-123">The frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span> <span data-ttu-id="1042b-124">예를 들어 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성이 <xref:System.ServiceModel.InstanceContextMode.PerCall>로 설정되면 도착하는 각 메시지를 처리하기 위해 서비스 클래스의 새 인스턴스가 만들어지며, 따라서 메시지가 도착할 때마다 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-124">For example, if the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property is set to <xref:System.ServiceModel.InstanceContextMode.PerCall> a new instance of service class is created to process each message that arrives, so <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> is called whenever a message arrives.</span></span>  
  
- <span data-ttu-id="1042b-125"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%29>: 메시지 인수가 없을 때 호출된다는 점을 제외하고 이전 메서드와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-125"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%29>: This is identical to the previous method, except this is invoked when there is no Message argument.</span></span>  
  
- <span data-ttu-id="1042b-126"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29>: 서비스 인스턴스의 수명이 끝나면 디스패처는 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-126"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29>: When a service instance's lifetime has elapsed, the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29> method.</span></span> <span data-ttu-id="1042b-127"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> 메서드와 마찬가지로 이 메서드의 호출 빈도는 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-127">Just like for the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> method, the frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span>  
  
## <a name="the-object-pool"></a><span data-ttu-id="1042b-128">개체 풀</span><span class="sxs-lookup"><span data-stu-id="1042b-128">The Object Pool</span></span>  

 <span data-ttu-id="1042b-129">사용자 지정 <xref:System.ServiceModel.Dispatcher.IInstanceProvider> 구현에서 서비스에 필요한 개체 풀링 의미 체계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-129">A custom <xref:System.ServiceModel.Dispatcher.IInstanceProvider> implementation provides the required object pooling semantics for a service.</span></span> <span data-ttu-id="1042b-130">따라서 이 샘플에는 풀링을 위한 사용자 지정 `ObjectPoolingInstanceProvider` 구현을 제공하는 <xref:System.ServiceModel.Dispatcher.IInstanceProvider> 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-130">Therefore, this sample has an `ObjectPoolingInstanceProvider` type that provides custom implementation of <xref:System.ServiceModel.Dispatcher.IInstanceProvider> for pooling.</span></span> <span data-ttu-id="1042b-131">`Dispatcher`가 새 인스턴스를 만들지 않고 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> 메서드를 호출할 때 사용자 지정 구현은 메모리에 있는 풀에서 기존 개체를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-131">When the `Dispatcher` calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> method, instead of creating a new instance, the custom implementation looks for an existing object in an in-memory pool.</span></span> <span data-ttu-id="1042b-132">사용할 수 있는 개체가 있으면 반환되고,</span><span class="sxs-lookup"><span data-stu-id="1042b-132">If one is available, it is returned.</span></span> <span data-ttu-id="1042b-133">그렇지 않으면 새 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-133">Otherwise, a new object is created.</span></span> <span data-ttu-id="1042b-134">`GetInstance`의 구현은 다음 샘플 코드에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-134">The implementation for `GetInstance` is shown in the following sample code.</span></span>  
  
```csharp  
object IInstanceProvider.GetInstance(InstanceContext instanceContext, Message message)  
{  
    object obj = null;  
  
    lock (poolLock)  
    {  
        if (pool.Count > 0)  
        {  
            obj = pool.Pop();  
        }  
        else  
        {  
            obj = CreateNewPoolObject();  
        }  
        activeObjectsCount++;  
    }  
  
    WritePoolMessage(ResourceHelper.GetString("MsgNewObject"));  
  
    idleTimer.Stop();  
  
    return obj;
}  
```  
  
 <span data-ttu-id="1042b-135">사용자 지정 `ReleaseInstance` 구현에서는 해제된 인스턴스를 다시 풀에 추가하고 `ActiveObjectsCount` 값을 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-135">The custom `ReleaseInstance` implementation adds the released instance back to the pool and decrements the `ActiveObjectsCount` value.</span></span> <span data-ttu-id="1042b-136">`Dispatcher`는 서로 다른 스레드에 있는 이 메서드를 호출할 수 있기 때문에 `ObjectPoolingInstanceProvider` 클래스에서 클래스 수준 멤버에 대한 액세스의 동기화가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-136">The `Dispatcher` can call these methods from different threads, and therefore synchronized access to the class level members in the `ObjectPoolingInstanceProvider` class is required.</span></span>  
  
```csharp  
void IInstanceProvider.ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        pool.Push(instance);  
        activeObjectsCount--;  
  
        WritePoolMessage(  
        ResourceHelper.GetString("MsgObjectPooled"));  
  
        // When the service goes completely idle (no requests
        // are being processed), the idle timer is started  
        if (activeObjectsCount == 0)  
            idleTimer.Start();
    }  
}  
```  
  
 <span data-ttu-id="1042b-137">`ReleaseInstance`메서드는 "초기화 정리" 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-137">The `ReleaseInstance` method provides a "clean up initialization" feature.</span></span> <span data-ttu-id="1042b-138">일반적으로 풀은 풀의 수명 동안 최소한의 개체 수를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-138">Normally the pool maintains a minimum number of objects for the lifetime of the pool.</span></span> <span data-ttu-id="1042b-139">하지만 사용량이 지나치게 많은 경우에는 구성에 지정된 최대 한도를 사용하기 위해 풀에 추가 개체를 만들어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-139">However, there can be periods of excessive usage that require creating additional objects in the pool to reach the maximum limit specified in the configuration.</span></span> <span data-ttu-id="1042b-140">결국 풀의 사용이 줄어들면 그런 여분의 개체가 추가 오버헤드가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-140">Eventually, when the pool becomes less active, those surplus objects can become an extra overhead.</span></span> <span data-ttu-id="1042b-141">따라서 `activeObjectsCount`가 0에 도달하면 유휴 타이머가 시작되고 정리 주기를 트리거 및 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-141">Therefore, when the `activeObjectsCount` reaches zero, an idle timer is started that triggers and performs a clean-up cycle.</span></span>  
  
## <a name="adding-the-behavior"></a><span data-ttu-id="1042b-142">동작 추가</span><span class="sxs-lookup"><span data-stu-id="1042b-142">Adding the Behavior</span></span>  

 <span data-ttu-id="1042b-143">디스패처 계층 확장은 다음 동작을 사용하여 후크합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-143">Dispatcher-layer extensions are hooked up using the following behaviors:</span></span>  
  
- <span data-ttu-id="1042b-144">서비스 동작.</span><span class="sxs-lookup"><span data-stu-id="1042b-144">Service Behaviors.</span></span> <span data-ttu-id="1042b-145">전체 서비스 런타임을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-145">These allow for the customization of the entire service runtime.</span></span>  
  
- <span data-ttu-id="1042b-146">엔드포인트 동작.</span><span class="sxs-lookup"><span data-stu-id="1042b-146">Endpoint Behaviors.</span></span> <span data-ttu-id="1042b-147">서비스 엔드포인트, 특히 채널 및 엔드포인트 디스패처를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-147">These allow for the customization of service endpoints, specifically a Channel and Endpoint Dispatcher.</span></span>  
  
- <span data-ttu-id="1042b-148">계약 동작.</span><span class="sxs-lookup"><span data-stu-id="1042b-148">Contract Behaviors.</span></span> <span data-ttu-id="1042b-149">클라이언트 및 서비스에서 각각 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 및 <xref:System.ServiceModel.Dispatcher.DispatchRuntime> 클래스를 모두 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-149">These allow for the customization of both <xref:System.ServiceModel.Dispatcher.ClientRuntime> and <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes on the client and the service respectively.</span></span>  
  
 <span data-ttu-id="1042b-150">개체 풀링 확장을 위해 서비스 동작을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-150">For the purpose of an object pooling extension a service behavior must be created.</span></span> <span data-ttu-id="1042b-151">서비스 동작은 <xref:System.ServiceModel.Description.IServiceBehavior> 인터페이스를 구현하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-151">Service behaviors are created by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface.</span></span> <span data-ttu-id="1042b-152">서비스 모델에 사용자 지정 동작을 인식시키는 방법에는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-152">There are several ways to make the service model aware of the custom behaviors:</span></span>  
  
- <span data-ttu-id="1042b-153">사용자 지정 특성 사용</span><span class="sxs-lookup"><span data-stu-id="1042b-153">Using a custom attribute.</span></span>  
  
- <span data-ttu-id="1042b-154">사용자 지정 동작을 서비스 설명의 동작 컬렉션에 명령적으로 추가</span><span class="sxs-lookup"><span data-stu-id="1042b-154">Imperatively adding it to the service description’s behaviors collection.</span></span>  
  
- <span data-ttu-id="1042b-155">구성 파일 확장</span><span class="sxs-lookup"><span data-stu-id="1042b-155">Extending the configuration file.</span></span>  
  
 <span data-ttu-id="1042b-156">이 샘플에서는 사용자 지정 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-156">This sample uses a custom attribute.</span></span> <span data-ttu-id="1042b-157"><xref:System.ServiceModel.ServiceHost>가 구성되면 서비스의 형식 정의에 사용되는 특성을 확인한 후 서비스 설명의 동작 컬렉션에 사용 가능한 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-157">When the <xref:System.ServiceModel.ServiceHost> is constructed it examines the attributes used in the service’s type definition and adds the available behaviors to the service description’s behaviors collection.</span></span>  
  
 <span data-ttu-id="1042b-158"><xref:System.ServiceModel.Description.IServiceBehavior> 인터페이스에는 세 개의 메서드, 즉 <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>, <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> 및 <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-158">The interface <xref:System.ServiceModel.Description.IServiceBehavior> has three methods in it -- <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>, <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>, and <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span></span> <span data-ttu-id="1042b-159"><xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> 메서드는 동작이 서비스에 적용될 수 있음을 확인할 때 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-159">The <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> method is used to ensure that the behavior can be applied to the service.</span></span> <span data-ttu-id="1042b-160">이 샘플의 구현에서는 서비스에 <xref:System.ServiceModel.InstanceContextMode.Single>이 구현되지 않음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-160">In this sample, the implementation ensures that the service is not configured with <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span> <span data-ttu-id="1042b-161"><xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> 메서드는 서비스의 바인딩을 구성하는 데 사용되며,</span><span class="sxs-lookup"><span data-stu-id="1042b-161">The <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> method is used to configure the service's bindings.</span></span> <span data-ttu-id="1042b-162">이 시나리오에서는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-162">It is not required in this scenario.</span></span> <span data-ttu-id="1042b-163"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>는 서비스의 디스패처를 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-163">The <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> is used to configure the service's dispatchers.</span></span> <span data-ttu-id="1042b-164">이 메서드는가 초기화 될 때 WCF에 의해 호출 됩니다 <xref:System.ServiceModel.ServiceHost> .</span><span class="sxs-lookup"><span data-stu-id="1042b-164">This method is called by WCF when the <xref:System.ServiceModel.ServiceHost> is being initialized.</span></span> <span data-ttu-id="1042b-165">다음 매개 변수가 이 메서드로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-165">The following parameters are passed into this method:</span></span>  
  
- <span data-ttu-id="1042b-166">`Description`: 이 인수는 전체 서비스의 서비스 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-166">`Description`: This argument provides the service description for the entire service.</span></span> <span data-ttu-id="1042b-167">서비스의 엔드포인트, 계약, 바인딩 및 기타 데이터에 대한 설명을 검사할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-167">This can be used to inspect description data about the service’s endpoints, contracts, bindings, and other data.</span></span>  
  
- <span data-ttu-id="1042b-168">`ServiceHostBase`: 이 인수는 현재 초기화되는 <xref:System.ServiceModel.ServiceHostBase>를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-168">`ServiceHostBase`: This argument provides the <xref:System.ServiceModel.ServiceHostBase> that is currently being initialized.</span></span>  
  
 <span data-ttu-id="1042b-169">사용자 지정 <xref:System.ServiceModel.Description.IServiceBehavior> 구현에서는 `ObjectPoolingInstanceProvider`의 새 인스턴스가 인스턴스화되어 ServiceHostBase에서 각 <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>의 <xref:System.ServiceModel.Dispatcher.DispatchRuntime> 속성에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-169">In the custom <xref:System.ServiceModel.Description.IServiceBehavior> implementation a new instance of `ObjectPoolingInstanceProvider` is instantiated and assigned to the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property in each <xref:System.ServiceModel.Dispatcher.DispatchRuntime> in the ServiceHostBase.</span></span>  
  
```csharp  
void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    // Create an instance of the ObjectPoolInstanceProvider.  
    ObjectPoolingInstanceProvider instanceProvider = new  
           ObjectPoolingInstanceProvider(description.ServiceType,
                                                    minPoolSize);  
  
    // Forward the call if we created a ServiceThrottlingBehavior.  
    if (this.throttlingBehavior != null)  
    {  
        ((IServiceBehavior)this.throttlingBehavior).ApplyDispatchBehavior(description, serviceHostBase);  
    }  
  
    // In case there was already a ServiceThrottlingBehavior
    // (this.throttlingBehavior==null), it should have initialized
    // a single ServiceThrottle on all ChannelDispatchers.
    // As we loop through the ChannelDispatchers, we verify that
    // and modify the ServiceThrottle to guard MaxPoolSize.  
    ServiceThrottle throttle = null;  
  
    foreach (ChannelDispatcherBase cdb in
            serviceHostBase.ChannelDispatchers)  
    {  
        ChannelDispatcher cd = cdb as ChannelDispatcher;  
        if (cd != null)  
        {  
            // Make sure there is exactly one throttle used by all
            // endpoints. If there were others, we could not enforce
            // MaxPoolSize.  
            if ((this.throttlingBehavior == null) &&
                        (this.maxPoolSize != Int32.MaxValue))  
            {  
                throttle ??= cd.ServiceThrottle;
                if (cd.ServiceThrottle == null)  
                {  
                    throw new
InvalidOperationException(ResourceHelper.GetString("ExNullThrottle"));  
                }  
                if (throttle != cd.ServiceThrottle)  
                {  
                    throw new InvalidOperationException(ResourceHelper.GetString("ExDifferentThrottle"));  
                }  
             }  
  
             foreach (EndpointDispatcher ed in cd.Endpoints)  
             {  
                 // Assign it to DispatchBehavior in each endpoint.  
                 ed.DispatchRuntime.InstanceProvider =
                                      instanceProvider;  
             }  
         }  
     }  
  
     // Set the MaxConcurrentInstances to limit the number of items
     // that will ever be requested from the pool.  
     if ((throttle != null) && (throttle.MaxConcurrentInstances >
                                      this.maxPoolSize))  
     {  
         throttle.MaxConcurrentInstances = this.maxPoolSize;  
     }  
}  
```  
  
 <span data-ttu-id="1042b-170"><xref:System.ServiceModel.Description.IServiceBehavior> 구현 외에 <xref:System.EnterpriseServices.ObjectPoolingAttribute> 클래스에도 특성 인수를 사용하여 개체 풀을 사용자 지정하는 멤버가 몇 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-170">In addition to an <xref:System.ServiceModel.Description.IServiceBehavior> implementation the <xref:System.EnterpriseServices.ObjectPoolingAttribute> class has several members to customize the object pool using the attribute arguments.</span></span> <span data-ttu-id="1042b-171">이 멤버에는 .NET Enterprise Services에서 제공되는 개체 풀링 기능 집합과 일치하는 <xref:System.EnterpriseServices.ObjectPoolingAttribute.MaxPoolSize%2A>, <xref:System.EnterpriseServices.ObjectPoolingAttribute.MinPoolSize%2A> 및 <xref:System.EnterpriseServices.ObjectPoolingAttribute.CreationTimeout%2A>이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-171">These members include <xref:System.EnterpriseServices.ObjectPoolingAttribute.MaxPoolSize%2A>, <xref:System.EnterpriseServices.ObjectPoolingAttribute.MinPoolSize%2A>, and <xref:System.EnterpriseServices.ObjectPoolingAttribute.CreationTimeout%2A>, to match the object pooling feature set provided by .NET Enterprise Services.</span></span>  
  
 <span data-ttu-id="1042b-172">이제 새로 만든 사용자 지정 특성을 사용 하 여 서비스 구현에 주석을 추가 하 여 개체 풀링 동작을 WCF 서비스에 추가할 수 있습니다 `ObjectPooling` .</span><span class="sxs-lookup"><span data-stu-id="1042b-172">The object pooling behavior can now be added to a WCF service by annotating the service implementation with the newly created custom `ObjectPooling` attribute.</span></span>  
  
```csharp  
[ObjectPooling(MaxPoolSize=1024, MinPoolSize=10, CreationTimeout=30000)]
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="1042b-173">샘플 실행</span><span class="sxs-lookup"><span data-stu-id="1042b-173">Running the Sample</span></span>  

 <span data-ttu-id="1042b-174">이 샘플에서는 특정 시나리오에서 개체 풀링을 사용할 경우 얻을 수 있는 성능상의 이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-174">The sample demonstrates the performance benefits that can be gained by using object pooling in certain scenarios.</span></span>  
  
 <span data-ttu-id="1042b-175">서비스 애플리케이션은 `WorkService` 및 `ObjectPooledWorkService`의 두 가지 서비스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-175">The service application implements two services -- `WorkService` and `ObjectPooledWorkService`.</span></span> <span data-ttu-id="1042b-176">두 서비스 모두 동일한 구현을 공유합니다. 둘 다 고비용의 초기화가 필요하며 그 다음에는 상대적으로 경제적인 `DoWork()` 메서드를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-176">Both services share the same implementation -- they both require expensive initialization and then expose a `DoWork()` method that is relatively cheap.</span></span> <span data-ttu-id="1042b-177">유일한 차이점은 `ObjectPooledWorkService`에 개체 풀링이 구성된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-177">The only difference is that the `ObjectPooledWorkService` has object pooling configured:</span></span>  
  
```csharp  
[ObjectPooling(MinPoolSize = 0, MaxPoolSize = 5)]  
public class ObjectPooledWorkService : IDoWork  
{  
    public ObjectPooledWorkService()  
    {  
        Thread.Sleep(5000);  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService instance created.");  
    }  
  
    public void DoWork()  
    {  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService.GetData() completed.");  
    }
}  
```  
  
 <span data-ttu-id="1042b-178">클라이언트를 실행하면 `WorkService`를 5회 호출하여 시간을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-178">When you run the client, it times calling the `WorkService` 5 times.</span></span> <span data-ttu-id="1042b-179">그런 다음 `ObjectPooledWorkService`를 5회 호출하여 시간을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-179">It then times calling the `ObjectPooledWorkService` 5 times.</span></span> <span data-ttu-id="1042b-180">그리고 나서 시간의 차이를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-180">The difference in time is then displayed:</span></span>  
  
```console
Press <ENTER> to start the client.  
  
Calling WorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling WorkService took: 26722 ms.  
Calling ObjectPooledWorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling ObjectPooledWorkService took: 5323 ms.  
Press <ENTER> to exit.  
```  
  
> [!NOTE]
> <span data-ttu-id="1042b-181">클라이언트가 맨 처음 실행되면 두 서비스에 소요되는 시간이 대략 같은 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-181">The first time the client is run both services appear to take about the same amount of time.</span></span> <span data-ttu-id="1042b-182">샘플을 다시 실행하면 `ObjectPooledWorkService`가 훨씬 빨리 반환되는 것을 알 수 있는데, 이 개체의 인스턴스가 이미 풀에 존재하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-182">If you re-run the sample, you can see that the `ObjectPooledWorkService` returns much quicker because an instance of that object already exists in the pool.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1042b-183">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="1042b-183">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="1042b-184">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-184">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="1042b-185">솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="1042b-185">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="1042b-186">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="1042b-186">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1042b-187">Svcutil.exe를 사용하여 이 샘플에 대한 구성을 다시 생성할 경우 클라이언트 구성에서 엔드포인트 이름을 클라이언트 코드와 일치하도록 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-187">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1042b-188">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-188">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1042b-189">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1042b-189">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1042b-190">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-190">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1042b-191">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1042b-191">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Pooling`  
