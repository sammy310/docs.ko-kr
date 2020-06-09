---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: c388a9dc3569e20639de09abc5f4941b73c561ad
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578053"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="69759-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="69759-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="69759-103">MSMQ에서 메시지를 거부했습니다.</span><span class="sxs-lookup"><span data-stu-id="69759-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="69759-104">Description</span><span class="sxs-lookup"><span data-stu-id="69759-104">Description</span></span>  
 <span data-ttu-id="69759-105">이 추적은 MSMQ 메시지가 거부되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69759-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="69759-106">Windows Communication Foundation (WCF) (NetMsmqBinding 또는 MsmqIntegrationBinding와 함께 사용)에서이를 처리할 수 없는 경우 MSMQ 메시지가 거부 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69759-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="69759-107">이러한 메시지를 포이즌 메시지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="69759-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="69759-108">포이즌 메시지는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Reject`로 설정할 경우 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="69759-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="69759-109">거부 된 메시지는 보낸 사람의 [배달 못 한 편지 큐](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)로 다시 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69759-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures).</span></span>  
  
 <span data-ttu-id="69759-110">메시지가 포이즌 메시지를 처리 하 고 적절 하 게 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 [포이즌 메시지 처리](../../feature-details/poison-message-handling.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69759-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="69759-111">MSMQ에서 거부 된 메시지의 의미에 대 한 자세한 내용은 [Mqmarkmessagerejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))않음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69759-111">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69759-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69759-112">See also</span></span>

- [<span data-ttu-id="69759-113">추적</span><span class="sxs-lookup"><span data-stu-id="69759-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="69759-114">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="69759-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="69759-115">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="69759-115">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="69759-116">포이즌 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="69759-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="69759-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="69759-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
