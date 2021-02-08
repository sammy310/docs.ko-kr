---
description: '자세한 정보: 영 속 인스턴스 컨텍스트'
title: 영속 인스턴스 컨텍스트
ms.date: 03/30/2017
ms.assetid: 97bc2994-5a2c-47c7-927a-c4cd273153df
ms.openlocfilehash: 6f879b2f6c592e5d8f7294405fda403e918070ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793300"
---
# <a name="durable-instance-context"></a><span data-ttu-id="37791-103">영속 인스턴스 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="37791-103">Durable Instance Context</span></span>

<span data-ttu-id="37791-104">이 샘플에서는 영 속 인스턴스 컨텍스트를 사용 하도록 WCF (Windows Communication Foundation) 런타임을 사용자 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37791-104">This sample demonstrates how to customize the Windows Communication Foundation (WCF) runtime to enable durable instance contexts.</span></span> <span data-ttu-id="37791-105">여기서는 SQL Server 2005를 백업 저장소(이 경우 SQL Server 2005 Express)로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-105">It uses SQL Server 2005 as its backing store (SQL Server 2005 Express in this case).</span></span> <span data-ttu-id="37791-106">사용자 지정 스토리지 메커니즘에 액세스하는 방법도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-106">However, it also provides a way to access custom storage mechanisms.</span></span>

> [!NOTE]
> <span data-ttu-id="37791-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="37791-108">이 샘플은 WCF의 채널 계층과 서비스 모델 계층을 모두 확장 하는 과정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-108">This sample involves extending both the channel layer and the service model layer of the WCF.</span></span> <span data-ttu-id="37791-109">따라서 구현 세부 정보를 검토하려면 먼저 기본 개념을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-109">Therefore it is necessary to understand the underlying concepts before going into the implementation details.</span></span>

<span data-ttu-id="37791-110">영속 인스턴스 컨텍스트는 실제 시나리오에서 매우 자주 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-110">Durable instance contexts can be found in the real world scenarios quite often.</span></span> <span data-ttu-id="37791-111">예를 들어 쇼핑 카트 응용 프로그램에는를 통해 쇼핑을 일시 중지 하 고 다른 날에 계속 진행할 수 있는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-111">A shopping cart application, for example, has the ability to pause shopping halfway through and continue it on another day.</span></span> <span data-ttu-id="37791-112">따라서 다음날 장바구니를 방문하면 원래 컨텍스트가 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-112">So that when we visit the shopping cart the next day, our original context is restored.</span></span> <span data-ttu-id="37791-113">서버의 장바구니 애플리케이션에서는 연결이 끊어진 동안 장바구니 인스턴스를 유지 관리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-113">It is important to note that the shopping cart application (on the server) does not maintain the shopping cart instance while we are disconnected.</span></span> <span data-ttu-id="37791-114">대신 해당 상태를 영속 스토리지 매체에 유지하여 복원된 컨텍스트에 새 인스턴스를 생성할 때 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-114">Instead, it persists its state into a durable storage media and uses it when constructing a new instance for the restored context.</span></span> <span data-ttu-id="37791-115">따라서 동일한 컨텍스트에 대해 제공되는 서비스 인스턴스는 이전 인스턴스와 동일하지 않습니다. 즉, 메모리 주소가 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-115">Therefore the service instance that may service for the same context is not the same as the previous instance (that is, it does not have the same memory address).</span></span>

<span data-ttu-id="37791-116">영속 인스턴스 컨텍스트는 클라이언트와 서비스 간에 컨텍스트 ID를 교환하는 작은 프로토콜로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-116">Durable instance context is made possible by a small protocol that exchanges a context ID between the client and service.</span></span> <span data-ttu-id="37791-117">이 컨텍스트 ID는 클라이언트에서 만들어 서비스로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-117">This context ID is created on the client and transmitted to the service.</span></span> <span data-ttu-id="37791-118">서비스 인스턴스가 만들어지면 서비스 런타임에서는 이 컨텍스트 ID에 해당하는 지속적인 상태를 영구 스토리지(기본적으로 SQL Server 2005 데이터베이스)에서 로드하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-118">When the service instance is created, the service runtime tries to load the persisted state that corresponds to this context ID from a persistent storage (by default it is a SQL Server 2005 database).</span></span> <span data-ttu-id="37791-119">상태를 사용할 수 없는 경우 새 인스턴스의 기본 상태는입니다.</span><span class="sxs-lookup"><span data-stu-id="37791-119">If no state is available, the new instance has its default state.</span></span> <span data-ttu-id="37791-120">서비스 구현에서는 사용자 지정 특성으로 서비스 구현 상태를 변경하는 작업을 표시하여 런타임에서 작업을 호출한 후 서비스 인스턴스를 저장할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-120">The service implementation uses a custom attribute to mark operations that change the state of the service implementation so that the runtime can save the service instance after invoking them.</span></span>

<span data-ttu-id="37791-121">앞에서 설명한 대로 다음과 같이 간단하게 두 단계를 구분하여 목표를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-121">By the previous description, two steps can easily be distinguished to achieve the goal:</span></span>

1. <span data-ttu-id="37791-122">네트워크를 통해 컨텍스트 ID를 전달하는 메시지를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-122">Change the message that goes on the wire to carry the context ID.</span></span>

2. <span data-ttu-id="37791-123">서비스 로컬 동작을 변경하여 사용자 지정 인스턴스 논리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-123">Change the service local behavior to implement custom instancing logic.</span></span>

<span data-ttu-id="37791-124">목록의 첫 번째 항목은 통신 중인 메시지에 영향을 주므로 사용자 지정 채널로 구현 하 고 채널 계층에 후크 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-124">Because the first one in the list affects the messages on the wire, it should be implemented as a custom channel and be hooked up to the channel layer.</span></span> <span data-ttu-id="37791-125">후자는 서비스 로컬 동작에만 영향을 주므로 여러 서비스 확장 지점을 확장하여 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-125">The latter only affects the service local behavior and therefore can be implemented by extending several service extensibility points.</span></span> <span data-ttu-id="37791-126">다음 단원에서는 각 확장에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-126">In the next few sections, each of these extensions are discussed.</span></span>

## <a name="durable-instancecontext-channel"></a><span data-ttu-id="37791-127">영속 InstanceContext 채널</span><span class="sxs-lookup"><span data-stu-id="37791-127">Durable InstanceContext Channel</span></span>

<span data-ttu-id="37791-128">먼저 채널 계층 확장을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-128">The first thing to look at is a channel layer extension.</span></span> <span data-ttu-id="37791-129">사용자 지정 채널을 기록하는 첫 단계는 채널의 통신 구조를 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37791-129">The first step in writing a custom channel is to decide the communication structure of the channel.</span></span> <span data-ttu-id="37791-130">새 유선 프로토콜이 도입 될 때 채널은 채널 스택의 거의 모든 채널에서 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-130">As a new wire protocol is being introduced, the channel should work with almost any other channel in the channel stack.</span></span> <span data-ttu-id="37791-131">따라서 모든 메시지 교환 패턴을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-131">Therefore it should support all the message exchange patterns.</span></span> <span data-ttu-id="37791-132">그러나 채널의 핵심 기능은 통신 구조와 관계없이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-132">However, the core functionality of the channel is the same regardless of its communication structure.</span></span> <span data-ttu-id="37791-133">즉, 클라이언트에서는 메시지에 컨텍스트 ID를 쓰고 서버에서는 메시지로부터 이 컨텍스트 ID를 읽어 상위 수준으로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-133">More specifically, from the client it should write the context ID to the messages and from the service it should read this context ID from the messages and pass it to the upper levels.</span></span> <span data-ttu-id="37791-134">따라서 모든 영속 인스턴스 컨텍스트 채널 구현에서 추상 기본 클래스 역할을 하는 `DurableInstanceContextChannelBase` 클래스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="37791-134">Because of that, a `DurableInstanceContextChannelBase` class is created that acts as the abstract base class for all durable instance context channel implementations.</span></span> <span data-ttu-id="37791-135">이 클래스에는 메시지에서 컨텍스트 정보를 적용하고 읽는 일반적인 상태 컴퓨터 관리 기능과 보호된 멤버 두 개가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-135">This class contains the common state machine management functions and two protected members to apply and read the context information to and from messages.</span></span>

```csharp
class DurableInstanceContextChannelBase
{
  //…
  protected void ApplyContext(Message message)
  {
    //…
  }
  protected string ReadContextId(Message message)
  {
    //…
  }
}
```

<span data-ttu-id="37791-136">이러한 두 메서드는 `IContextManager` 구현을 사용하여 메시지에서 컨텍스트 ID를 쓰고 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-136">These two methods make use of `IContextManager` implementations to write and read the context ID to or from the message.</span></span> <span data-ttu-id="37791-137">`IContextManager`는 모든 컨텍스트 관리자에 대 한 계약을 정의 하는 데 사용 되는 사용자 지정 인터페이스입니다. 채널은 사용자 지정 SOAP 헤더에 컨텍스트 ID를 포함 하거나 HTTP 쿠키 헤더에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-137">(`IContextManager` is a custom interface used to define the contract for all context managers.) The channel can either include the context ID in a custom SOAP header or in an HTTP cookie header.</span></span> <span data-ttu-id="37791-138">각 컨텍스트 관리자 구현은 모든 컨텍스트 관리자의 공통 기능이 포함된 `ContextManagerBase` 클래스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-138">Each context manager implementation inherits from the `ContextManagerBase` class that contains the common functionality for all context managers.</span></span> <span data-ttu-id="37791-139">이 클래스의 `GetContextId` 메서드는 클라이언트에서 컨텍스트 ID를 가져오는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-139">The `GetContextId` method in this class is used to originate the context ID from the client.</span></span> <span data-ttu-id="37791-140">컨텍스트 ID를 처음으로 가져오면 이 메서드는 원격 엔드포인트 주소로 이름이 생성되는 텍스트 파일에 컨텍스트 ID를 저장합니다. 일반적인 URI에서 잘못된 파일 이름 문자는 @ 문자로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="37791-140">When a context ID is originated for the first time, this method saves it into a text file whose name is constructed by the remote endpoint address (the invalid file name characters in the typical URIs are replaced with @ characters).</span></span>

<span data-ttu-id="37791-141">나중에 동일한 원격 엔드포인트에 컨텍스트 ID가 필요하면 적합한 파일이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-141">Later when the context ID is required for the same remote endpoint, it checks whether an appropriate file exists.</span></span> <span data-ttu-id="37791-142">파일이 있으면 컨텍스트 ID를 읽어 반환하고,</span><span class="sxs-lookup"><span data-stu-id="37791-142">If it does, it reads the context ID and returns.</span></span> <span data-ttu-id="37791-143">그렇지 않으면 새로 생성한 컨텍스트 ID를 반환하여 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-143">Otherwise it returns a newly generated context ID and saves it to a file.</span></span> <span data-ttu-id="37791-144">기본 구성을 사용 하 여 이러한 파일은 현재 사용자의 임시 디렉터리에 있는 ContextStore 라는 디렉터리에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-144">With the default configuration, these files are placed in a directory called ContextStore, which resides in the current user's temp directory.</span></span> <span data-ttu-id="37791-145">그러나 이 위치는 바인딩 요소를 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-145">However this location is configurable using the binding element.</span></span>

<span data-ttu-id="37791-146">컨텍스트 ID를 전송하는 데 사용되는 메커니즘은 구성 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-146">The mechanism used to transport the context ID is configurable.</span></span> <span data-ttu-id="37791-147">이 메커니즘은 HTTP 쿠키 헤더 또는 사용자 지정 SOAP 헤더에 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-147">It could be either written to the HTTP cookie header or to a custom SOAP header.</span></span> <span data-ttu-id="37791-148">사용자 지정 SOAP 헤더 접근 방식에서는 HTTP가 아닌 프로토콜(예: TCP 또는 명명된 파이프)과 함께 이 프로토콜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-148">The custom SOAP header approach makes it possible to use this protocol with non-HTTP protocols (for example, TCP or Named Pipes).</span></span> <span data-ttu-id="37791-149">`MessageHeaderContextManager`와 `HttpCookieContextManager`라는 클래스에서 이 두 옵션을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-149">There are two classes, namely `MessageHeaderContextManager` and `HttpCookieContextManager`, which implement these two options.</span></span>

<span data-ttu-id="37791-150">두 클래스 모두 컨텍스트 ID를 메시지에 적절하게 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-150">Both of them write the context ID to the message appropriately.</span></span> <span data-ttu-id="37791-151">예를 들어, `MessageHeaderContextManager` 클래스는 `WriteContext` 메서드의 SOAP 헤더에 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-151">For example, the `MessageHeaderContextManager` class writes it to a SOAP header in the `WriteContext` method.</span></span>

```csharp
public override void WriteContext(Message message)
{
  string contextId = this.GetContextId();

  MessageHeader contextHeader =
    MessageHeader.CreateHeader(DurableInstanceContextUtility.HeaderName,
      DurableInstanceContextUtility.HeaderNamespace,
      contextId,
      true);

  message.Headers.Add(contextHeader);
}
```

<span data-ttu-id="37791-152">`ApplyContext` 클래스의 `ReadContextId` 및 `DurableInstanceContextChannelBase` 메서드는 각각 `IContextManager.ReadContext` 및 `IContextManager.WriteContext`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-152">Both the `ApplyContext` and `ReadContextId` methods in the `DurableInstanceContextChannelBase` class invoke the `IContextManager.ReadContext` and `IContextManager.WriteContext`, respectively.</span></span> <span data-ttu-id="37791-153">그러나 `DurableInstanceContextChannelBase` 클래스로 이러한 컨텍스트 관리자를 직접 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-153">However, these context managers are not directly created by the `DurableInstanceContextChannelBase` class.</span></span> <span data-ttu-id="37791-154">대신 `ContextManagerFactory` 클래스를 사용하여 해당 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-154">Instead it uses the `ContextManagerFactory` class to do that job.</span></span>

```csharp
IContextManager contextManager =
                ContextManagerFactory.CreateContextManager(contextType,
                this.contextStoreLocation,
                this.endpointAddress);
```

<span data-ttu-id="37791-155">`ApplyContext` 메서드는 보내는 채널에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-155">The `ApplyContext` method is invoked by the sending channels.</span></span> <span data-ttu-id="37791-156">이 메서드는 나가는 메시지에 컨텍스트 ID를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-156">It injects the context ID to the outgoing messages.</span></span> <span data-ttu-id="37791-157">`ReadContextId` 메서드는 받는 채널에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-157">The `ReadContextId` method is invoked by the receiving channels.</span></span> <span data-ttu-id="37791-158">이 메서드를 사용하면 들어오는 메시지에서 컨텍스트 ID를 사용할 수 있고 `Properties` 클래스의 `Message` 컬렉션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-158">This method ensures that the context ID is available in the incoming messages and adds it to the `Properties` collection of the `Message` class.</span></span> <span data-ttu-id="37791-159">또한 컨텍스트 ID를 읽는 데 오류가 발생하면 `CommunicationException`이 throw되어 채널이 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-159">It also throws a `CommunicationException` in case of a failure to read the context ID and thus causes the channel to be aborted.</span></span>

```csharp
message.Properties.Add(DurableInstanceContextUtility.ContextIdProperty, contextId);
```

<span data-ttu-id="37791-160">계속하려면 `Properties` 클래스에서 `Message` 컬렉션을 사용하는 방법을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-160">Before proceeding, it is important to understand the usage of the `Properties` collection in the `Message` class.</span></span> <span data-ttu-id="37791-161">일반적으로 이 `Properties` 컬렉션은 채널 계층의 하위 수준에서 상위 수준으로 데이터를 전달할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-161">Typically, this `Properties` collection is used when passing data from lower to the upper levels from the channel layer.</span></span> <span data-ttu-id="37791-162">이렇게 하면 프로토콜 정보에 관계없이 일관된 방식으로 상위 수준에 원하는 데이터를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-162">This way the desired data can be provided to the upper levels in a consistent manner regardless of the protocol details.</span></span> <span data-ttu-id="37791-163">즉, 채널 계층은 SOAP 헤더 또는 HTTP 쿠키 헤더로 컨텍스트 ID를 보내고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-163">In other words, the channel layer can send and receive the context ID either as a SOAP header or an HTTP cookie header.</span></span> <span data-ttu-id="37791-164">그러나 채널 계층을 통해 `Properties` 컬렉션에서 이 정보를 사용할 수 있으므로 상위 수준에서는 해당 정보에 대해 알 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-164">But it is not necessary for the upper levels to know about these details because the channel layer makes this information available in the `Properties` collection.</span></span>

<span data-ttu-id="37791-165">이제 `DurableInstanceContextChannelBase` 클래스를 사용하여 필요한 인터페이스 10개(IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel)를 모두 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-165">Now with the `DurableInstanceContextChannelBase` class in place all ten of the necessary interfaces (IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel) must be implemented.</span></span> <span data-ttu-id="37791-166">사용 가능한 모든 메시지 교환 패턴 (데이터 그램, 단면, 이중 및 해당 세션 변형)과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-166">They resemble every available message exchange pattern (datagram, simplex, duplex, and their sessionful variants).</span></span> <span data-ttu-id="37791-167">이러한 각 구현은 앞에서 설명한 기본 클래스를 상속 하 고 `ApplyContext` 를 `ReadContextId` 적절 하 게 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-167">Each of these implementations inherits the base class previously described and calls `ApplyContext` and `ReadContextId` appropriately.</span></span> <span data-ttu-id="37791-168">예를 들어, IOutputChannel 인터페이스를 구현하는 `DurableInstanceContextOutputChannel`은 메시지를 보내는 각 메서드에서 `ApplyContext` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-168">For example, `DurableInstanceContextOutputChannel` - which implements the IOutputChannel interface - calls the `ApplyContext` method from each method that sends the messages.</span></span>

```csharp
public void Send(Message message, TimeSpan timeout)
{
    // Apply the context information before sending the message.
    this.ApplyContext(message);
    //…
}
```

<span data-ttu-id="37791-169">반면, `DurableInstanceContextInputChannel` 인터페이스를 구현 하는는 `IInputChannel` 각 메서드에서 메서드를 호출 하 여 메시지를 `ReadContextId` 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-169">On the other hand, `DurableInstanceContextInputChannel` - which implements the `IInputChannel` interface - calls the `ReadContextId` method in each method, which receives the messages.</span></span>

```csharp
public Message Receive(TimeSpan timeout)
{
    //…
      ReadContextId(message);
      return message;
}
```

<span data-ttu-id="37791-170">이와 달리 다음 채널 구현에서는 메서드 호출을 채널 스택의 아래 채널에 위임합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-170">Apart from this, these channel implementations delegate the method invocations to the channel below them in the channel stack.</span></span> <span data-ttu-id="37791-171">그러나 세션 변형에는 세션을 만드는 첫 번째 메시지에 대해서만 컨텍스트 ID를 보내고 읽을 수 있는 기본 논리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-171">However, sessionful variants have a basic logic to make sure that the context ID is sent and is read only for the first message that causes the session to be created.</span></span>

```csharp
if (isFirstMessage)
{
//…
    this.ApplyContext(message);
    isFirstMessage = false;
}
```

<span data-ttu-id="37791-172">이러한 채널 구현은 클래스 및 클래스에 의해 WCF 채널 런타임에 적절히 추가 됩니다 `DurableInstanceContextBindingElement` `DurableInstanceContextBindingElementSection` .</span><span class="sxs-lookup"><span data-stu-id="37791-172">These channel implementations are then added to the WCF channel runtime by the `DurableInstanceContextBindingElement` class and `DurableInstanceContextBindingElementSection` class appropriately.</span></span> <span data-ttu-id="37791-173">바인딩 요소 및 바인딩 요소에 대 한 자세한 내용은 [HttpCookieSession](httpcookiesession.md) channel 샘플 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37791-173">See the [HttpCookieSession](httpcookiesession.md) channel sample documentation for more details about binding elements and binding element sections.</span></span>

## <a name="service-model-layer-extensions"></a><span data-ttu-id="37791-174">서비스 모델 계층 확장명</span><span class="sxs-lookup"><span data-stu-id="37791-174">Service Model Layer Extensions</span></span>

<span data-ttu-id="37791-175">이제 컨텍스트 ID가 채널 계층을 통해 이동했으므로 서비스 동작을 구현하여 인스턴스를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-175">Now that the context ID has traveled through the channel layer, the service behavior can be implemented to customize the instantiation.</span></span> <span data-ttu-id="37791-176">이 샘플에서는 스토리지 관리자를 사용하여 영구 스토리지에서 상태를 로드하고 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-176">In this sample, a storage manager is used to load and save state from or to the persistent store.</span></span> <span data-ttu-id="37791-177">앞에서 설명한 대로 이 샘플에서는 SQL Server 2005를 백업 스토리지로 사용하는 스토리지 관리자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-177">As explained previously, this sample provides a storage manager that uses SQL Server 2005 as its backing store.</span></span> <span data-ttu-id="37791-178">그러나 이 확장에 사용자 지정 스토리지 메커니즘을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-178">However, it is also possible to add custom storage mechanisms to this extension.</span></span> <span data-ttu-id="37791-179">해당 작업을 수행하기 위해 모든 스토리지 관리자에 의해 구현되어야 하는 공용 인터페이스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-179">To do that a public interface is declared, which must be implemented by all storage managers.</span></span>

```csharp
public interface IStorageManager
{
    object GetInstance(string contextId, Type type);
    void SaveInstance(string contextId, object state);
}
```

<span data-ttu-id="37791-180">`SqlServerStorageManager` 클래스에는 기본 `IStorageManager` 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-180">The `SqlServerStorageManager` class contains the default `IStorageManager` implementation.</span></span> <span data-ttu-id="37791-181">해당 `SaveInstance` 메서드에서 지정 된 개체는 XmlSerializer를 사용 하 여 serialize 되 고 SQL Server 데이터베이스에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-181">In its `SaveInstance` method, the given object is serialized using the XmlSerializer and is saved to the SQL Server database.</span></span>

```csharp
XmlSerializer serializer = new XmlSerializer(state.GetType());
string data;

using (StringWriter writer = new StringWriter(CultureInfo.InvariantCulture))
{
    serializer.Serialize(writer, state);
    data = writer.ToString();
}

using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string update = @"UPDATE Instances SET Instance = @instance WHERE ContextId = @contextId";

    using (SqlCommand command = new SqlCommand(update, connection))
    {
        command.Parameters.Add("@instance", SqlDbType.VarChar, 2147483647).Value = data;
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;

        int rows = command.ExecuteNonQuery();

        if (rows == 0)
        {
            string insert = @"INSERT INTO Instances(ContextId, Instance) VALUES(@contextId, @instance)";
            command.CommandText = insert;
            command.ExecuteNonQuery();
        }
    }
}
```

<span data-ttu-id="37791-182">메서드에서는 `GetInstance` 지정 된 컨텍스트 ID에 대해 serialize 된 데이터를 읽고이를 통해 생성 된 개체를 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-182">In the `GetInstance` method, the serialized data is read for a given context ID and the object constructed from it is returned to the caller.</span></span>

```csharp
object data;
using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string select = "SELECT Instance FROM Instances WHERE ContextId = @contextId";
    using (SqlCommand command = new SqlCommand(select, connection))
    {
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;
        data = command.ExecuteScalar();
    }
}

if (data != null)
{
    XmlSerializer serializer = new XmlSerializer(type);
    using (StringReader reader = new StringReader((string)data))
    {
        object instance = serializer.Deserialize(reader);
        return instance;
    }
}
```

<span data-ttu-id="37791-183">이러한 스토리지 관리자의 사용자는 해당 관리자를 직접 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-183">Users of these storage managers are not supposed to instantiate them directly.</span></span> <span data-ttu-id="37791-184">따라서 스토리지 관리자 생성 정보에서 추출한 `StorageManagerFactory` 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-184">They use the `StorageManagerFactory` class, which abstracts from the storage manager creation details.</span></span> <span data-ttu-id="37791-185">이 클래스에는 지정된 스토리지 관리자 형식의 인스턴스를 만드는 정적 멤버인 `GetStorageManager`가 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-185">This class has one static member, `GetStorageManager`, which creates an instance of a given storage manager type.</span></span> <span data-ttu-id="37791-186">형식 매개 변수가 `null`이면 이 메서드는 기본 `SqlServerStorageManager` 클래스의 인스턴스를 만들어 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-186">If the type parameter is `null`, this method creates an instance of the default `SqlServerStorageManager` class and returns it.</span></span> <span data-ttu-id="37791-187">또한 지정된 형식의 유효성을 검사하여 `IStorageManager` 인터페이스가 구현되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-187">It also validates the given type to make sure that it implements the `IStorageManager` interface.</span></span>

```csharp
public static IStorageManager GetStorageManager(Type storageManagerType)
{
IStorageManager storageManager = null;

if (storageManagerType == null)
{
    return new SqlServerStorageManager();
}
else
{
    object obj = Activator.CreateInstance(storageManagerType);

    // Throw if the specified storage manager type does not
    // implement IStorageManager.
    if (obj is IStorageManager)
    {
        storageManager = (IStorageManager)obj;
    }
    else
    {
        throw new InvalidOperationException(
                  ResourceHelper.GetString("ExInvalidStorageManager"));
    }

    return storageManager;
}
}
```

<span data-ttu-id="37791-188">영구 스토리지에서 인터페이스를 읽고 쓰는 데 필요한 인프라를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-188">The necessary infrastructure to read and write instances from the persistent storage is implemented.</span></span> <span data-ttu-id="37791-189">이제 서비스 동작을 변경하는 데 필요한 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-189">Now the necessary steps to change the service behavior have to be taken.</span></span>

<span data-ttu-id="37791-190">이 프로세스의 첫 번째 단계로 채널 계층을 통해 현재 InstanceContext에 도달한 컨텍스트 ID를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-190">As the first step of this process we have to save the context ID, which came through the channel layer to the current InstanceContext.</span></span> <span data-ttu-id="37791-191">InstanceContext는 WCF 디스패처와 서비스 인스턴스 간의 링크 역할을 하는 런타임 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="37791-191">InstanceContext is a runtime component that acts as the link between the WCF dispatcher and the service instance.</span></span> <span data-ttu-id="37791-192">이 구성 요소를 사용하면 서비스 인스턴스에 추가 상태 및 동작을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-192">It can be used to provide additional state and behavior to the service instance.</span></span> <span data-ttu-id="37791-193">세션 통신에서는 첫 번째 메시지에 대해서만 컨텍스트 ID를 전송하기 때문에 이 구성 요소가 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-193">This is essential because in sessionful communication the context ID is sent only with the first message.</span></span>

<span data-ttu-id="37791-194">WCF를 사용 하면 확장 가능한 개체 패턴을 사용 하 여 새 상태 및 동작을 추가 하 여 InstanceContext 런타임 구성 요소를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-194">WCF allows extending its InstanceContext runtime component by adding a new state and behavior using its extensible object pattern.</span></span> <span data-ttu-id="37791-195">확장 가능한 개체 패턴은 새 기능으로 기존 런타임 클래스를 확장 하거나 개체에 새 상태 기능을 추가 하기 위해 WCF에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-195">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="37791-196">확장 가능한 개체 패턴에는 Iextensibleobject<t> \<T> , iextension \<T> 및 IExtensionCollection의 세 가지 인터페이스가 있습니다 \<T> .</span><span class="sxs-lookup"><span data-stu-id="37791-196">There are three interfaces in the extensible object pattern - IExtensibleObject\<T>, IExtension\<T>, and IExtensionCollection\<T>:</span></span>

- <span data-ttu-id="37791-197">Iextensibleobject<t> \<T> 인터페이스는 해당 기능을 사용자 지정 하는 확장을 허용 하는 개체에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-197">The IExtensibleObject\<T> interface is implemented by objects that allow extensions that customize their functionality.</span></span>

- <span data-ttu-id="37791-198">IExtension \<T> 인터페이스는 T 형식의 클래스를 확장 하는 개체에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-198">The IExtension\<T> interface is implemented by objects that are extensions of classes of type T.</span></span>

- <span data-ttu-id="37791-199">IExtensionCollection \<T> 인터페이스는 형식으로 Iextension을 검색할 수 있도록 하는 iextensions의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="37791-199">The IExtensionCollection\<T> interface is a collection of IExtensions that allows for retrieving IExtensions by their type.</span></span>

<span data-ttu-id="37791-200">따라서 IExtension 인터페이스를 구현하고 필요한 상태를 정의하는 InstanceContextExtension 클래스를 만들어 컨텍스트 ID를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-200">Therefore an InstanceContextExtension class should be created that implements the IExtension interface and defines the required state to save the context ID.</span></span> <span data-ttu-id="37791-201">이 클래스는 사용할 스토리지 관리자를 보유하는 상태도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-201">This class also provides the state to hold the storage manager being used.</span></span> <span data-ttu-id="37791-202">새 상태가 저장된 다음에는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-202">Once the new state is saved, it should not be possible to modify it.</span></span> <span data-ttu-id="37791-203">따라서 상태가 생성되어 인스턴스에 제공되고 저장된 다음에는 읽기 전용 속성으로만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-203">Therefore the state is provided and saved to the instance at the time it is being constructed and then only accessible using read-only properties.</span></span>

```csharp
// Constructor
public DurableInstanceContextExtension(string contextId,
            IStorageManager storageManager)
{
    this.contextId = contextId;
    this.storageManager = storageManager;
}

// Read only properties
public string ContextId
{
    get { return this.contextId; }
}

public IStorageManager StorageManager
{
    get { return this.storageManager; }
}
```

<span data-ttu-id="37791-204">InstanceContextInitializer 클래스는 IInstanceContextInitializer 인터페이스를 구현하고 생성되는 InstanceContext의 Extensions 컬렉션에 인스턴스 컨텍스트 확장명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-204">The InstanceContextInitializer class implements the IInstanceContextInitializer interface and adds the instance context extension to the Extensions collection of the InstanceContext being constructed.</span></span>

```csharp
public void Initialize(InstanceContext instanceContext, Message message)
{
    string contextId =
  (string)message.Properties[DurableInstanceContextUtility.ContextIdProperty];

    DurableInstanceContextExtension extension =
                new DurableInstanceContextExtension(contextId,
                     storageManager);
    instanceContext.Extensions.Add(extension);
}
```

<span data-ttu-id="37791-205">앞에서 설명한 대로 `Properties` 클래스의 `Message` 컬렉션에서 컨텍스트 ID를 읽고 확장 클래스의 생성자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-205">As described earlier the context ID is read from the `Properties` collection of the `Message` class and passed to the constructor of the extension class.</span></span> <span data-ttu-id="37791-206">이 샘플에서는 계층 간에 일관된 방식으로 정보를 교환할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37791-206">This demonstrates how information can be exchanged between the layers in a consistent manner.</span></span>

<span data-ttu-id="37791-207">다음으로 중요한 단계는 서비스 인스턴스 생성 프로세스를 재정의하는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="37791-207">The next important step is overriding the service instance creation process.</span></span> <span data-ttu-id="37791-208">WCF를 사용 하면 사용자 지정 인스턴스화 동작을 구현 하 고 IInstanceProvider 인터페이스를 사용 하 여 런타임에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-208">WCF allows implementing custom instantiation behaviors and hooking them up to the runtime using the IInstanceProvider interface.</span></span> <span data-ttu-id="37791-209">이 작업을 수행하기 위해 새 `InstanceProvider` 클래스가 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-209">The new `InstanceProvider` class is implemented to do that job.</span></span> <span data-ttu-id="37791-210">인스턴스 공급자에서 예상한 서비스 형식이 생성자에서 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-210">The service type expected from the instance provider is accepted in the constructor.</span></span> <span data-ttu-id="37791-211">이 서비스 유형은 나중에 새 인스턴스를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-211">Later this is used to create new instances.</span></span> <span data-ttu-id="37791-212">구현에서 `GetInstance` 지속형 인스턴스를 찾기 위해 저장소 관리자의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="37791-212">In the `GetInstance` implementation, an instance of a storage manager is created looking for a persisted instance.</span></span> <span data-ttu-id="37791-213">가 반환 되는 경우 `null` 서비스 형식의 새 인스턴스가 인스턴스화되고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-213">If it returns `null`, then a new instance of the service type is instantiated and returned to the caller.</span></span>

```csharp
public object GetInstance(InstanceContext instanceContext, Message message)
{
    object instance = null;

    DurableInstanceContextExtension extension =
    instanceContext.Extensions.Find<DurableInstanceContextExtension>();

    string contextId = extension.ContextId;
    IStorageManager storageManager = extension.StorageManager;

    instance = storageManager.GetInstance(contextId, serviceType);

    instance ??= Activator.CreateInstance(serviceType);
    return instance;
}
```

<span data-ttu-id="37791-214">그 다음으로 중요 한 단계는 `InstanceContextExtension` `InstanceContextInitializer` 서비스 모델 런타임에, 및 클래스를 설치 하는 것입니다 `InstanceProvider` .</span><span class="sxs-lookup"><span data-stu-id="37791-214">The next important step is to install the `InstanceContextExtension`, `InstanceContextInitializer`, and `InstanceProvider` classes into the service model runtime.</span></span> <span data-ttu-id="37791-215">사용자 지정 특성을 사용하면 서비스 구현 클래스를 표시하여 동작을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-215">A custom attribute could be used to mark the service implementation classes to install the behavior.</span></span> <span data-ttu-id="37791-216">`DurableInstanceContextAttribute`에는 이 특성의 구현이 포함되어 있으며 `IServiceBehavior` 인터페이스를 구현하여 전체 서비스 런타임을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-216">The `DurableInstanceContextAttribute` contains the implementation for this attribute and it implements the `IServiceBehavior` interface to extend the entire service runtime.</span></span>

<span data-ttu-id="37791-217">이 클래스에는 사용할 스토리지 관리자의 형식을 허용하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-217">This class has a property that accepts the type of the storage manager to be used.</span></span> <span data-ttu-id="37791-218">이러한 방식으로 구현을 통해 사용자는 고유한 `IStorageManager` 구현을이 특성의 매개 변수로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-218">In this way, the implementation enables the users to specify their own `IStorageManager` implementation as parameter of this attribute.</span></span>

<span data-ttu-id="37791-219">구현에서 `ApplyDispatchBehavior` `InstanceContextMode` 현재 특성의를 `ServiceBehavior` 확인 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="37791-219">In the `ApplyDispatchBehavior` implementation, the `InstanceContextMode` of the current `ServiceBehavior` attribute is being verified.</span></span> <span data-ttu-id="37791-220">이 속성을 Singleton으로 설정하면 영속 인스턴스를 사용할 수 없으며 `InvalidOperationException`이 throw되어 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="37791-220">If this property is set to Singleton, enabling durable instancing is not possible and an `InvalidOperationException` is thrown to notify the host.</span></span>

```csharp
ServiceBehaviorAttribute serviceBehavior =
    serviceDescription.Behaviors.Find<ServiceBehaviorAttribute>();

if (serviceBehavior != null &&
     serviceBehavior.InstanceContextMode == InstanceContextMode.Single)
{
    throw new InvalidOperationException(
       ResourceHelper.GetString("ExSingletonInstancingNotSupported"));
}
```

<span data-ttu-id="37791-221">그런 다음 스토리지 관리자, 인스턴스 컨텍스트 이니셜라이저 및 인스턴스 공급자의 인스턴스가 생성되고 모든 엔드포인트에 대해 만들어진 `DispatchRuntime`에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-221">After this the instances of the storage manager, instance context initializer, and the instance provider are created and installed in the `DispatchRuntime` created for every endpoint.</span></span>

```csharp
IStorageManager storageManager =
    StorageManagerFactory.GetStorageManager(storageManagerType);

InstanceContextInitializer contextInitializer =
    new InstanceContextInitializer(storageManager);

InstanceProvider instanceProvider =
    new InstanceProvider(description.ServiceType);

foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
{
    ChannelDispatcher cd = cdb as ChannelDispatcher;

    if (cd != null)
    {
        foreach (EndpointDispatcher ed in cd.Endpoints)
        {
            ed.DispatchRuntime.InstanceContextInitializers.Add(contextInitializer);
            ed.DispatchRuntime.InstanceProvider = instanceProvider;
        }
    }
}
```

<span data-ttu-id="37791-222">지금까지의 내용을 요약하면 이 샘플에서는 사용자 지정 컨텍스트 ID 교환을 위해 사용자 지정 유선 프로토콜을 사용하는 채널을 생성하고 기본 인스턴스 동작을 덮어써서 영구 스토리지에서 인스턴스를 로드했습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-222">In summary so far, this sample has produced a channel that enabled the custom wire protocol for custom context ID exchange and it also overwrites the default instancing behavior to load the instances from the persistent storage.</span></span>

<span data-ttu-id="37791-223">이제 서비스 인스턴스를 영구 스토리지에 저장하는 방법만 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-223">What is left is a way to save the service instance to the persistent storage.</span></span> <span data-ttu-id="37791-224">앞에서 설명한 대로 상태를 저장하는 데 필요한 기능은 `IStorageManager`에 이미 구현되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-224">As discussed previously, there is already the required functionality to save the state in an `IStorageManager` implementation.</span></span> <span data-ttu-id="37791-225">이제이를 WCF 런타임과 통합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-225">We now must integrate this with the WCF runtime.</span></span> <span data-ttu-id="37791-226">서비스 구현 클래스의 메서드에 적용할 수 있는 또 다른 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-226">Another attribute is required that is applicable to the methods in the service implementation class.</span></span> <span data-ttu-id="37791-227">이 특성은 서비스 인스턴스의 상태를 변경하는 메서드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-227">This attribute is supposed to be applied to the methods that change the state of the service instance.</span></span>

<span data-ttu-id="37791-228">`SaveStateAttribute` 클래스가 이 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-228">The `SaveStateAttribute` class implements this functionality.</span></span> <span data-ttu-id="37791-229">또한 `IOperationBehavior` 각 작업에 대해 WCF 런타임을 수정 하는 클래스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-229">It also implements `IOperationBehavior` class to modify the WCF runtime for each operation.</span></span> <span data-ttu-id="37791-230">메서드가이 특성으로 표시 된 경우 WCF 런타임은 `ApplyBehavior` 적절 한가 생성 되는 동안 메서드를 호출 합니다 `DispatchOperation` .</span><span class="sxs-lookup"><span data-stu-id="37791-230">When a method is marked with this attribute, the WCF runtime invokes the `ApplyBehavior` method while the appropriate `DispatchOperation` is being constructed.</span></span> <span data-ttu-id="37791-231">이 메서드 구현에는 한 줄의 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-231">There is a single line of code in this method implementation:</span></span>

```csharp
dispatch.Invoker = new OperationInvoker(dispatch.Invoker);
```

<span data-ttu-id="37791-232">이 명령은 `OperationInvoker` 형식의 인스턴스를 만들어 생성할 `Invoker`의 `DispatchOperation` 속성에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-232">This instruction creates an instance of `OperationInvoker` type and assigns it to the `Invoker` property of the `DispatchOperation` being constructed.</span></span> <span data-ttu-id="37791-233">`OperationInvoker` 클래스는 `DispatchOperation`에 대해 생성된 기본 작업 호출자의 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="37791-233">The `OperationInvoker` class is a wrapper for the default operation invoker created for the `DispatchOperation`.</span></span> <span data-ttu-id="37791-234">이 클래스는 `IOperationInvoker` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-234">This class implements the `IOperationInvoker` interface.</span></span> <span data-ttu-id="37791-235">`Invoke`메서드 구현에서 실제 메서드 호출은 내부 작업 호출자에 게 위임 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-235">In the `Invoke` method implementation, the actual method invocation is delegated to the inner operation invoker.</span></span> <span data-ttu-id="37791-236">그러나 결과를 반환하기 전에 `InstanceContext`의 스토리지 관리자를 사용하여 서비스 인스턴스를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-236">However, before returning the results the storage manager in the `InstanceContext` is used to save the service instance.</span></span>

```csharp
object result = innerOperationInvoker.Invoke(instance,
    inputs, out outputs);

// Save the instance using the storage manager saved in the
// current InstanceContext.
InstanceContextExtension extension =
    OperationContext.Current.InstanceContext.Extensions.Find<InstanceContextExtension>();

extension.StorageManager.SaveInstance(extension.ContextId, instance);
return result;
```

## <a name="using-the-extension"></a><span data-ttu-id="37791-237">확장 사용</span><span class="sxs-lookup"><span data-stu-id="37791-237">Using the Extension</span></span>

<span data-ttu-id="37791-238">채널 계층과 서비스 모델 계층 확장이 모두 수행 되며 이제 WCF 응용 프로그램에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-238">Both the channel layer and service model layer extensions are done and they can now be used in WCF applications.</span></span> <span data-ttu-id="37791-239">서비스는 사용자 지정 바인딩을 사용 하 여 채널 스택에 채널을 추가한 다음 서비스 구현 클래스를 적절 한 특성으로 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-239">Services must add the channel into the channel stack using a custom binding and then mark the service implementation classes with the appropriate attributes.</span></span>

```csharp
[DurableInstanceContext]
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]
public class ShoppingCart : IShoppingCart
{
//…
     [SaveState]
     public int AddItem(string item)
     {
         //…
     }
//…
 }
```

<span data-ttu-id="37791-240">클라이언트 애플리케이션에서는 사용자 지정 바인딩을 사용하여 채널 스택에 DurableInstanceContextChannel을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-240">Client applications must add the DurableInstanceContextChannel into the channel stack using a custom binding.</span></span> <span data-ttu-id="37791-241">구성 파일에서 선언적으로 채널을 구성하려면 바인딩 요소 섹션을 바인딩 요소 확장명 컬렉션에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-241">To configure the channel declaratively in the configuration file, the binding element section has to be added to the binding element extensions collection.</span></span>

```xml
<system.serviceModel>
 <extensions>
   <bindingElementExtensions>
     <add name="durableInstanceContext"
type="Microsoft.ServiceModel.Samples.DurableInstanceContextBindingElementSection, DurableInstanceContextExtension, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>
   </bindingElementExtensions>
 </extensions>
</system.serviceModel>
```

<span data-ttu-id="37791-242">이제 다른 표준 바인딩 요소와 마찬가지로 바인딩 요소를 사용자 지정 바인딩에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-242">Now the binding element can be used with a custom binding just like other standard binding elements:</span></span>

```xml
<bindings>
 <customBinding>
   <binding name="TextOverHttp">
     <durableInstanceContext contextType="HttpCookie"/>
     <reliableSession />
     <textMessageEncoding />
     <httpTransport />
   </binding>
 </customBinding>
</bindings>
```

## <a name="conclusion"></a><span data-ttu-id="37791-243">결론</span><span class="sxs-lookup"><span data-stu-id="37791-243">Conclusion</span></span>

<span data-ttu-id="37791-244">이 샘플에서는 사용자 지정 프로토콜 채널을 만드는 방법 및 서비스 동작을 사용자 지정하여 사용하는 방법을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-244">This sample showed how to create a custom protocol channel and how to customize the service behavior to enable it.</span></span>

<span data-ttu-id="37791-245">사용자가 구성 섹션을 사용하여 `IStorageManager` 구현을 지정할 수 있도록 하면 확장을 더 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-245">The extension can be further improved by letting users specify the `IStorageManager` implementation using a configuration section.</span></span> <span data-ttu-id="37791-246">이렇게 하면 서비스 코드를 다시 컴파일하지 않고도 백업 저장소를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-246">This makes it possible to modify the backing store without recompiling the service code.</span></span>

<span data-ttu-id="37791-247">또한 인스턴스의 상태를 캡슐화하는 클래스(예: `StateBag`)를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-247">Furthermore you could try to implement a class (for example, `StateBag`), which encapsulates the state of the instance.</span></span> <span data-ttu-id="37791-248">이 클래스는 상태가 변경될 때마다 상태를 유지하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-248">That class is responsible for persisting the state whenever it changes.</span></span> <span data-ttu-id="37791-249">따라서 `SaveState` 특성을 사용하지 않고 유지 작업을 보다 정확하게 수행할 수 있습니다. 예를 들어, 메서드를 호출할 때마다 `SaveState` 특성으로 상태를 저장하는 대신 상태가 실제로 변경될 때 해당 상태를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-249">This way you can avoid using the `SaveState` attribute and perform the persisting work more accurately (for example, you could persist the state when the state is actually changed rather than saving it each time when a method with the `SaveState` attribute is called).</span></span>

<span data-ttu-id="37791-250">샘플을 실행하면 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37791-250">When you run the sample, the following output is displayed.</span></span> <span data-ttu-id="37791-251">클라이언트는 장바구니에 항목 두 개를 추가하고 장바구니의 항목 목록을 서비스에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37791-251">The client adds two items to its shopping cart and then gets the list of items in its shopping cart from the service.</span></span> <span data-ttu-id="37791-252">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="37791-252">Press ENTER in each console window to shut down the service and client.</span></span>

```console
Enter the name of the product: apples
Enter the name of the product: bananas

Shopping cart currently contains the following items.
apples
bananas
Press ENTER to shut down client
```

> [!NOTE]
> <span data-ttu-id="37791-253">서비스를 다시 빌드하면 데이터베이스 파일을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="37791-253">Rebuilding the service overwrites the database file.</span></span> <span data-ttu-id="37791-254">샘플을 여러 번 실행하는 동안 상태를 유지하려면 실행할 때마다 샘플을 다시 빌드하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-254">To observe state preserved across multiple runs of the sample, be sure not to rebuild the sample between runs.</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="37791-255">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="37791-255">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="37791-256">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-256">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="37791-257">솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="37791-257">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="37791-258">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="37791-258">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!NOTE]
> <span data-ttu-id="37791-259">이 샘플을 실행하려면 SQL Server 2005 또는 SQL Express 2005를 실행하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-259">You must be running SQL Server 2005 or SQL Express 2005 to run this sample.</span></span> <span data-ttu-id="37791-260">SQL Server 2005를 실행하고 있는 경우 서비스의 연결 문자열 구성을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-260">If you are running SQL Server 2005, you must modify the configuration of the service's connection string.</span></span> <span data-ttu-id="37791-261">다중 컴퓨터 구성에서 실행하는 경우 SQL Server는 서버 컴퓨터에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-261">When running cross-machine, SQL Server is only required on the server machine.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37791-262">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-262">The samples may already be installed on your machine.</span></span> <span data-ttu-id="37791-263">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="37791-263">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="37791-264">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="37791-264">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="37791-265">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37791-265">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Durable`
