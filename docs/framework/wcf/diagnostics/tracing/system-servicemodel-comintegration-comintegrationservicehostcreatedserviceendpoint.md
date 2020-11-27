---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: aeeba38eaf674453f4c87cf62f5088c55b5fde2d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290818"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="6a0ed-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="6a0ed-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>

<span data-ttu-id="6a0ed-103">메시지를 이동하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ed-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6a0ed-104">Description</span><span class="sxs-lookup"><span data-stu-id="6a0ed-104">Description</span></span>  

 <span data-ttu-id="6a0ed-105">이 추적은 MSMQ 메시지를 이동, 삭제 및 거부하는 동안 오류가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ed-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="6a0ed-106">NetMsmqBinding 또는 MsmqIntegrationBinding과 함께 사용 하는 경우 WCF (Windows Communication Foundation)에서 MSMQ 메시지를 사용 합니다. 이 추적은 `ReceiveErrorHandling` NetMsmqBinding 또는 MsmqIntegrationBinding에서 선택한 속성 값과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ed-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="6a0ed-107">이 추적은 전체 시스템 오류를 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ed-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="6a0ed-108">그러나 메시지에서 선택한 포이즌 메시지를 처리하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ed-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="6a0ed-109">메시지가 포이즌 메시지를 처리 하 고 적절 하 게 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 [포이즌 메시지 처리](../../feature-details/poison-message-handling.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a0ed-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a0ed-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a0ed-110">See also</span></span>

- [<span data-ttu-id="6a0ed-111">추적</span><span class="sxs-lookup"><span data-stu-id="6a0ed-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="6a0ed-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6a0ed-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6a0ed-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="6a0ed-113">Administration and Diagnostics</span></span>](../index.md)
