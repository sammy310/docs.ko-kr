---
title: 동작을 사용하여 런타임 구성 및 확장
ms.date: 03/30/2017
helpviewer_keywords:
- attaching extensions using behaviors [WCF]
ms.assetid: 149b99b6-6eb6-4f45-be22-c967279677d9
ms.openlocfilehash: 67db06649d6059ff6b6e6fb8d84058621fcc7dab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185648"
---
# <a name="configuring-and-extending-the-runtime-with-behaviors"></a><span data-ttu-id="ea003-102">동작을 사용하여 런타임 구성 및 확장</span><span class="sxs-lookup"><span data-stu-id="ea003-102">Configuring and Extending the Runtime with Behaviors</span></span>
<span data-ttu-id="ea003-103">동작을 사용하면 기본 동작을 수정하고 서비스 구성을 검사 및 유효성을 검사하는 사용자 지정 확장을 추가하거나 WCF(Windows Communication Foundation) 클라이언트 및 서비스 응용 프로그램에서 런타임 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-103">Behaviors enable you to modify default behavior and add custom extensions that inspect and validate service configuration or modify runtime behavior in Windows Communication Foundation (WCF) client and service applications.</span></span> <span data-ttu-id="ea003-104">이 항목에서는 동작 인터페이스에 대해 설명하고 이를 구현하는 방법 및 프로그래밍 방식이나 구성 파일을 통해 서비스 애플리케이션의 서비스 설명 또는 클라이언트 애플리케이션의 엔드포인트에 추가하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-104">This topic describes the behavior interfaces, how to implement them, and how to add them to the service description (in a service application) or endpoint (in a client application) programmatically or in a configuration file.</span></span> <span data-ttu-id="ea003-105">시스템에서 제공한 비헤이비어 사용에 대한 자세한 내용은 [서비스 런타임 동작 지정](../specifying-service-run-time-behavior.md) 및 클라이언트 [런타임 동작 지정을](../specifying-client-run-time-behavior.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea003-105">For more information about using system-provided behaviors, see [Specifying Service Run-Time Behavior](../specifying-service-run-time-behavior.md) and [Specifying Client Run-Time Behavior](../specifying-client-run-time-behavior.md).</span></span>  
  
## <a name="behaviors"></a><span data-ttu-id="ea003-106">동작</span><span class="sxs-lookup"><span data-stu-id="ea003-106">Behaviors</span></span>  
 <span data-ttu-id="ea003-107">동작 유형은 WCF(WCF) 에서 해당 개체를 사용하여 WCF 서비스 또는 WCF 클라이언트를 실행하는 런타임을 만들기 전에 서비스 또는 서비스 끝점 설명 개체(각각 서비스 또는 클라이언트)에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-107">Behavior types are added to the service or service endpoint description objects (on the service or client, respectively) before those objects are used by Windows Communication Foundation (WCF) to create a runtime that executes a WCF service or a WCF client.</span></span> <span data-ttu-id="ea003-108">런타임 생성이 처리되는 동안 이러한 동작이 호출되면 동작은 계약, 바인딩 및 주소에 의해 생성된 런타임을 수정하는 메서드 및 런타임 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-108">When these behaviors are called during the runtime construction process they are then able to access runtime properties and methods that modify the runtime constructed by the contract, bindings, and addresses.</span></span>  
  
### <a name="behavior-methods"></a><span data-ttu-id="ea003-109">동작 메서드</span><span class="sxs-lookup"><span data-stu-id="ea003-109">Behavior Methods</span></span>  
 <span data-ttu-id="ea003-110">모든 동작에는 `AddBindingParameters` 메서드, `ApplyDispatchBehavior` 메서드, `Validate` 메서드 및 `ApplyClientBehavior` 메서드가 있지만, 한 가지 예외가 있습니다. <xref:System.ServiceModel.Description.IServiceBehavior>는 클라이언트에서 실행되지 않기 때문에 `ApplyClientBehavior`를 구현하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-110">All behaviors have an `AddBindingParameters` method, an `ApplyDispatchBehavior` method, a `Validate` method, and an `ApplyClientBehavior` method with one exception: Because <xref:System.ServiceModel.Description.IServiceBehavior> cannot execute in a client, it does not implement `ApplyClientBehavior`.</span></span>  
  
- <span data-ttu-id="ea003-111">런타임 생성 시 사용자 지정 개체를 사용하기 위해 이러한 개체를 사용자 지정 바인딩에서 액세스할 수 있는 컬렉션에 추가하거나 수정하려면 `AddBindingParameters` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-111">Use the `AddBindingParameters` method to modify or add custom objects to a collection that custom bindings can access for their use when the runtime is constructed.</span></span> <span data-ttu-id="ea003-112">예를 들어 보호 요구 사항에 지정된 내용은 채널 빌드 방식에 영향을 주지만 채널 개발자는 이를 모릅니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-112">For example, this how protection requirements are specified that affect the way the channel is built, but are not known by the channel developer.</span></span>  
  
- <span data-ttu-id="ea003-113">설명 트리와 해당 런타임 개체를 검사하여 일부 조건에 부합하는지 확인하려면 `Validate` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-113">Use the `Validate` method to examine the description tree and corresponding runtime object to ensure it conforms to some set of criteria.</span></span>  
  
- <span data-ttu-id="ea003-114">서비스나 클라이언트의 특정 범위에 대해 런타임을 수정하고 설명 트리를 검사하려면 `ApplyDispatchBehavior` 및 `ApplyClientBehavior` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-114">Use the `ApplyDispatchBehavior` and `ApplyClientBehavior` methods to examine the description tree and modify the runtime for a particular scope on either the service or the client.</span></span> <span data-ttu-id="ea003-115">확장명 개체도 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-115">You can also insert extension objects as well.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ea003-116">이러한 메서드에 제공되는 설명 트리는 검사용입니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-116">Although a description tree is provided in these methods, it is for examination only.</span></span> <span data-ttu-id="ea003-117">설명 트리가 수정되면 동작이 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-117">If a description tree is modified, the behavior is undefined.</span></span>  
  
 <span data-ttu-id="ea003-118">서비스 및 클라이언트 런타임 클래스를 통해, 수정할 수 있는 속성과 구현할 수 있는 사용자 지정 인터페이스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-118">The properties you can modify and the customization interfaces you can implement are accessed through the service and client runtime classes.</span></span> <span data-ttu-id="ea003-119">서비스 유형은 <xref:System.ServiceModel.Dispatcher.DispatchRuntime> 및  <xref:System.ServiceModel.Dispatcher.DispatchOperation> 클래스이며,</span><span class="sxs-lookup"><span data-stu-id="ea003-119">The service types are the <xref:System.ServiceModel.Dispatcher.DispatchRuntime> and  <xref:System.ServiceModel.Dispatcher.DispatchOperation> classes.</span></span> <span data-ttu-id="ea003-120">클라이언트 형식은 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 및 <xref:System.ServiceModel.Dispatcher.ClientOperation> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-120">The client types are the <xref:System.ServiceModel.Dispatcher.ClientRuntime> and <xref:System.ServiceModel.Dispatcher.ClientOperation> classes.</span></span> <span data-ttu-id="ea003-121"><xref:System.ServiceModel.Dispatcher.ClientRuntime>과 <xref:System.ServiceModel.Dispatcher.DispatchRuntime> 클래스는 클라이언트 전체 및 서비스 전체의 런타임 속성과 확장 컬렉션에 각각 액세스할 수 있는 확장성 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-121">The <xref:System.ServiceModel.Dispatcher.ClientRuntime> and <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes are the extensibility entry points to access client-wide and service-wide runtime properties and extension collections, respectively.</span></span> <span data-ttu-id="ea003-122">마찬가지로 <xref:System.ServiceModel.Dispatcher.ClientOperation>과 <xref:System.ServiceModel.Dispatcher.DispatchOperation> 클래스는 클라이언트 작업 및 서비스 작업의 런타임 속성과 확장명 컬렉션을 각각 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-122">Similarly, the <xref:System.ServiceModel.Dispatcher.ClientOperation> and  <xref:System.ServiceModel.Dispatcher.DispatchOperation> classes expose client operation and service operation runtime properties and extension collections, respectively.</span></span> <span data-ttu-id="ea003-123">하지만 작업 런타임 개체에서 더 넓은 범위의 런타임 개체에 액세스하거나 필요에 따라 그 반대로 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-123">You can, however, access the wider scoped runtime object from the operation runtime object and vice versa if need be.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea003-124">클라이언트의 실행 동작을 수정하는 데 사용할 수 있는 런타임 속성 및 확장 형식에 대한 설명은 [클라이언트 확장을](extending-clients.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea003-124">For a discussion of runtime properties and extension types that you can use to modify the execution behavior of a client, see [Extending Clients](extending-clients.md).</span></span> <span data-ttu-id="ea003-125">서비스 디스패처의 실행 동작을 수정하는 데 사용할 수 있는 런타임 속성 및 확장 유형에 대한 설명은 [디스패처 확장](extending-dispatchers.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea003-125">For a discussion of runtime properties and extension types that you can use to modify the execution behavior of a service dispatcher, see [Extending Dispatchers](extending-dispatchers.md).</span></span>  
  
 <span data-ttu-id="ea003-126">대부분의 WCF 사용자는 런타임과 직접 상호 작용하지 않습니다. 대신 구성 파일의 클래스 또는 동작에 끝점, 계약, 바인딩, 주소 및 동작 특성과 같은 핵심 프로그래밍 모델 구문구조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-126">Most WCF users do not interact with the runtime directly; instead they use core programming model constructs like endpoints, contracts, bindings, addresses, and behavior attributes on classes or behaviors in configuration files.</span></span> <span data-ttu-id="ea003-127">이러한 구문은 *설명 트리에서*설명하는 서비스 또는 클라이언트를 지원하기 위해 런타임을 생성하기 위한 전체 사양인 설명 트리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-127">These constructs make up the *description tree*, which is the complete specification for constructing a runtime to support a service or client described by the description tree.</span></span>  
  
 <span data-ttu-id="ea003-128">WCF에는 네 가지 종류의 동작이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-128">There are four kinds of behaviors in WCF:</span></span>  
  
- <span data-ttu-id="ea003-129">서비스 동작(<xref:System.ServiceModel.Description.IServiceBehavior> 형식)을 사용하면 <xref:System.ServiceModel.ServiceHostBase>를 비롯한 전체 서비스 런타임을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-129">Service behaviors (<xref:System.ServiceModel.Description.IServiceBehavior> types) enable the customization of the entire service runtime including <xref:System.ServiceModel.ServiceHostBase>.</span></span>  
  
- <span data-ttu-id="ea003-130">엔드포인트 동작(<xref:System.ServiceModel.Description.IEndpointBehavior> 형식)을 사용하면 서비스 엔드포인트와 이에 연결된 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> 개체를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-130">Endpoint behaviors (<xref:System.ServiceModel.Description.IEndpointBehavior> types) enable the customization of service endpoints and their associated <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> objects.</span></span>  
  
- <span data-ttu-id="ea003-131">계약 동작(<xref:System.ServiceModel.Description.IContractBehavior> 형식)을 사용하면 각각 클라이언트 및 서비스 애플리케이션에서 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 및 <xref:System.ServiceModel.Dispatcher.DispatchRuntime> 클래스를 모두 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-131">Contract behaviors (<xref:System.ServiceModel.Description.IContractBehavior> types) enable the customization of both the <xref:System.ServiceModel.Dispatcher.ClientRuntime> and <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes in client and service applications, respectively.</span></span>  
  
- <span data-ttu-id="ea003-132">작업 동작(<xref:System.ServiceModel.Description.IOperationBehavior> 형식)을 사용하면 클라이언트 및 서비스에서 <xref:System.ServiceModel.Dispatcher.ClientOperation> 및 <xref:System.ServiceModel.Dispatcher.DispatchOperation> 클래스를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-132">Operation behaviors (<xref:System.ServiceModel.Description.IOperationBehavior> types) enable the customization of the <xref:System.ServiceModel.Dispatcher.ClientOperation> and <xref:System.ServiceModel.Dispatcher.DispatchOperation> classes, again, on the client and service.</span></span>  
  
 <span data-ttu-id="ea003-133">이러한 동작은 애플리케이션 구성 파일을 사용하여 사용자 지정 특성을 구현함으로써 다양한 설명 개체에 추가할 수 있고, 또는 적합한 설명 개체의 동작 컬렉션에 이를 바로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-133">You can add these behaviors to the various description objects by implementing custom attributes, using application configuration files, or directly by adding them to the behaviors collection on the appropriate description object.</span></span> <span data-ttu-id="ea003-134">하지만 <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.ServiceHost>에서의 <xref:System.ServiceModel.ChannelFactory%601> 호출 이전에 서비스 설명 또는 서비스 엔드포인트 설명 개체에 추가되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-134">The must, however, be added to a service description or service endpoint description object prior to calling <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> on the <xref:System.ServiceModel.ServiceHost> or a <xref:System.ServiceModel.ChannelFactory%601>.</span></span>  
  
### <a name="behavior-scopes"></a><span data-ttu-id="ea003-135">동작 범위</span><span class="sxs-lookup"><span data-stu-id="ea003-135">Behavior Scopes</span></span>  
 <span data-ttu-id="ea003-136">각각 특정 범위의 런타임 액세스에 해당하는 네 가지 동작 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-136">There are four behavior types, each of which corresponds to a particular scope of runtime access.</span></span>  
  
#### <a name="service-behaviors"></a><span data-ttu-id="ea003-137">서비스 동작</span><span class="sxs-lookup"><span data-stu-id="ea003-137">Service Behaviors</span></span>  
 <span data-ttu-id="ea003-138"><xref:System.ServiceModel.Description.IServiceBehavior>를 구현하는 서비스 동작은 전체 서비스 런타임을 수정할 수 있는 기본 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-138">Service behaviors, which implement <xref:System.ServiceModel.Description.IServiceBehavior>, are the primary mechanism by which you modify the entire service runtime.</span></span> <span data-ttu-id="ea003-139">서비스 동작을 서비스에 추가하는 데는 다음과 같은 세 가지 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-139">There are three mechanisms for adding service behaviors to a service.</span></span>  
  
1. <span data-ttu-id="ea003-140">서비스 클래스의 특성 사용.</span><span class="sxs-lookup"><span data-stu-id="ea003-140">Using an attribute on the service class.</span></span>  <span data-ttu-id="ea003-141"><xref:System.ServiceModel.ServiceHost>가 생성되면 <xref:System.ServiceModel.ServiceHost> 구현에서는 리플렉션을 사용하여 서비스 유형에 대한 특성 집합을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-141">When a <xref:System.ServiceModel.ServiceHost> is constructed, the <xref:System.ServiceModel.ServiceHost> implementation uses reflection to discover the set of attributes on the type of the service.</span></span> <span data-ttu-id="ea003-142"><xref:System.ServiceModel.Description.IServiceBehavior>를 구현하는 특성이 있는 경우 <xref:System.ServiceModel.Description.ServiceDescription>의 동작 컬렉션에 해당 특성이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-142">If any of those attributes are implementations of <xref:System.ServiceModel.Description.IServiceBehavior>, they are added to the behaviors collection on <xref:System.ServiceModel.Description.ServiceDescription>.</span></span> <span data-ttu-id="ea003-143">이를 통해 이러한 동작이 서비스 런타임 생성에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-143">This allows those behaviors to participate in the construction of the service run time.</span></span>  
  
2. <span data-ttu-id="ea003-144">프로그래밍 방식으로 동작을 <xref:System.ServiceModel.Description.ServiceDescription>의 동작 컬렉션에 추가.</span><span class="sxs-lookup"><span data-stu-id="ea003-144">Programmatically adding the behavior to the behaviors collection on <xref:System.ServiceModel.Description.ServiceDescription>.</span></span> <span data-ttu-id="ea003-145">이 작업은 다음 코드를 통해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-145">This can be accomplished with the following lines of code:</span></span>  
  
    ```csharp
    ServiceHost host = new ServiceHost(/* Parameters */);  
    host.Description.Behaviors.Add(/* Service Behavior */);  
    ```  
  
3. <span data-ttu-id="ea003-146">구성을 확장하는 사용자 지정 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> 구현.</span><span class="sxs-lookup"><span data-stu-id="ea003-146">Implementing a custom <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> that extends configuration.</span></span> <span data-ttu-id="ea003-147">이를 통해 애플리케이션 구성 파일에서 서비스 동작을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-147">This enables the use of the service behavior from application configuration files.</span></span>  
  
 <span data-ttu-id="ea003-148">WCF의 서비스 동작예로는 <xref:System.ServiceModel.ServiceBehaviorAttribute> 특성, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>? 및 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 동작이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-148">Examples of service behaviors in WCF include the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute, the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>, and the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
#### <a name="contract-behaviors"></a><span data-ttu-id="ea003-149">계약 동작</span><span class="sxs-lookup"><span data-stu-id="ea003-149">Contract Behaviors</span></span>  
 <span data-ttu-id="ea003-150"><xref:System.ServiceModel.Description.IContractBehavior> 인터페이스를 구현하는 계약 동작은 계약에서 클라이언트와 서비스 런타임을 모두 확장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-150">Contract behaviors, which implement the <xref:System.ServiceModel.Description.IContractBehavior> interface, are used to extend both the client and service runtime across a contract.</span></span>  
  
 <span data-ttu-id="ea003-151">계약 동작을 계약에 추가하는 데는 다음과 같은 두 가지 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-151">There are two mechanisms for adding contract behaviors to a contract.</span></span>  <span data-ttu-id="ea003-152">첫 번째 메커니즘에서는 계약 인터페이스에 사용될 사용자 지정 특성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-152">The first mechanism is to create a custom attribute to be used on the contract interface.</span></span> <span data-ttu-id="ea003-153">계약 인터페이스가 a <xref:System.ServiceModel.ServiceHost> 또는 <xref:System.ServiceModel.ChannelFactory%601>a로 전달되면 WCF는 인터페이스의 특성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-153">When a contract interface is passed to either a <xref:System.ServiceModel.ServiceHost> or a <xref:System.ServiceModel.ChannelFactory%601>, WCF examines the attributes on the interface.</span></span> <span data-ttu-id="ea003-154"><xref:System.ServiceModel.Description.IContractBehavior>를 구현하는 특성이 있는 경우 해당 인터페이스용으로 만들어진 <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>의 동작 컬렉션에 해당 특성이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-154">If any attributes are implementations of <xref:System.ServiceModel.Description.IContractBehavior>, those are added to the behaviors collection on the <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType> created for that interface.</span></span>  
  
 <span data-ttu-id="ea003-155">사용자 지정 계약 동작 특성에 대한 <xref:System.ServiceModel.Description.IContractBehaviorAttribute?displayProperty=nameWithType>를 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-155">You can also implement the <xref:System.ServiceModel.Description.IContractBehaviorAttribute?displayProperty=nameWithType> on the custom contract behavior attribute.</span></span> <span data-ttu-id="ea003-156">이 경우 적용되는 동작은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-156">In this case, the behavior is as follows when applied to:</span></span>  
  
 <span data-ttu-id="ea003-157">• 계약 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="ea003-157">•A contract interface.</span></span> <span data-ttu-id="ea003-158">이 경우 동작은 모든 끝점에서 해당 형식의 모든 계약에 적용되고 WCF는 <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A?displayProperty=nameWithType> 속성 값을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-158">In this case, the behavior is applied to all contracts of that type in any endpoint and WCF ignores the value of the <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="ea003-159">• 서비스 클래스.</span><span class="sxs-lookup"><span data-stu-id="ea003-159">•A service class.</span></span> <span data-ttu-id="ea003-160">이 경우 동작은 <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A> 계약의 끝점에만 적용되며, 이 동작은 속성값입니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-160">In this case, the behavior is applied only to endpoints the contract of which is the value of the <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A> property.</span></span>  
  
 <span data-ttu-id="ea003-161">• 콜백 클래스.</span><span class="sxs-lookup"><span data-stu-id="ea003-161">•A callback class.</span></span> <span data-ttu-id="ea003-162">이 경우 동작은 양면 클라이언트의 끝점에 적용되고 WCF는 <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A> 속성 값을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-162">In this case, the behavior is applied to the duplex client's endpoint and WCF ignores the value of the <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A> property.</span></span>  
  
 <span data-ttu-id="ea003-163">두 번째 메커니즘에서는 <xref:System.ServiceModel.Description.ContractDescription>의 동작 컬렉션에 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-163">The second mechanism is to add the behavior to the behaviors collection on a <xref:System.ServiceModel.Description.ContractDescription>.</span></span>  
  
 <span data-ttu-id="ea003-164">WCF의 계약 동작의 예로는 <xref:System.ServiceModel.DeliveryRequirementsAttribute?displayProperty=nameWithType> 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-164">Examples of contract behaviors in WCF include the <xref:System.ServiceModel.DeliveryRequirementsAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="ea003-165">자세한 내용 및 예제는 참조 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea003-165">For more information and an example, see the reference topic.</span></span>  
  
#### <a name="endpoint-behaviors"></a><span data-ttu-id="ea003-166">엔드포인트 동작</span><span class="sxs-lookup"><span data-stu-id="ea003-166">Endpoint Behaviors</span></span>  
 <span data-ttu-id="ea003-167"><xref:System.ServiceModel.Description.IEndpointBehavior>를 구현하는 엔드포인트 동작은 특정 엔드포인트에 대한 전체 서비스 또는 클라이언트 런타임을 수정할 수 있는 기본 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-167">Endpoint behaviors, which implement <xref:System.ServiceModel.Description.IEndpointBehavior>, are the primary mechanism by which you modify the entire service or client run time for a specific endpoint.</span></span>  
  
 <span data-ttu-id="ea003-168">엔드포인트 동작을 서비스에 추가하는 데는 다음과 같은 두 가지 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-168">There are two mechanisms for adding endpoint behaviors to a service.</span></span>  
  
1. <span data-ttu-id="ea003-169">동작을 <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> 속성에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-169">Add the behavior to the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property.</span></span>  
  
2. <span data-ttu-id="ea003-170">구성을 확장하는 사용자 지정 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-170">Implement a custom <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> that extends configuration.</span></span>  
  
 <span data-ttu-id="ea003-171">자세한 내용 및 예제는 참조 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea003-171">For more information and an example, see the reference topic.</span></span>  
  
#### <a name="operation-behaviors"></a><span data-ttu-id="ea003-172">작업 동작</span><span class="sxs-lookup"><span data-stu-id="ea003-172">Operation Behaviors</span></span>  
 <span data-ttu-id="ea003-173"><xref:System.ServiceModel.Description.IOperationBehavior> 인터페이스를 구현하는 작업 동작은 각 작업에 대해 클라이언트와 서비스 런타임을 모두 확장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-173">Operation behaviors, which implement the <xref:System.ServiceModel.Description.IOperationBehavior> interface, are used to extend both the client and service runtime for each operation.</span></span>  
  
 <span data-ttu-id="ea003-174">작업 동작을 작업에 추가하는 데는 다음과 같은 두 가지 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-174">There are two mechanisms for adding operation behaviors to an operation.</span></span> <span data-ttu-id="ea003-175">첫 번째 메커니즘에서는 작업을 모델링하는 메서드에서 사용될 사용자 지정 특성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-175">The first mechanism is to create a custom attribute to be used on the method that models the operation.</span></span> <span data-ttu-id="ea003-176">A <xref:System.ServiceModel.ServiceHost> 또는 <xref:System.ServiceModel.ChannelFactory>에 작업이 추가되면 WCF는 <xref:System.ServiceModel.Description.IOperationBehavior> 해당 작업에 대해 <xref:System.ServiceModel.Description.OperationDescription> 생성된 동작 컬렉션에 모든 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-176">When an operation is added to either a <xref:System.ServiceModel.ServiceHost> or a <xref:System.ServiceModel.ChannelFactory>, WCF adds any  <xref:System.ServiceModel.Description.IOperationBehavior> attributes to the behaviors collection on the <xref:System.ServiceModel.Description.OperationDescription> created for that operation.</span></span>  
  
 <span data-ttu-id="ea003-177">두 번째 메커니즘에서는 생성된 <xref:System.ServiceModel.Description.OperationDescription>의 동작 컬렉션에 동작을 직접 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-177">The second mechanism is by directly adding the behavior to the behaviors collection on a constructed <xref:System.ServiceModel.Description.OperationDescription>.</span></span>  
  
 <span data-ttu-id="ea003-178">WCF의 작업 동작 의 예로는 <xref:System.ServiceModel.OperationBehaviorAttribute> <xref:System.ServiceModel.TransactionFlowAttribute>및 .</span><span class="sxs-lookup"><span data-stu-id="ea003-178">Examples of operation behaviors in WCF include the <xref:System.ServiceModel.OperationBehaviorAttribute> and the <xref:System.ServiceModel.TransactionFlowAttribute>.</span></span>  
  
 <span data-ttu-id="ea003-179">자세한 내용 및 예제는 참조 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea003-179">For more information and an example, see the reference topic.</span></span>  
  
### <a name="using-configuration-to-create-behaviors"></a><span data-ttu-id="ea003-180">구성을 사용하여 동작 생성</span><span class="sxs-lookup"><span data-stu-id="ea003-180">Using Configuration to Create Behaviors</span></span>  
 <span data-ttu-id="ea003-181">서비스와 엔드포인트 및 계약 동작은 코드나 특성을 사용하여 지정하도록 디자인할 수 있지만, 서비스와 엔드포인트 동작은 애플리케이션이나 웹 구성 파일을 통해서만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-181">Service and endpoint, and contract behaviors can by designed to be specified in code or using attributes; only service and endpoint behaviors can be configured using application or Web configuration files.</span></span> <span data-ttu-id="ea003-182">개발자는 특성을 사용하여 동작을 노출함으로써, 런타임에는 추가, 제거 또는 수정할 수 없는 동작을 컴파일 시간에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-182">Exposing behaviors using attributes allows developers to specify a behavior at compilation-time that cannot be added, removed, or modified at runtime.</span></span> <span data-ttu-id="ea003-183">따라서 올바른 서비스 동작을 위해 항상 필요한 동작에 적합합니다(예: <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType> 특성에 대한 트랜잭션 관련 매개 변수).</span><span class="sxs-lookup"><span data-stu-id="ea003-183">This is often suitable for behaviors that are always required for the correct operation of a service (for example, the transaction-related parameters to the <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType> attribute).</span></span> <span data-ttu-id="ea003-184">또한 개발자는 구성을 사용하여 동작을 노출함으로써, 해당 동작의 구성과 사양을 서비스 배포자에게 맡길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-184">Exposing behaviors using configuration allows developers to leave the specification and configuration of those behaviors to those who deploy the service.</span></span> <span data-ttu-id="ea003-185">따라서 서비스에 메타데이터가 노출되는지 또는 특정 권한 부여 구성이 노출되는지 등의 선택적 구성 요소 또는 기타 다른 배포 관련 구성 동작에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-185">This is suitable for behaviors that are optional components or other deployment-specific configuration, such as whether metadata is exposed for the service or the particular authorization configuration for a service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea003-186">또한 회사 애플리케이션 정책이 적용되도록 구성을 지원하는 동작은 machine.config 구성 파일에 삽입하고 해당 항목을 잠금으로써 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-186">You can also use behaviors that support configuration to enforce company application policies by inserting them into the machine.config configuration file and locking those items down.</span></span> <span data-ttu-id="ea003-187">설명 및 예제는 [엔터프라이즈에서 끝점을 잠그는 방법(방법)을](how-to-lock-down-endpoints-in-the-enterprise.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea003-187">For a description and an example, see [How to: Lock Down Endpoints in the Enterprise](how-to-lock-down-endpoints-in-the-enterprise.md).</span></span>  
  
 <span data-ttu-id="ea003-188">개발자의 경우 구성을 사용하여 동작을 노출하려면 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>의 파생 클래스를 만든 후 해당 확장을 구성에 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-188">To expose a behavior using configuration, a developer must create a derived class of <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> and then register that extension with configuration.</span></span>  
  
 <span data-ttu-id="ea003-189">다음 코드 예제에서는 <xref:System.ServiceModel.Description.IEndpointBehavior>를 통해 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-189">The following code example shows how an  <xref:System.ServiceModel.Description.IEndpointBehavior> implements <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>:</span></span>  
  
```csharp
// BehaviorExtensionElement members  
public override Type BehaviorType  
{  
  get { return typeof(EndpointBehaviorMessageInspector); }  
}  
  
protected override object CreateBehavior()  
{  
  return new EndpointBehaviorMessageInspector();  
}  
```  
  
 <span data-ttu-id="ea003-190">구성 시스템에서 사용자 지정 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>를 로드하려면 이 클래스가 확장으로 등록되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-190">In order for the configuration system to load a custom <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, it must be registered as an extension.</span></span> <span data-ttu-id="ea003-191">다음 코드 예제에서는 이전의 엔드포인트 동작에 대한 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-191">The following code example shows the configuration file for the preceding endpoint behavior:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service
        name="Microsoft.WCF.Documentation.SampleService"  
        behaviorConfiguration="metadataSupport"  
      >  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8080/ServiceMetadata" />  
          </baseAddresses>  
        </host>  
        <endpoint  
          address="/SampleService"  
          binding="wsHttpBinding"  
          behaviorConfiguration="withMessageInspector"
          contract="Microsoft.WCF.Documentation.ISampleService"  
        />  
        <endpoint  
           address="mex"  
           binding="mexHttpBinding"  
           contract="IMetadataExchange"  
        />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="metadataSupport">  
        <serviceMetadata httpGetEnabled="true" httpGetUrl=""/>  
      </behavior>  
      </serviceBehaviors>  
      <endpointBehaviors>  
        <behavior name="withMessageInspector">  
          <endpointMessageInspector />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <extensions>  
      <behaviorExtensions>  
        <add
          name="endpointMessageInspector"  
          type="Microsoft.WCF.Documentation.EndpointBehaviorMessageInspector, HostApplication, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"  
        />  
      </behaviorExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="ea003-192">동작 `Microsoft.WCF.Documentation.EndpointBehaviorMessageInspector` 확장 유형은 `HostApplication` 어디에 있으며 해당 클래스가 컴파일된 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-192">Where `Microsoft.WCF.Documentation.EndpointBehaviorMessageInspector` is the behavior extension type and `HostApplication` is the name of the assembly into which that class has been compiled.</span></span>  
  
### <a name="evaluation-order"></a><span data-ttu-id="ea003-193">평가 순서</span><span class="sxs-lookup"><span data-stu-id="ea003-193">Evaluation Order</span></span>  
 <span data-ttu-id="ea003-194"><xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>와 <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>는 설명 및 프로그래밍 모델을 통해 런타임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-194">The <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> and the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> are responsible for building the runtime from the programming model and description.</span></span> <span data-ttu-id="ea003-195">앞에서 설명한 대로 동작은 서비스, 엔드포인트, 계약 및 작업에서 빌드 프로세스를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-195">Behaviors, as previously described, contribute to that build process at the service, endpoint, contract, and operation.</span></span>  
  
 <span data-ttu-id="ea003-196"><xref:System.ServiceModel.ServiceHost>는 다음 순서로 동작을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-196">The <xref:System.ServiceModel.ServiceHost> applies behaviors in the following order:</span></span>  
  
1. <span data-ttu-id="ea003-197">서비스</span><span class="sxs-lookup"><span data-stu-id="ea003-197">Service</span></span>  
  
2. <span data-ttu-id="ea003-198">계약</span><span class="sxs-lookup"><span data-stu-id="ea003-198">Contract</span></span>  
  
3. <span data-ttu-id="ea003-199">엔드포인트</span><span class="sxs-lookup"><span data-stu-id="ea003-199">Endpoint</span></span>  
  
4. <span data-ttu-id="ea003-200">작업(Operation)</span><span class="sxs-lookup"><span data-stu-id="ea003-200">Operation</span></span>  
  
 <span data-ttu-id="ea003-201">동작 컬렉션 내에서는 정해진 순서가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-201">Within any collection of behaviors, no order is guaranteed.</span></span>  
  
 <span data-ttu-id="ea003-202"><xref:System.ServiceModel.ChannelFactory%601>는 다음 순서로 동작을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-202">The <xref:System.ServiceModel.ChannelFactory%601> applies behaviors in the following order:</span></span>  
  
1. <span data-ttu-id="ea003-203">계약</span><span class="sxs-lookup"><span data-stu-id="ea003-203">Contract</span></span>  
  
2. <span data-ttu-id="ea003-204">엔드포인트</span><span class="sxs-lookup"><span data-stu-id="ea003-204">Endpoint</span></span>  
  
3. <span data-ttu-id="ea003-205">작업(Operation)</span><span class="sxs-lookup"><span data-stu-id="ea003-205">Operation</span></span>  
  
 <span data-ttu-id="ea003-206">앞서 설명한 대로 동작 컬렉션 내에서는 정해진 순서가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-206">Within any collection of behaviors, again, no order is guaranteed.</span></span>  
  
### <a name="adding-behaviors-programmatically"></a><span data-ttu-id="ea003-207">프로그래밍 방식으로 동작 추가</span><span class="sxs-lookup"><span data-stu-id="ea003-207">Adding Behaviors Programmatically</span></span>  
 <span data-ttu-id="ea003-208"><xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType>의 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A?displayProperty=nameWithType> 메서드 다음에 나오는 서비스 애플리케이션의 <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType> 속성은 수정하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-208">Properties of the <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> in the service application must not be modified subsequent to the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A?displayProperty=nameWithType> method on <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ea003-209">이러한 지점을 지나서 수정될 경우 <xref:System.ServiceModel.ServiceHostBase.Credentials%2A?displayProperty=nameWithType> 및 `AddServiceEndpoint`의 <xref:System.ServiceModel.ServiceHostBase> 메서드와 <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> 속성과 같은 일부 멤버는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-209">Some members, like the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A?displayProperty=nameWithType> property and the `AddServiceEndpoint` methods on <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>, throw an exception if modified past that point.</span></span> <span data-ttu-id="ea003-210">다른 멤버에서는 이를 수정할 수 있지만 그 결과는 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-210">Others permit you to modify them, but the result is undefined.</span></span>  
  
 <span data-ttu-id="ea003-211">마찬가지로 클라이언트에서 <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>의 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A>을 호출한 이후에는 <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> 값을 수정해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-211">Similarly, on the client the <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType> values must not be modified after the call to <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> on the <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ea003-212">이러한 지점을 지나서 수정될 경우 <xref:System.ServiceModel.ChannelFactory.Credentials%2A?displayProperty=nameWithType> 속성에서 예외를 throw하지만 다른 클라이언트 설명 값은 오류를 발생시키지 않고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-212">The <xref:System.ServiceModel.ChannelFactory.Credentials%2A?displayProperty=nameWithType> property throws an exception if modified past that point, but the other client description values can be modified without error.</span></span> <span data-ttu-id="ea003-213">하지만 그 결과는 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-213">The result, however, is undefined.</span></span>  
  
 <span data-ttu-id="ea003-214">서비스와 클라이언트 모두에 대해 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType>을 호출하기 이전에 설명을 수정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-214">Whether for the service or client, it is recommended that you modify the description prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="inheritance-rules-for-behavior-attributes"></a><span data-ttu-id="ea003-215">동작 특성의 상속 규칙</span><span class="sxs-lookup"><span data-stu-id="ea003-215">Inheritance Rules for Behavior Attributes</span></span>  
 <span data-ttu-id="ea003-216">서비스 동작, 계약 동작 등 네 가지 형식의 모든 동작은 특성을 사용하여 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-216">All four types of behaviors can be populated using attributes – service behaviors and contract behaviors.</span></span> <span data-ttu-id="ea003-217">관리되는 개체 및 멤버에서 특성을 정의하고 관리되는 개체와 멤버에서는 상속을 지원하므로 상속 컨텍스트에서 동작 특성이 작동되는 방법을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-217">Because attributes are defined on managed objects and members, and managed objects and members support inheritance, it is necessary to define how behavior attributes work in the context of inheritance.</span></span>  
  
 <span data-ttu-id="ea003-218">상위 수준에서는 서비스, 계약 또는 작업 등의 특정 범위의 경우 해당 범위에 대해 상속 계층 구조의 모든 동작 특성이 적용된다는 것이 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-218">At a high level, the rule is that for a particular scope (for example, service, contract, or operation), all behavior attributes in the inheritance hierarchy for that scope are applied.</span></span> <span data-ttu-id="ea003-219">같은 형식의 동작 특성이 두 개 있으면 가장 많이 파생된 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-219">If there are two behavior attributes of the same type, only the most-derived type is used.</span></span>  
  
#### <a name="service-behaviors"></a><span data-ttu-id="ea003-220">서비스 동작</span><span class="sxs-lookup"><span data-stu-id="ea003-220">Service Behaviors</span></span>  
 <span data-ttu-id="ea003-221">지정된 서비스 클래스의 경우, 해당 클래스 및 그 클래스 부모의 모든 서비스 동작 특성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-221">For a given service class, all service behavior attributes on that class, and on parents of that class, are applied.</span></span> <span data-ttu-id="ea003-222">동일한 특성 형식이 상속 계층 구조의 여러 위치에 적용된 경우에는 가장 많이 파생된 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-222">If the same type of attribute is applied at multiple places in the inheritance hierarchy, the most-derived type is used.</span></span>  
  
```csharp  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple)]  
[AspNetCompatibilityRequirementsAttribute(  
    AspNetCompatibilityRequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
public class A { /* … */ }  
  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
public class B : A { /* … */}  
```  
  
 <span data-ttu-id="ea003-223">예를 들어 앞의 경우에서 서비스 B는 <xref:System.ServiceModel.InstanceContextMode>가 <xref:System.ServiceModel.InstanceContextMode.Single>, <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> 모드가 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>, <xref:System.ServiceModel.ConcurrencyMode>가 <xref:System.ServiceModel.ConcurrencyMode.Single>인 상태로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-223">For example, in the preceding case, the service B ends up with an <xref:System.ServiceModel.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.Single>, an <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> mode of <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>, and a <xref:System.ServiceModel.ConcurrencyMode> of <xref:System.ServiceModel.ConcurrencyMode.Single>.</span></span> <span data-ttu-id="ea003-224">서비스 B의 <xref:System.ServiceModel.ConcurrencyMode> 특성이 서비스 A의 해당 특성보다 "더 많이 파생된" 상태이므로 <xref:System.ServiceModel.ConcurrencyMode.Single>는 <xref:System.ServiceModel.ServiceBehaviorAttribute>입니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-224">The <xref:System.ServiceModel.ConcurrencyMode> is <xref:System.ServiceModel.ConcurrencyMode.Single>, because <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute on service B is on "more derived" than that on service A.</span></span>  
  
#### <a name="contract-behaviors"></a><span data-ttu-id="ea003-225">계약 동작</span><span class="sxs-lookup"><span data-stu-id="ea003-225">Contract Behaviors</span></span>  
 <span data-ttu-id="ea003-226">지정된 계약의 경우, 해당 인터페이스 및 그 인터페이스 부모의 모든 계약 동작 특성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-226">For a given contract, all contract behavior attributes on that interface and on parents of that interface, are applied.</span></span> <span data-ttu-id="ea003-227">동일한 특성 형식이 상속 계층 구조의 여러 위치에 적용된 경우에는 가장 많이 파생된 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-227">If the same type of attribute is applied at multiple places in the inheritance hierarchy, the most-derived type is used.</span></span>  
  
#### <a name="operation-behaviors"></a><span data-ttu-id="ea003-228">작업 동작</span><span class="sxs-lookup"><span data-stu-id="ea003-228">Operation Behaviors</span></span>  
 <span data-ttu-id="ea003-229">지정된 작업에서 기존의 추상 또는 가상 작업을 재정의하지 않으면 적용되는 상속 규칙은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-229">If a given operation does not override an existing abstract or virtual operation, no inheritance rules apply.</span></span>  
  
 <span data-ttu-id="ea003-230">작업이 기존 작업을 재정의하면 그 작업 및 해당 작업 부모의 모든 작업 동작 특성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-230">If an operation does override an existing operation, then all operation behavior attributes on that operation and on parents of that operation, are applied.</span></span>  <span data-ttu-id="ea003-231">동일한 특성 형식이 상속 계층 구조의 여러 위치에 적용된 경우에는 가장 많이 파생된 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea003-231">If the same type of attribute is applied at multiple places in the inheritance hierarchy, the most-derived type is used.</span></span>
