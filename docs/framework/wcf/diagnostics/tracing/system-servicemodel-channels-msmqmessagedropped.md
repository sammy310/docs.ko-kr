---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 3fa5ec62c5e8ac83f3f81fb406499b7e596b3dac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161339"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="2e4ff-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="2e4ff-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="2e4ff-103">MSMQ에서 메시지를 삭제했습니다.</span><span class="sxs-lookup"><span data-stu-id="2e4ff-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2e4ff-104">설명</span><span class="sxs-lookup"><span data-stu-id="2e4ff-104">Description</span></span>  
 <span data-ttu-id="2e4ff-105">추적은 MSMQ 메시지가 삭제되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2e4ff-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="2e4ff-106">Windows Communication Foundation (WCF) (NetMsmqBinding 또는 MsmqIntegrationBinding을 사용 하 여 사용)를 처리할 수 없는 경우 MSMQ 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e4ff-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="2e4ff-107">이러한 메시지를 포이즌 메시지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e4ff-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="2e4ff-108">포이즌 메시지는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Drop`으로 설정할 경우 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e4ff-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="2e4ff-109">삭제된 메시지는 큐에서 제거되고 더 이상 복구될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e4ff-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="2e4ff-110">참조 [포이즌 메시지 처리](https://go.microsoft.com/fwlink/?LinkID=99546) 메시지는 포이즌 메시지가 될 경우 및이 적절히 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e4ff-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e4ff-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="2e4ff-111">See also</span></span>

- [<span data-ttu-id="2e4ff-112">추적</span><span class="sxs-lookup"><span data-stu-id="2e4ff-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="2e4ff-113">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2e4ff-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2e4ff-114">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="2e4ff-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="2e4ff-115">포이즌 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="2e4ff-115">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
