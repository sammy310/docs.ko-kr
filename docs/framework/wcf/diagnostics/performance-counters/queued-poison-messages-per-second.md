---
title: Queued Poison Messages Per Second
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 1e515a81580bd9773841bee4230288d8c7d12216
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276232"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="c7915-102">Queued Poison Messages Per Second</span><span class="sxs-lookup"><span data-stu-id="c7915-102">Queued Poison Messages Per Second</span></span>

<span data-ttu-id="c7915-103">카운터 이름: Queued Poison Messages Per Second</span><span class="sxs-lookup"><span data-stu-id="c7915-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c7915-104">Description</span><span class="sxs-lookup"><span data-stu-id="c7915-104">Description</span></span>  

 <span data-ttu-id="c7915-105">1초 동안 이 서비스에 대기 중인 전송에 의해 포이즌으로 표시된 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c7915-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="c7915-106">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="c7915-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c7915-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="c7915-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
