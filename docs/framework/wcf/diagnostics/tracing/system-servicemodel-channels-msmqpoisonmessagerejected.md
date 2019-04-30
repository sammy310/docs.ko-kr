---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 562399c1d45dc73c7c88bd165e9f95ee1bcfa19d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997517"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="214eb-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="214eb-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="214eb-103">포이즌 메시지가 거부되었습니다.</span><span class="sxs-lookup"><span data-stu-id="214eb-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="214eb-104">설명</span><span class="sxs-lookup"><span data-stu-id="214eb-104">Description</span></span>  
 <span data-ttu-id="214eb-105">이 추적은 포이즌 메시지가 발생되어 거부되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="214eb-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="214eb-106">이는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Reject`로 설정할 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="214eb-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="214eb-107">거부 된 메시지를 보낸 사람에 게 배달 됩니다 [배달 못 한 편지 큐](https://go.microsoft.com/fwlink/?LinkId=99544)합니다.</span><span class="sxs-lookup"><span data-stu-id="214eb-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="214eb-108">참조 [포이즌 메시지 처리](https://go.microsoft.com/fwlink/?LinkId=99546) 메시지는 포이즌 메시지가 될 경우 및이 적절히 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="214eb-108">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="214eb-109">참조 [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) MSMQ에서 거부 된 메시지가 의미 하는 바를 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="214eb-109">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="214eb-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="214eb-110">See also</span></span>

- [<span data-ttu-id="214eb-111">추적</span><span class="sxs-lookup"><span data-stu-id="214eb-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="214eb-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="214eb-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="214eb-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="214eb-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="214eb-114">포이즌 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="214eb-114">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkId=99546)
- [<span data-ttu-id="214eb-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="214eb-115">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkId=99548)
