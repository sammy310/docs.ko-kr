---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: d56bbf145c85902d8e5f1fd21f760633121da6da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115286"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="c88c2-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="c88c2-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="c88c2-103">메시지를 이동하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c88c2-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c88c2-104">설명</span><span class="sxs-lookup"><span data-stu-id="c88c2-104">Description</span></span>  
 <span data-ttu-id="c88c2-105">이 추적은 MSMQ 메시지를 이동, 삭제 및 거부하는 동안 오류가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c88c2-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="c88c2-106">MSMQ 메시지를 사용 하 여 Windows Communication Foundation (WCF) (NetMsmqBinding 또는 MsmqIntegrationBinding와 함께 사용) 하는 경우. 선택한 값이이 추적 관련 된 `ReceiveErrorHandling` NetMsmqBinding 또는 MsmqIntegrationBinding의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c88c2-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="c88c2-107">이 추적은 전체 시스템 오류를 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c88c2-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="c88c2-108">그러나 메시지에서 선택한 포이즌 메시지를 처리하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c88c2-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="c88c2-109">참조 [포이즌 메시지 처리](https://go.microsoft.com/fwlink/?LinkID=99546) 메시지는 포이즌 메시지가 될 경우 및이 적절히 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="c88c2-109">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c88c2-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="c88c2-110">See also</span></span>

- [<span data-ttu-id="c88c2-111">추적</span><span class="sxs-lookup"><span data-stu-id="c88c2-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="c88c2-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c88c2-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c88c2-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="c88c2-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
