---
title: 세션의 대기 중인 메시지 그룹화
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- queues [WCF]. grouping messages
ms.assetid: 63b23b36-261f-4c37-99a2-cc323cd72a1a
ms.openlocfilehash: 995697e618ff5d56a719efc5d69b97583733d980
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70892744"
---
# <a name="grouping-queued-messages-in-a-session"></a><span data-ttu-id="edca0-102">세션의 대기 중인 메시지 그룹화</span><span class="sxs-lookup"><span data-stu-id="edca0-102">Grouping Queued Messages in a Session</span></span>
<span data-ttu-id="edca0-103">WCF (Windows Communication Foundation)는 단일 수신 응용 프로그램에서 처리 하기 위해 관련 메시지 집합을 그룹화 할 수 있는 세션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-103">Windows Communication Foundation (WCF) provides a session that allows you to group a set of related messages together for processing by a single receiving application.</span></span> <span data-ttu-id="edca0-104">세션의 일부인 메시지는 동일한 트랜잭션의 일부여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-104">Messages that are part of a session must be part of the same transaction.</span></span> <span data-ttu-id="edca0-105">모든 메시지가 동일한 트랜잭션의 일부이므로, 하나의 메시지가 처리되지 않으면 전체 세션이 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-105">Because all messages are part of the same transaction, if one message fails to be processed the entire session is rolled back.</span></span> <span data-ttu-id="edca0-106">세션은 배달 못 한 편지 큐 및 포이즌 큐와 관련하여 유사하게 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-106">Sessions have similar behaviors with regard to dead-letter queues and poison queues.</span></span> <span data-ttu-id="edca0-107">세션에 대해 구성된 대기 중인 바인딩에 대해 설정된 TTL(Time to Live) 속성은 세션에 전체적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-107">The Time to Live (TTL) property set on a queued binding configured for sessions is applied to the session as a whole.</span></span> <span data-ttu-id="edca0-108">TTL이 만료되기 전에 세션에 있는 메시지 중 일부만 전송된 경우 전체 세션이 배달 못 한 편지 큐에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-108">If only some of the messages in the session are sent before the TTL expires, the entire session is placed in the dead-letter queue.</span></span> <span data-ttu-id="edca0-109">마찬가지로 세션에 있는 메시지가 애플리케이션 큐에서 애플리케이션으로 전송되지 못하면 전체 세션이 포이즌 큐(사용 가능한 경우)에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-109">Similarly, when messages in a session fail to be sent to an application from the application queue, the entire session is placed in the poison queue (if available).</span></span>  
  
## <a name="message-grouping-example"></a><span data-ttu-id="edca0-110">메시지 그룹화 예제</span><span class="sxs-lookup"><span data-stu-id="edca0-110">Message Grouping Example</span></span>  
 <span data-ttu-id="edca0-111">메시지를 그룹화 하는 한 가지 예는 주문 처리 응용 프로그램을 WCF 서비스로 구현 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-111">One example where grouping messages is helpful is when implementing an order-processing application as a WCF service.</span></span> <span data-ttu-id="edca0-112">예를 들어 클라이언트가 많은 항목을 포함하는 주문을 이 애플리케이션에 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-112">For instance, a client submits an order to this application that contains a number of items.</span></span> <span data-ttu-id="edca0-113">각 항목에 대해 클라이언트가 서비스를 호출하고, 그 결과 메시지가 개별적으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-113">For each item, the client makes a call to the service, which results in a separate message being sent.</span></span> <span data-ttu-id="edca0-114">서버 A가 첫 번째 항목을 수신하고 서버 B가 두 번째 항목을 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-114">It is possible for serve A to receive the first item, and server B to receive the second item.</span></span> <span data-ttu-id="edca0-115">항목이 추가될 때마다 해당 항목을 처리하는 서버는 해당 주문을 찾아서 항목을 추가해야 하므로 매우 비효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-115">Each time an item is added, the server processing that item has to find the appropriate order and add the item to it, which is highly inefficient.</span></span> <span data-ttu-id="edca0-116">서버에서 현재 처리 중인 모든 주문을 추적하여 새 항목이 속하는 주문을 확인해야 하기 때문에 단일 서버에서 모든 요청을 처리하는 이런 비효율성이 여전히 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-116">You still run into such inefficiencies with only a single server handling all requests, because the server must keep track of all orders currently being processed and determine which one the new item belongs to.</span></span> <span data-ttu-id="edca0-117">단일 주문에 대한 모든 요청을 그룹화하면 이러한 애플리케이션의 구현이 크게 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-117">Grouping all requests for a single order greatly simplifies implementation of such an application.</span></span> <span data-ttu-id="edca0-118">클라이언트 애플리케이션이 세션에 있는 단일 주문에 대한 모든 항목을 보내기 때문에 서비스에서 주문을 처리할 때 전체 세션을 한 번에 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-118">The client application sends all items for a single order in a session, so when the service processes the order, it processes the entire session at once.</span></span> \  
  
## <a name="procedures"></a><span data-ttu-id="edca0-119">절차</span><span class="sxs-lookup"><span data-stu-id="edca0-119">Procedures</span></span>  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a><span data-ttu-id="edca0-120">세션을 사용하도록 서비스 계약을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="edca0-120">To set up a service contract to use sessions</span></span>  
  
1. <span data-ttu-id="edca0-121">세션이 필요한 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-121">Define a service contract that requires a session.</span></span> <span data-ttu-id="edca0-122">다음을 지정 하 <xref:System.ServiceModel.ServiceContractAttribute> 여 특성을 사용 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-122">Do this with the <xref:System.ServiceModel.ServiceContractAttribute> attribute by specifying:</span></span>  
  
    ```csharp
    SessionMode=SessionMode.Required  
    ```  
  
2. <span data-ttu-id="edca0-123">이러한 메서드는 아무것도 반환하지 않기 때문에 계약의 작업을 단방향으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-123">Mark the operations in the contract as one-way, because these methods do not return anything.</span></span> <span data-ttu-id="edca0-124">이 작업은 다음을 <xref:System.ServiceModel.OperationContractAttribute> 지정 하 여 특성을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-124">This is done with the <xref:System.ServiceModel.OperationContractAttribute> attribute by specifying:</span></span>  
  
    ```csharp  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3. <span data-ttu-id="edca0-125">서비스 계약을 구현하고 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode>의 <xref:System.ServiceModel.InstanceContextMode.PerSession?displayProperty=nameWithType>를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-125">Implement the service contract and specify an <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.PerSession?displayProperty=nameWithType>.</span></span> <span data-ttu-id="edca0-126">그러면 각 세션에 대해 서비스가 한 번씩만 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-126">This instantiates the service only once for each session.</span></span>  
  
    ```csharp  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4. <span data-ttu-id="edca0-127">서비스 작업마다 하나의 트랜잭션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-127">Each service operation requires a transaction.</span></span> <span data-ttu-id="edca0-128"><xref:System.ServiceModel.OperationBehaviorAttribute> 특성을 사용하여 이를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-128">Specify this with the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="edca0-129">트랜잭션을 완료하는 작업에서는 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete>를 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-129">The operation that completes the transaction should also set <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete> to `true`.</span></span>  
  
    ```csharp  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]   
    ```  
  
5. <span data-ttu-id="edca0-130">시스템 제공 `NetMsmqBinding` 바인딩을 사용하는 엔드포인트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-130">Configure an endpoint that uses the system-provided `NetMsmqBinding` binding.</span></span>  
  
6. <span data-ttu-id="edca0-131"><xref:System.Messaging>을 사용하여 트랜잭션 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-131">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="edca0-132">메시지 큐(MSMQ) 또는 MMC를 사용하여 큐를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-132">You can also create the queue by using Message Queuing (MSMQ) or MMC.</span></span> <span data-ttu-id="edca0-133">그러면 트랜잭션 큐가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-133">If you do, create a transactional queue.</span></span>  
  
7. <span data-ttu-id="edca0-134"><xref:System.ServiceModel.ServiceHost>를 사용하여 서비스에 대한 서비스 호스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-134">Create a service host for the service by using <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
8. <span data-ttu-id="edca0-135">서비스를 사용할 수 있도록 서비스 호스트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-135">Open the service host to make the service available.</span></span>  
  
9. <span data-ttu-id="edca0-136">서비스 호스트를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-136">Close the service host.</span></span>  
  
#### <a name="to-set-up-a-client"></a><span data-ttu-id="edca0-137">클라이언트를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="edca0-137">To set up a client</span></span>  
  
1. <span data-ttu-id="edca0-138">트랜잭션 큐에 쓸 트랜잭션 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-138">Create a transaction scope to write to the transactional queue.</span></span>  
  
2. <span data-ttu-id="edca0-139">[ServiceModel Metadata 유틸리티 도구 (svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구를 사용 하 여 WCF 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-139">Create the WCF client using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool.</span></span>  
  
3. <span data-ttu-id="edca0-140">주문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-140">Place the order.</span></span>  
  
4. <span data-ttu-id="edca0-141">WCF 클라이언트를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-141">Close the WCF client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edca0-142">예제</span><span class="sxs-lookup"><span data-stu-id="edca0-142">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="edca0-143">설명</span><span class="sxs-lookup"><span data-stu-id="edca0-143">Description</span></span>  
 <span data-ttu-id="edca0-144">다음 예제에서는 `IProcessOrder` 서비스와 이 서비스를 사용하는 클라이언트에 대한 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-144">The following example provides the code for the `IProcessOrder` service and for a client that uses this service.</span></span> <span data-ttu-id="edca0-145">WCF에서 큐에 대기 중인 세션을 사용 하 여 그룹화 동작을 제공 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="edca0-145">It shows how WCF uses queued sessions to provide the grouping behavior.</span></span>  
  
### <a name="code-for-the-service"></a><span data-ttu-id="edca0-146">서비스 코드</span><span class="sxs-lookup"><span data-stu-id="edca0-146">Code for the Service</span></span>  
 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  

### <a name="code-for-the-client"></a><span data-ttu-id="edca0-147">클라이언트 코드</span><span class="sxs-lookup"><span data-stu-id="edca0-147">Code for the Client</span></span>  
 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  

## <a name="see-also"></a><span data-ttu-id="edca0-148">참고자료</span><span class="sxs-lookup"><span data-stu-id="edca0-148">See also</span></span>

- [<span data-ttu-id="edca0-149">세션 및 큐</span><span class="sxs-lookup"><span data-stu-id="edca0-149">Sessions and Queues</span></span>](../../../../docs/framework/wcf/samples/sessions-and-queues.md)
- [<span data-ttu-id="edca0-150">큐 개요</span><span class="sxs-lookup"><span data-stu-id="edca0-150">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)
