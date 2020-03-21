---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: e80fecf508158dcb53f08b75c8f9486c13e403a4
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674792"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="8edd0-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="8edd0-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="8edd0-103">MSMQ에서 메시지를 삭제했습니다.</span><span class="sxs-lookup"><span data-stu-id="8edd0-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8edd0-104">Description</span><span class="sxs-lookup"><span data-stu-id="8edd0-104">Description</span></span>  
 <span data-ttu-id="8edd0-105">추적은 MSMQ 메시지가 삭제되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8edd0-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="8edd0-106">Windows 통신 재단(WCF)(NetMsmqBinding 또는 MsmqIntegrationBinding과 함께 사용)이 처리할 수 없는 경우 MSMQ 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8edd0-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="8edd0-107">이러한 메시지를 포이즌 메시지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8edd0-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="8edd0-108">포이즌 메시지는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Drop`으로 설정할 경우 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8edd0-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="8edd0-109">삭제된 메시지는 큐에서 제거되고 더 이상 복구될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8edd0-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="8edd0-110">메시지가 독이 되는 시기와 메시지를 적절하게 처리하도록 서비스를 구성하는 방법에 대한 자세한 내용은 [독 메시지 처리를](../../feature-details/poison-message-handling.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8edd0-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8edd0-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8edd0-111">See also</span></span>

- [<span data-ttu-id="8edd0-112">추적</span><span class="sxs-lookup"><span data-stu-id="8edd0-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="8edd0-113">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8edd0-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="8edd0-114">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="8edd0-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="8edd0-115">포이즌 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="8edd0-115">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
