---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 0ca3d198ce225221348ac7b405ea91ad215cd298
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190901"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="22e21-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="22e21-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="22e21-103">메시지의 인바운드 수신 속도가 너무 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="22e21-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="22e21-104">설명</span><span class="sxs-lookup"><span data-stu-id="22e21-104">Description</span></span>  
 <span data-ttu-id="22e21-105">이 추적은 인바운드 메시지를 처리하려 할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="22e21-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="22e21-106">인접 부분에 설정된 할당량을 초과했기 때문에 특정 인접 부분에 메시지를 전달하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="22e21-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="22e21-107">이 문제는 응답하지 않는 인접 부분에서 보류 중인 메시지의 백로그를 지우지 못한 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="22e21-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="22e21-108">문제 해결</span><span class="sxs-lookup"><span data-stu-id="22e21-108">Troubleshooting</span></span>  
 <span data-ttu-id="22e21-109">메시 내에서 메시지를 보내는 속도를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="22e21-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e21-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="22e21-110">See also</span></span>

- [<span data-ttu-id="22e21-111">추적</span><span class="sxs-lookup"><span data-stu-id="22e21-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="22e21-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="22e21-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="22e21-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="22e21-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
