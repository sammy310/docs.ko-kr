---
description: MsmqMoveOrDeleteAttemptFailed에 대해 자세히 알아보세요.
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 7b3c8dad9e3a3e88dff72706917f3729d55b3799
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769743"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="553a1-103">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="553a1-103">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>

<span data-ttu-id="553a1-104">메시지를 이동하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="553a1-104">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="553a1-105">설명</span><span class="sxs-lookup"><span data-stu-id="553a1-105">Description</span></span>  

 <span data-ttu-id="553a1-106">이 추적은 MSMQ 메시지를 이동, 삭제 및 거부하는 동안 오류가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="553a1-106">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="553a1-107">NetMsmqBinding 또는 MsmqIntegrationBinding과 함께 사용 하는 경우 WCF (Windows Communication Foundation)에서 MSMQ 메시지를 사용 합니다. 이 추적은 `ReceiveErrorHandling` NetMsmqBinding 또는 MsmqIntegrationBinding에서 선택한 속성 값과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="553a1-107">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="553a1-108">이 추적은 전체 시스템 오류를 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="553a1-108">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="553a1-109">그러나 메시지에서 선택한 포이즌 메시지를 처리하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="553a1-109">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="553a1-110">메시지가 포이즌 메시지를 처리 하 고 적절 하 게 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 [포이즌 메시지 처리](../../feature-details/poison-message-handling.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="553a1-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553a1-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="553a1-111">See also</span></span>

- [<span data-ttu-id="553a1-112">추적</span><span class="sxs-lookup"><span data-stu-id="553a1-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="553a1-113">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="553a1-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="553a1-114">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="553a1-114">Administration and Diagnostics</span></span>](../index.md)
