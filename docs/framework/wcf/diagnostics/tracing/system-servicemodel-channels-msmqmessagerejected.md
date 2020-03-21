---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 8f783dcd4b966ed89c24d724918a3923c5a2d0b1
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674766"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="2e926-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="2e926-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="2e926-103">MSMQ에서 메시지를 거부했습니다.</span><span class="sxs-lookup"><span data-stu-id="2e926-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2e926-104">Description</span><span class="sxs-lookup"><span data-stu-id="2e926-104">Description</span></span>  
 <span data-ttu-id="2e926-105">이 추적은 MSMQ 메시지가 거부되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2e926-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="2e926-106">MsMQ 메시지는 Windows 통신 재단(NetMsmqBinding 또는 MsmqIntegrationBinding)과 함께 사용)이 이를 처리할 수 없는 경우 거부될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e926-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="2e926-107">이러한 메시지를 포이즌 메시지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e926-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="2e926-108">포이즌 메시지는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Reject`로 설정할 경우 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e926-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="2e926-109">거부된 메시지는 보낸 사람의 [배달 못한 편지 대기열로](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)다시 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e926-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures).</span></span>  
  
 <span data-ttu-id="2e926-110">메시지가 독이 되는 시기와 메시지를 적절하게 처리하도록 서비스를 구성하는 방법에 대한 자세한 내용은 [독 메시지 처리를](../../feature-details/poison-message-handling.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2e926-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="2e926-111">MSMQ에서 거부된 메시지의 의미에 대한 자세한 내용은 [MQMarkMessage거부를](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2e926-111">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e926-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e926-112">See also</span></span>

- [<span data-ttu-id="2e926-113">추적</span><span class="sxs-lookup"><span data-stu-id="2e926-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="2e926-114">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2e926-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2e926-115">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="2e926-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="2e926-116">포이즌 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="2e926-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="2e926-117">[MQMark메시지거부](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="2e926-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
