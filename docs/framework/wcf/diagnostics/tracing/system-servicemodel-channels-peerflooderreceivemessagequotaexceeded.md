---
description: PeerFlooderReceiveMessageQuotaExceeded에 대해 자세히 알아보세요.
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 8ad164b253491f3a533c4828cd76f915eb5aed68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780872"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="e788b-103">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="e788b-103">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>

<span data-ttu-id="e788b-104">메시지의 인바운드 수신 속도가 너무 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="e788b-104">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e788b-105">설명</span><span class="sxs-lookup"><span data-stu-id="e788b-105">Description</span></span>  

 <span data-ttu-id="e788b-106">이 추적은 인바운드 메시지를 처리하려 할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e788b-106">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="e788b-107">인접 부분에 설정된 할당량을 초과했기 때문에 특정 인접 부분에 메시지를 전달하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="e788b-107">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="e788b-108">이 문제는 응답하지 않는 인접 부분에서 보류 중인 메시지의 백로그를 지우지 못한 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e788b-108">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="e788b-109">문제 해결</span><span class="sxs-lookup"><span data-stu-id="e788b-109">Troubleshooting</span></span>  

 <span data-ttu-id="e788b-110">메시 내에서 메시지를 보내는 속도를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="e788b-110">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e788b-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e788b-111">See also</span></span>

- [<span data-ttu-id="e788b-112">추적</span><span class="sxs-lookup"><span data-stu-id="e788b-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="e788b-113">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e788b-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e788b-114">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="e788b-114">Administration and Diagnostics</span></span>](../index.md)
