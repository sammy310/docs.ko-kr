---
description: PeerMaintainerActivity에 대해 자세히 알아보세요.
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: da4e4cf87da808cb6779445b6507b51d098132b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780883"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a><span data-ttu-id="67adc-103">System.ServiceModel.Channels.PeerMaintainerActivity</span><span class="sxs-lookup"><span data-stu-id="67adc-103">System.ServiceModel.Channels.PeerMaintainerActivity</span></span>

<span data-ttu-id="67adc-104">PeerMaintainer 모듈이 특정 작업을 수행하고 있습니다(상세 정보는 추적 메시지 본문에 포함).</span><span class="sxs-lookup"><span data-stu-id="67adc-104">The PeerMaintainer module is performing a specific operation (details contained within the trace message body).</span></span>  
  
## <a name="description"></a><span data-ttu-id="67adc-105">설명</span><span class="sxs-lookup"><span data-stu-id="67adc-105">Description</span></span>  

 <span data-ttu-id="67adc-106">이 추적은 다양한 PeerMaintainer 작업을 수행하는 동안 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="67adc-106">This trace occurs during various PeerMaintainer operations.</span></span>  
  
 <span data-ttu-id="67adc-107">PeerMaintainer는 PeerNode의 내부 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="67adc-107">PeerMaintainer is an internal component of PeerNode.</span></span> <span data-ttu-id="67adc-108">1분마다 또는 메시지 32개를 받을 때마다 PeerMaintainer는 교환된 메시지 수 및 유용한 메시지(손상되지 않은 비중복 메시지) 수에 대한 통계가 포함된 LinkUtility 메시지를 인접한 환경에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="67adc-108">Every minute, or every 32 messages received, it sends a LinkUtility message to its neighbors with statistics about how many messages are exchanged and how many are useful (non-duplicates, untampered).</span></span> <span data-ttu-id="67adc-109">이렇게 하면 특정 환경의 링크 유틸리티를 확인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67adc-109">This helps determine a particular neighbor's Link Utility.</span></span> <span data-ttu-id="67adc-110">약 5분마다 유지 관리자는 환경 연결의 상태를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="67adc-110">Approximately every five minutes, the maintainer checks the health of neighbor connections.</span></span> <span data-ttu-id="67adc-111">환경 연결 수가 이상적인 값을 초과하면 유지 관리자가 가장 덜 유용한 연결을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="67adc-111">If the number of neighbor connections exceeds the ideal amount, the maintainer prunes off the least useful connections.</span></span> <span data-ttu-id="67adc-112">연결 수가 충분하지 않으면 유지 관리자가 새 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="67adc-112">If there are not enough connections, the maintainer acquires new connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67adc-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67adc-113">See also</span></span>

- [<span data-ttu-id="67adc-114">추적</span><span class="sxs-lookup"><span data-stu-id="67adc-114">Tracing</span></span>](index.md)
- [<span data-ttu-id="67adc-115">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="67adc-115">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="67adc-116">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="67adc-116">Administration and Diagnostics</span></span>](../index.md)
