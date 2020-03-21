---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 6b0e6e3ebcf5d414e9dbbcecd09ba2e8bb3ddd3a
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674806"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="6288c-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="6288c-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="6288c-103">포이즌 메시지가 거부되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6288c-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6288c-104">Description</span><span class="sxs-lookup"><span data-stu-id="6288c-104">Description</span></span>  

 <span data-ttu-id="6288c-105">이 추적은 포이즌 메시지가 발생되어 거부되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6288c-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="6288c-106">이는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Reject`로 설정할 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6288c-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="6288c-107">거부된 메시지는 보낸 사람의 [배달 못한 편지 대기열로](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)다시 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="6288c-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="6288c-108">메시지가 독이 되는 시기와 메시지를 적절하게 처리하도록 서비스를 구성하는 방법에 대한 자세한 내용은 [독 메시지 처리를](../../feature-details/poison-message-handling.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6288c-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="6288c-109">MSMQ에서 거부된 메시지의 의미에 대한 자세한 내용은 [MQMarkMessage거부를](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6288c-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6288c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6288c-110">See also</span></span>

- [<span data-ttu-id="6288c-111">추적</span><span class="sxs-lookup"><span data-stu-id="6288c-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="6288c-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6288c-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6288c-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="6288c-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="6288c-114">포이즌 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="6288c-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="6288c-115">[MQMark메시지거부](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="6288c-115">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
