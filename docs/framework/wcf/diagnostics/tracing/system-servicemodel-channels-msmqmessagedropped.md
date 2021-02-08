---
description: MsmqMessageDropped에 대해 자세히 알아보세요.
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 41b9c6d5399f0f6b458404ee4b64624e5863c777
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780962"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="b764d-103">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="b764d-103">System.ServiceModel.Channels.MsmqMessageDropped</span></span>

<span data-ttu-id="b764d-104">MSMQ에서 메시지를 삭제했습니다.</span><span class="sxs-lookup"><span data-stu-id="b764d-104">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b764d-105">설명</span><span class="sxs-lookup"><span data-stu-id="b764d-105">Description</span></span>  

 <span data-ttu-id="b764d-106">추적은 MSMQ 메시지가 삭제되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b764d-106">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="b764d-107">Windows Communication Foundation (WCF) (NetMsmqBinding 또는 MsmqIntegrationBinding에서 사용)가 처리할 수 없는 경우 MSMQ 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b764d-107">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="b764d-108">이러한 메시지를 포이즌 메시지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b764d-108">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="b764d-109">포이즌 메시지는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Drop`으로 설정할 경우 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b764d-109">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="b764d-110">삭제된 메시지는 큐에서 제거되고 더 이상 복구될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b764d-110">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="b764d-111">메시지가 포이즌 메시지를 처리 하 고 적절 하 게 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 [포이즌 메시지 처리](../../feature-details/poison-message-handling.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b764d-111">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b764d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b764d-112">See also</span></span>

- [<span data-ttu-id="b764d-113">추적</span><span class="sxs-lookup"><span data-stu-id="b764d-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="b764d-114">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b764d-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b764d-115">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="b764d-115">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="b764d-116">포이즌 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="b764d-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
