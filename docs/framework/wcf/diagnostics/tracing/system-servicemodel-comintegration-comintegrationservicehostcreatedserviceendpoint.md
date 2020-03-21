---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: f89dd1373d67714046f8cb958582c3a5dea04456
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674785"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="7ed48-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="7ed48-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="7ed48-103">메시지를 이동하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ed48-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7ed48-104">Description</span><span class="sxs-lookup"><span data-stu-id="7ed48-104">Description</span></span>  
 <span data-ttu-id="7ed48-105">이 추적은 MSMQ 메시지를 이동, 삭제 및 거부하는 동안 오류가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7ed48-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="7ed48-106">MSMQ 메시지는 WCF(Windows 통신 재단)에서 사용됩니다(NetMsmqBinding 또는 MsmqIntegrationBinding과 함께 사용할 경우). 이 추적은 NetMsmqBinding `ReceiveErrorHandling` 또는 MsmqIntegrationBinding에서 속성의 선택된 값과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ed48-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="7ed48-107">이 추적은 전체 시스템 오류를 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ed48-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="7ed48-108">그러나 메시지에서 선택한 포이즌 메시지를 처리하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7ed48-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="7ed48-109">메시지가 독이 되는 시기와 메시지를 적절하게 처리하도록 서비스를 구성하는 방법에 대한 자세한 내용은 [독 메시지 처리를](../../feature-details/poison-message-handling.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ed48-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ed48-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ed48-110">See also</span></span>

- [<span data-ttu-id="7ed48-111">추적</span><span class="sxs-lookup"><span data-stu-id="7ed48-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="7ed48-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7ed48-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7ed48-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="7ed48-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
