---
description: '자세한 정보: 순서가 잘못 된 메시지 처리'
title: 순서에 상관없이 메시지 처리
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 4349b7d72c080dff579eda18ce51de99ab5e91fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733608"
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="e3232-103">순서에 상관없이 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="e3232-103">Out-of-Order Message Processing</span></span>

<span data-ttu-id="e3232-104">워크플로 서비스는 특정 순서로 보내지는 메시지에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3232-104">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="e3232-105">워크플로 서비스는 하나 이상의 <xref:System.ServiceModel.Activities.Receive> 활동을 포함하고 각 <xref:System.ServiceModel.Activities.Receive> 활동은 특정 메시지를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="e3232-105">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="e3232-106">특정 전송 전달 보장이 없으면 클라이언트가 보낸 메시지가 지연되어 워크플로 서비스가 예상할 수 없는 순서로 배달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3232-106">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="e3232-107">메시지를 순서에 상관없이 보내도 되는 워크플로 서비스를 구현하는 작업은 일반적으로 병렬 활동을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3232-107">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="e3232-108">복잡한 애플리케이션 프로토콜의 경우 워크플로가 매우 빠른 속도로 매우 복잡해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3232-108">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="e3232-109">WCF (Windows Communication Foundation)에서 순서가 잘못 된 메시지 처리 기능을 사용 하면 중첩 된 병렬 작업의 복잡성을 모두 제외 하 고 이러한 워크플로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3232-109">The out-of-order message processing feature in Windows Communication Foundation (WCF) allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="e3232-110">순서가 잘못 된 메시지 처리는 <xref:System.ServiceModel.Channels.ReceiveContext> WCF MSMQ 바인딩과 같은를 지 원하는 채널 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3232-110">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the WCF MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="e3232-111">메시지를 순서에 상관없이 처리하는 기능 사용</span><span class="sxs-lookup"><span data-stu-id="e3232-111">Enabling Out-Of-Order Message Processing</span></span>  

 <span data-ttu-id="e3232-112">메시지를 순서에 상관없이 처리하는 기능을 사용하려면 WorkflowService의 <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3232-112">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="e3232-113">다음 예제에서는 코드에서 <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> 속성을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3232-113">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="e3232-114">또한 다음 예제와 같이 XAML에서 워크플로 서비스에 `AllowBufferedReceive` 특성을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3232-114">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3232-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3232-115">See also</span></span>

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [<span data-ttu-id="e3232-116">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="e3232-116">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="e3232-117">큐 및 신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="e3232-117">Queues and Reliable Sessions</span></span>](queues-and-reliable-sessions.md)
