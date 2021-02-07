---
description: '자세한 정보: 인스턴스 초기화'
title: 인스턴싱 초기화
ms.date: 03/30/2017
ms.assetid: 154d049f-2140-4696-b494-c7e53f6775ef
ms.openlocfilehash: 056f867012667abaf046827a7c6295f83d4794f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726522"
---
# <a name="instancing-initialization"></a><span data-ttu-id="acdc7-103">인스턴싱 초기화</span><span class="sxs-lookup"><span data-stu-id="acdc7-103">Instancing Initialization</span></span>

<span data-ttu-id="acdc7-104">이 샘플은 개체의 초기화를 활성화 및 비활성화 하 여 사용자 지정 하는 인터페이스를 정의 하 여 [풀링](pooling.md) 샘플을 확장 합니다 `IObjectControl` .</span><span class="sxs-lookup"><span data-stu-id="acdc7-104">This sample extends the [Pooling](pooling.md) sample by defining an interface, `IObjectControl`, which customizes the initialization of an object by activating and deactivating it.</span></span> <span data-ttu-id="acdc7-105">클라이언트에서는 개체를 풀로 반환하는 메서드와 개체를 풀로 반환하지 않는 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-105">The client invokes methods that return the object to the pool and that do not return the object to the pool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="acdc7-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="extensibility-points"></a><span data-ttu-id="acdc7-107">확장 지점</span><span class="sxs-lookup"><span data-stu-id="acdc7-107">Extensibility Points</span></span>  

 <span data-ttu-id="acdc7-108">WCF (Windows Communication Foundation) 확장을 만드는 첫 번째 단계는 사용할 확장성 지점을 결정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-108">The first step in creating a Windows Communication Foundation (WCF) extension is to decide the extensibility point to use.</span></span> <span data-ttu-id="acdc7-109">WCF에서 *EndpointDispatcher* 이라는 용어는 들어오는 메시지를 사용자 서비스의 메서드 호출로 변환 하 고 해당 메서드의 반환 값을 나가는 메시지로 변환 하는 런타임 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-109">In WCF, the term *EndpointDispatcher* refers to a run-time component responsible for converting incoming messages into method invocations on the user’s service and for converting return values from that method to an outgoing message.</span></span> <span data-ttu-id="acdc7-110">WCF 서비스는 각 끝점에 대해 EndpointDispatcher를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-110">A WCF service creates an EndpointDispatcher for each endpoint.</span></span>  
  
 <span data-ttu-id="acdc7-111">EndpointDispatcher는 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> 클래스를 사용하여 서비스에서 보내거나 받는 모든 메시지에 대해 엔드포인트 범위 확장성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-111">The EndpointDispatcher offers endpoint scope (for all messages received or sent by the service) extensibility using the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> class.</span></span> <span data-ttu-id="acdc7-112">이 클래스를 사용하면 EndpointDispatcher의 동작을 제어하는 다양한 속성을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-112">This class allows you to customize various properties that control the behavior of the EndpointDispatcher.</span></span> <span data-ttu-id="acdc7-113">이 샘플에서는 서비스 클래스의 인스턴스를 제공하는 개체를 가리키는 <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> 속성을 중점적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-113">This sample focuses on the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property that points to the object that provides the instances of the service class.</span></span>  
  
## <a name="iinstanceprovider"></a><span data-ttu-id="acdc7-114">IInstanceProvider</span><span class="sxs-lookup"><span data-stu-id="acdc7-114">IInstanceProvider</span></span>  

 <span data-ttu-id="acdc7-115">WCF에서 EndpointDispatcher는 인터페이스를 구현 하는 인스턴스 공급자를 사용 하 여 서비스 클래스의 인스턴스를 만듭니다 <xref:System.ServiceModel.Dispatcher.IInstanceProvider> .</span><span class="sxs-lookup"><span data-stu-id="acdc7-115">In WCF, the EndpointDispatcher creates instances of a service class by using an instance provider that implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface.</span></span> <span data-ttu-id="acdc7-116">이 인터페이스에는 다음과 같은 두 개의 메서드만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-116">This interface has only two methods:</span></span>  
  
- <span data-ttu-id="acdc7-117"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: 메시지가 도착하면 디스패처가 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> 메서드를 호출하여 메시지를 처리할 서비스 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-117"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: When a message arrives, the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method to create an instance of the service class to process the message.</span></span> <span data-ttu-id="acdc7-118">이 메서드의 호출 빈도는 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-118">The frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span> <span data-ttu-id="acdc7-119">예를 들어 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성이 <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType>로 설정된 경우 도착하는 각 메시지를 처리하기 위해 서비스 클래스의 새 인스턴스가 만들어지므로, 메시지가 도착할 때마다 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-119">For example if the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property is set to <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType>, a new instance of service class is created to process each message that arrives, so <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> is called whenever a message arrives.</span></span>  
  
- <span data-ttu-id="acdc7-120"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: 서비스 인스턴스가 메시지 처리 작업을 마치면 EndpointDispatcher는 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-120"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: When the service instance finishes processing the message, the EndpointDispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method.</span></span> <span data-ttu-id="acdc7-121"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> 메서드에서와 마찬가지로 이 메서드의 호출 빈도는 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-121">As in the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method, the frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span>  
  
## <a name="the-object-pool"></a><span data-ttu-id="acdc7-122">개체 풀</span><span class="sxs-lookup"><span data-stu-id="acdc7-122">The Object Pool</span></span>  

 <span data-ttu-id="acdc7-123">`ObjectPoolInstanceProvider` 클래스에는 개체 풀이 구현되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-123">The `ObjectPoolInstanceProvider` class contains the implementation for the object pool.</span></span> <span data-ttu-id="acdc7-124">이 클래스는 <xref:System.ServiceModel.Dispatcher.IInstanceProvider> 인터페이스를 구현하여 서비스 모델 계층과 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-124">This class implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface to interact with the service model layer.</span></span> <span data-ttu-id="acdc7-125">EndpointDispatcher가 새 인스턴스를 만드는 대신 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> 메서드를 호출하면 사용자 지정 구현에서 메모리 내의 풀에 있는 기존 개체를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-125">When the EndpointDispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method, instead of creating a new instance, the custom implementation looks for an existing object in an in-memory pool.</span></span> <span data-ttu-id="acdc7-126">사용할 수 있는 개체가 있으면 반환되고,</span><span class="sxs-lookup"><span data-stu-id="acdc7-126">If one is available, it is returned.</span></span> <span data-ttu-id="acdc7-127">그렇지 않으면 `ObjectPoolInstanceProvider`는 `ActiveObjectsCount` 속성(풀에서 반환된 개체의 개수)이 최대 풀 크기에 도달했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-127">Otherwise, `ObjectPoolInstanceProvider` checks whether the `ActiveObjectsCount` property (number of objects returned from the pool) has reached the maximum pool size.</span></span> <span data-ttu-id="acdc7-128">이 크기에 도달하지 않았으면 새 인스턴스가 만들어지고 호출자에게 반환하며 이어서 `ActiveObjectsCount`가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-128">If not, a new instance is created and returned to the caller and `ActiveObjectsCount` is subsequently incremented.</span></span> <span data-ttu-id="acdc7-129">도달했으면 구성된 시간 동안 개체 만들기 요청이 큐에 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-129">Otherwise an object creation request is queued for a configured period of time.</span></span> <span data-ttu-id="acdc7-130">`GetObjectFromThePool`의 구현은 다음 샘플 코드에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-130">The implementation for `GetObjectFromThePool` is shown in the following sample code.</span></span>  
  
```csharp
private object GetObjectFromThePool()  
{  
    bool didNotTimeout =
       availableCount.WaitOne(creationTimeout, true);  
    if(didNotTimeout)  
    {  
         object obj = null;  
         lock (poolLock)  
        {  
             if (pool.Count != 0)  
             {  
                   obj = pool.Pop();  
                   activeObjectsCount++;  
             }  
             else if (pool.Count == 0)  
             {  
                   if (activeObjectsCount < maxPoolSize)  
                   {  
                        obj = CreateNewPoolObject();  
                        activeObjectsCount++;  
  
                        #if (DEBUG)  
                        WritePoolMessage(  
                             ResourceHelper.GetString("MsgNewObject"));  
                       #endif  
                   }
            }  
           idleTimer.Stop();  
      }  
     // Call the Activate method if possible.  
    if (obj is IObjectControl)  
   {  
         ((IObjectControl)obj).Activate();  
   }  
   return obj;  
}  
throw new TimeoutException(  
ResourceHelper.GetString("ExObjectCreationTimeout"));  
}  
```  
  
 <span data-ttu-id="acdc7-131">사용자 지정 `ReleaseInstance` 구현에서는 해제된 인스턴스를 다시 풀에 추가하고 `ActiveObjectsCount` 값을 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-131">The custom `ReleaseInstance` implementation adds the released instance back to the pool and decrements the `ActiveObjectsCount` value.</span></span> <span data-ttu-id="acdc7-132">EndpointDispatcher는 서로 다른 스레드에서 이러한 메서드를 호출할 수 있기 때문에 `ObjectPoolInstanceProvider` 클래스의 클래스 수준 멤버에 대한 액세스를 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-132">The EndpointDispatcher can call these methods from different threads, and therefore synchronized access to the class level members in the `ObjectPoolInstanceProvider` class is required.</span></span>  
  
```csharp
public void ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        // Check whether the object can be pooled.
        // Call the Deactivate method if possible.  
        if (instance is IObjectControl)  
        {  
            IObjectControl objectControl = (IObjectControl)instance;  
            objectControl.Deactivate();  
  
            if (objectControl.CanBePooled)  
            {  
                pool.Push(instance);  
  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectPooled"));  
                #endif
            }  
            else  
            {  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectWasNotPooled"));  
                #endif  
            }  
        }  
        else  
        {  
            pool.Push(instance);  
  
            #if(DEBUG)  
            WritePoolMessage(  
                ResourceHelper.GetString("MsgObjectPooled"));  
            #endif
        }  
  
        activeObjectsCount--;  
  
        if (activeObjectsCount == 0)  
        {  
            idleTimer.Start();
        }  
    }  
  
    availableCount.Release(1);  
}  
```  
  
 <span data-ttu-id="acdc7-133">`ReleaseInstance`메서드는 *정리 초기화* 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-133">The `ReleaseInstance` method provides a *clean up initialization* feature.</span></span> <span data-ttu-id="acdc7-134">일반적으로 풀은 풀의 수명 동안 최소한의 개체 수를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-134">Normally the pool maintains a minimum number of objects for the lifetime of the pool.</span></span> <span data-ttu-id="acdc7-135">하지만 사용량이 지나치게 많은 경우에는 구성에 지정된 최대 한도를 사용하기 위해 풀에 추가 개체를 만들어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-135">However, there can be periods of excessive usage that require creating additional objects in the pool to reach the maximum limit specified in the configuration.</span></span> <span data-ttu-id="acdc7-136">결국 풀의 사용이 줄어들면 여분의 해당 개체는 추가 오버헤드가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-136">Eventually when the pool becomes less active those surplus objects can become an extra overhead.</span></span> <span data-ttu-id="acdc7-137">따라서 `activeObjectsCount`가 0에 도달하면 정리 주기를 트리거하고 수행하는 유휴 타이머가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-137">Therefore when the `activeObjectsCount` reaches zero an idle timer is started that triggers and performs a clean-up cycle.</span></span>  
  
```csharp  
if (activeObjectsCount == 0)  
{  
    idleTimer.Start();
}  
```  
  
 <span data-ttu-id="acdc7-138">ServiceModel 계층 확장은 다음 동작을 사용하여 후크됩니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-138">ServiceModel layer extensions are hooked up using the following behaviors:</span></span>  
  
- <span data-ttu-id="acdc7-139">서비스 동작: 전체 서비스 런타임을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-139">Service Behaviors: These allow for the customization of the entire service runtime.</span></span>  
  
- <span data-ttu-id="acdc7-140">엔드포인트 동작: EndpointDispatcher를 포함한 특정 서비스 엔드포인트를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-140">Endpoint Behaviors: These allow for the customization of a particular service endpoint, including the EndpointDispatcher.</span></span>  
  
- <span data-ttu-id="acdc7-141">계약 동작: 클라이언트 또는 서비스에서 각각 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 또는 <xref:System.ServiceModel.Dispatcher.DispatchRuntime> 클래스를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-141">Contract Behaviors: These allow for the customization of either <xref:System.ServiceModel.Dispatcher.ClientRuntime> or <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes on the client or the service respectively.</span></span>  
  
- <span data-ttu-id="acdc7-142">작업 동작: 클라이언트 또는 서비스에서 각각 <xref:System.ServiceModel.Dispatcher.ClientOperation> 또는 <xref:System.ServiceModel.Dispatcher.DispatchOperation> 클래스를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-142">Operation Behaviors: These allow for the customization of either <xref:System.ServiceModel.Dispatcher.ClientOperation> or <xref:System.ServiceModel.Dispatcher.DispatchOperation> classes on the client or the service respectively.</span></span>  
  
 <span data-ttu-id="acdc7-143">개체 풀링 확장을 위해 엔드포인트 동작 또는 서비스 동작을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-143">For the purpose of an object pooling extension, either an endpoint behavior or a service behavior can be created.</span></span> <span data-ttu-id="acdc7-144">이 예제에서는 서비스의 모든 엔드포인트에 개체 풀링 기능을 적용하는 서비스 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-144">In this example, we use a service behavior, which applies object pooling ability to every endpoint of the service.</span></span> <span data-ttu-id="acdc7-145">서비스 동작은 <xref:System.ServiceModel.Description.IServiceBehavior> 인터페이스를 구현하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-145">Service behaviors are created by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface.</span></span> <span data-ttu-id="acdc7-146">ServiceModel에 사용자 지정 동작을 인식시키는 방법에는 다음 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-146">There are several ways to make the ServiceModel aware of the custom behaviors:</span></span>  
  
- <span data-ttu-id="acdc7-147">사용자 지정 특성 사용</span><span class="sxs-lookup"><span data-stu-id="acdc7-147">Using a custom attribute.</span></span>  
  
- <span data-ttu-id="acdc7-148">사용자 지정 동작을 서비스 설명의 동작 컬렉션에 명령적으로 추가</span><span class="sxs-lookup"><span data-stu-id="acdc7-148">Imperatively adding it to the service description’s behaviors collection.</span></span>  
  
- <span data-ttu-id="acdc7-149">구성 파일 확장</span><span class="sxs-lookup"><span data-stu-id="acdc7-149">Extending the configuration file.</span></span>  
  
 <span data-ttu-id="acdc7-150">이 샘플에서는 사용자 지정 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-150">This sample uses a custom attribute.</span></span> <span data-ttu-id="acdc7-151"><xref:System.ServiceModel.ServiceHost>가 생성되면 이는 서비스의 형식 정의에 사용된 특성을 확인하고 사용 가능한 동작을 서비스 설명의 동작 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-151">When the <xref:System.ServiceModel.ServiceHost> is constructed, it examines the attributes used in the service’s type definition and adds the available behaviors to the service description’s behaviors collection.</span></span>  
  
 <span data-ttu-id="acdc7-152">인터페이스에는 <xref:System.ServiceModel.Description.IServiceBehavior> <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> `,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> `,` 및 <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> 라는 세 가지 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-152">The <xref:System.ServiceModel.Description.IServiceBehavior> interface has three methods: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>`,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>`,` and <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span></span> <span data-ttu-id="acdc7-153">이러한 메서드는가 초기화 될 때 WCF에 의해 호출 됩니다 <xref:System.ServiceModel.ServiceHost> .</span><span class="sxs-lookup"><span data-stu-id="acdc7-153">These methods are called by WCF when the <xref:System.ServiceModel.ServiceHost> is being initialized.</span></span> <span data-ttu-id="acdc7-154"><xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType>가 먼저 호출되어 서비스에 일관성을 검사할 수 있게 해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-154"><xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType> is called first; it allows the service to be inspected for inconsistencies.</span></span> <span data-ttu-id="acdc7-155"><xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType>이 다음으로 호출됩니다. 이 메서드는 고급 시나리오에서만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-155"><xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType> is called next; this method is only required in very advanced scenarios.</span></span> <span data-ttu-id="acdc7-156"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>가 마지막으로 호출되며 런타임 구성을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-156"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> is called last and is responsible for configuring the runtime.</span></span> <span data-ttu-id="acdc7-157">다음 매개 변수가 <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-157">The following parameters are passed into <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>:</span></span>  
  
- <span data-ttu-id="acdc7-158">`Description`: 이 매개 변수는 전체 서비스에 대한 서비스 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-158">`Description`: This parameter provides the service description for the entire service.</span></span> <span data-ttu-id="acdc7-159">이 매개 변수를 사용하여 서비스의 엔드포인트, 계약, 바인딩 및 그 외 서비스와 관련된 데이터에 대한 설명 데이터를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-159">This can be used to inspect description data about the service’s endpoints, contracts, bindings, and other data associated with the service.</span></span>  
  
- <span data-ttu-id="acdc7-160">`ServiceHostBase`: 이 매개 변수는 현재 초기화하고 있는 <xref:System.ServiceModel.ServiceHostBase>를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-160">`ServiceHostBase`: This parameter provides the <xref:System.ServiceModel.ServiceHostBase> that is currently being initialized.</span></span>  
  
 <span data-ttu-id="acdc7-161">사용자 지정 <xref:System.ServiceModel.Description.IServiceBehavior> 구현에서는 `ObjectPoolInstanceProvider`의 새 인스턴스가 인스턴스화되어 <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>에 첨부된 각 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>의 <xref:System.ServiceModel.ServiceHostBase> 속성에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-161">In the custom <xref:System.ServiceModel.Description.IServiceBehavior> implementation, a new instance of `ObjectPoolInstanceProvider` is instantiated and assigned to the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property in each <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> that is attached to the <xref:System.ServiceModel.ServiceHostBase>.</span></span>  
  
```csharp
public void ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    if (enabled)  
    {  
        // Create an instance of the ObjectPoolInstanceProvider.  
        instanceProvider = new ObjectPoolInstanceProvider(description.ServiceType,  
        maxPoolSize, minPoolSize, creationTimeout);  
  
        // Assign our instance provider to Dispatch behavior in each
        // endpoint.  
        foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)  
        {  
             ChannelDispatcher cd = cdb as ChannelDispatcher;  
             if (cd != null)  
             {  
                 foreach (EndpointDispatcher ed in cd.Endpoints)  
                 {  
                        ed.DispatchRuntime.InstanceProvider = instanceProvider;  
                 }  
             }  
         }  
     }  
}
```  
  
 <span data-ttu-id="acdc7-162"><xref:System.ServiceModel.Description.IServiceBehavior> 구현 외에 `ObjectPoolingAttribute` 클래스에도 특성 인수를 사용하여 개체 풀을 사용자 지정하는 멤버가 몇 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-162">In addition to an <xref:System.ServiceModel.Description.IServiceBehavior> implementation the `ObjectPoolingAttribute` class has several members to customize the object pool using the attribute arguments.</span></span> <span data-ttu-id="acdc7-163">이러한 멤버에는 .NET Enterprise Services에서 제공하는 개체 풀링 기능 집합과 일치하는 `MaxSize`, `MinSize`, `Enabled` 및 `CreationTimeout`이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-163">These members include `MaxSize`, `MinSize`, `Enabled` and `CreationTimeout`, to match the object pooling feature set provided by .NET Enterprise Services.</span></span>  
  
 <span data-ttu-id="acdc7-164">이제 새로 만든 사용자 지정 특성을 사용 하 여 서비스 구현에 주석을 추가 하 여 개체 풀링 동작을 WCF 서비스에 추가할 수 있습니다 `ObjectPooling` .</span><span class="sxs-lookup"><span data-stu-id="acdc7-164">The object pooling behavior can now be added to a WCF service by annotating the service implementation with the newly created custom `ObjectPooling` attribute.</span></span>  
  
```csharp  
[ObjectPooling(MaxSize=1024, MinSize=10, CreationTimeout=30000]
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="hooking-activation-and-deactivation"></a><span data-ttu-id="acdc7-165">활성화 및 비활성화 후크</span><span class="sxs-lookup"><span data-stu-id="acdc7-165">Hooking Activation and Deactivation</span></span>  

 <span data-ttu-id="acdc7-166">개체 풀링의 주요 목적은 만들고 초기화하는 데 비교적 자원이 많이 사용되는 수명이 짧은 개체를 최적화하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-166">The primary objective of object pooling is to optimize short-lived objects with relatively expensive creation and initialization.</span></span> <span data-ttu-id="acdc7-167">따라서 개체 풀링을 제대로 사용하면 애플리케이션의 성능을 현저히 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-167">Therefore it can give a dramatic performance boost to an application if properly used.</span></span> <span data-ttu-id="acdc7-168">풀에서 개체가 반환되기 때문에 생성자는 한 번만 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-168">Because the object is returned from the pool, the constructor is called only once.</span></span> <span data-ttu-id="acdc7-169">반면 일부 애플리케이션의 경우는 단일 컨텍스트 동안 사용된 리소스를 초기화하고 정리할 수 있도록 일정 수준의 제어가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-169">However, some applications require some level of control so that they can initialize and clean-up the resources used during a single context.</span></span> <span data-ttu-id="acdc7-170">예를 들어 일련의 계산에 사용되는 개체는 다음 계산을 처리하기 전에 private 필드를 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-170">For example, an object being used for a set of calculations can reset its private fields before processing the next calculation.</span></span> <span data-ttu-id="acdc7-171">엔터프라이즈 서비스에서는 개체 개발자가 `Activate` 기본 클래스의 `Deactivate` 및 <xref:System.EnterpriseServices.ServicedComponent> 메서드를 재정의할 수 있도록 하여 이러한 종류의 컨텍스트별 초기화를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-171">Enterprise Services enabled this kind of context-specific initialization by letting the object developer override `Activate` and `Deactivate` methods from the <xref:System.EnterpriseServices.ServicedComponent> base class.</span></span>  
  
 <span data-ttu-id="acdc7-172">개체 풀은 풀에서 개체를 반환하기 바로 전에 `Activate` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-172">The object pool calls the `Activate` method just before returning the object from the pool.</span></span> <span data-ttu-id="acdc7-173">개체가 풀로 다시 돌아갈 때 `Deactivate`가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-173">`Deactivate` is called when the object returns back to the pool.</span></span> <span data-ttu-id="acdc7-174"><xref:System.EnterpriseServices.ServicedComponent> 기본 클래스에는 또한 개체를 계속 풀링할 수 있는지 여부를 풀에 알리는 데 사용되는 `boolean`라는 `CanBePooled` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-174">The <xref:System.EnterpriseServices.ServicedComponent> base class also has a `boolean` property called `CanBePooled`, which can be used to notify the pool whether the object can be pooled further.</span></span>  
  
 <span data-ttu-id="acdc7-175">이 기능을 모방하기 위해 이 샘플에서는 이전에 언급된 멤버가 있는 공용 인터페이스(`IObjectControl`)를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-175">To mimic this functionality, the sample declares a public interface (`IObjectControl`) that has the aforementioned members.</span></span> <span data-ttu-id="acdc7-176">그런 다음 이 인터페이스는 컨텍스트별 초기화를 제공하는 데 사용되는 서비스 클래스에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-176">This interface is then implemented by service classes intended to provide context specific initialization.</span></span> <span data-ttu-id="acdc7-177">이러한 요구 사항에 맞게 <xref:System.ServiceModel.Dispatcher.IInstanceProvider> 구현을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-177">The <xref:System.ServiceModel.Dispatcher.IInstanceProvider> implementation must be modified to meet these requirements.</span></span> <span data-ttu-id="acdc7-178">이제 메서드를 호출 하 여 개체를 가져올 때마다 `GetInstance` 개체가 구현 되는지 여부를 확인 해야 합니다 `IObjectControl.` .이 경우에는 메서드를 적절 하 게 호출 해야 합니다 `Activate` .</span><span class="sxs-lookup"><span data-stu-id="acdc7-178">Now, each time you get an object by calling the `GetInstance` method, you must check whether the object implements `IObjectControl.` If it does, you must call the `Activate` method appropriately.</span></span>  
  
```csharp  
if (obj is IObjectControl)  
{  
    ((IObjectControl)obj).Activate();  
}  
```  
  
 <span data-ttu-id="acdc7-179">개체를 풀에 반환할 때는 개체를 다시 풀에 추가하기 전에 `CanBePooled` 속성을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-179">When returning an object to the pool, a check is required for the `CanBePooled` property before adding the object back to the pool.</span></span>  
  
```csharp  
if (instance is IObjectControl)  
{  
    IObjectControl objectControl = (IObjectControl)instance;  
    objectControl.Deactivate();  
    if (objectControl.CanBePooled)  
    {  
       pool.Push(instance);  
    }  
}  
```  
  
 <span data-ttu-id="acdc7-180">서비스 개발자는 개체를 풀링할 수 있는지 여부를 결정할 수 있으므로 지정된 시간에 풀에 있는 개체 수가 최소 크기 아래로 내려갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-180">Because the service developer can decide whether an object can be pooled, the object count in the pool at a given time can go below the minimum size.</span></span> <span data-ttu-id="acdc7-181">따라서 개체 수가 최소 수준 아래로 내려갔는지 확인하고 정리 절차에서 필요한 시작 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-181">Therefore you must check whether the object count has gone below the minimum level and perform the necessary initialization in the clean-up procedure.</span></span>  
  
```csharp  
// Remove the surplus objects.  
if (pool.Count > minPoolSize)  
{  
  // Clean the surplus objects.  
}
else if (pool.Count < minPoolSize)  
{  
  // Reinitialize the missing objects.  
  while(pool.Count != minPoolSize)  
  {  
    pool.Push(CreateNewPoolObject());  
  }  
}  
```  
  
 <span data-ttu-id="acdc7-182">샘플을 실행하면 작업 요청 및 응답이 서비스와 클라이언트 콘솔 창 모두에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-182">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="acdc7-183">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-183">Press Enter in each console window to shut down the service and client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="acdc7-184">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="acdc7-184">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="acdc7-185">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="acdc7-186">솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="acdc7-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="acdc7-187">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="acdc7-187">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="acdc7-188">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-188">The samples may already be installed on your machine.</span></span> <span data-ttu-id="acdc7-189">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="acdc7-189">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="acdc7-190">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-190">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="acdc7-191">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acdc7-191">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Initialization`  
