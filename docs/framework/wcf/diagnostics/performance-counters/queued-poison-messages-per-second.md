---
title: Queued Poison Messages Per Second
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 39118b515949e6ad4f6ff651037cd757a6dd9bbf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552650"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="552aa-102">Queued Poison Messages Per Second</span><span class="sxs-lookup"><span data-stu-id="552aa-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="552aa-103">카운터 이름: Queued Poison Messages Per Second</span><span class="sxs-lookup"><span data-stu-id="552aa-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="552aa-104">Description</span><span class="sxs-lookup"><span data-stu-id="552aa-104">Description</span></span>  
 <span data-ttu-id="552aa-105">1초 동안 이 서비스에 대기 중인 전송에 의해 포이즌으로 표시된 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="552aa-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="552aa-106">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="552aa-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="552aa-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="552aa-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
