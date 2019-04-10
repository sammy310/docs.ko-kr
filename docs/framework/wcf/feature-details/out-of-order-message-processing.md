---
title: 순서에 상관없이 메시지 처리
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 4e1864b25a4dbe8192cd5c692c75645bebbb92d2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141403"
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="c3d5f-102">순서에 상관없이 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="c3d5f-102">Out-of-Order Message Processing</span></span>
<span data-ttu-id="c3d5f-103">워크플로 서비스는 특정 순서로 보내지는 메시지에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d5f-103">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="c3d5f-104">워크플로 서비스는 하나 이상의 <xref:System.ServiceModel.Activities.Receive> 활동을 포함하고 각 <xref:System.ServiceModel.Activities.Receive> 활동은 특정 메시지를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c3d5f-104">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="c3d5f-105">특정 전송 전달 보장이 없으면 클라이언트가 보낸 메시지가 지연되어 워크플로 서비스가 예상할 수 없는 순서로 배달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d5f-105">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="c3d5f-106">메시지를 순서에 상관없이 보내도 되는 워크플로 서비스를 구현하는 작업은 일반적으로 병렬 활동을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3d5f-106">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="c3d5f-107">복잡한 응용 프로그램 프로토콜의 경우 워크플로가 매우 빠른 속도로 매우 복잡해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d5f-107">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="c3d5f-108">순서가의 메시지 처리 기능에서 Windows Communication Foundation (WCF)를 사용 하면 모든 중첩 된 병렬 작업의 복잡성 없이 워크플로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d5f-108">The out-of-order message processing feature in Windows Communication Foundation (WCF) allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="c3d5f-109">순서의 메시지 처리를 지 원하는 채널 에서만 지원 됩니다 <xref:System.ServiceModel.Channels.ReceiveContext> WCF MSMQ 바인딩 같은 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3d5f-109">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the WCF MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="c3d5f-110">메시지를 순서에 상관없이 처리하는 기능 사용</span><span class="sxs-lookup"><span data-stu-id="c3d5f-110">Enabling Out-Of-Order Message Processing</span></span>  
 <span data-ttu-id="c3d5f-111">메시지를 순서에 상관없이 처리하는 기능을 사용하려면 WorkflowService의 <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c3d5f-111">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="c3d5f-112">다음 예제에서는 코드에서 <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> 속성을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3d5f-112">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="c3d5f-113">또한 다음 예제와 같이 XAML에서 워크플로 서비스에 `AllowBufferedReceive` 특성을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d5f-113">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3d5f-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3d5f-114">See also</span></span>

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [<span data-ttu-id="c3d5f-115">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="c3d5f-115">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="c3d5f-116">큐 및 신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="c3d5f-116">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
