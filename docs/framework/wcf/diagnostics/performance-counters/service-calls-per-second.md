---
title: '서비스: Calls Per Second'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 5066108d8183502eeaec7c25186c00d9978261b7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546935"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="05fd9-102">서비스: Calls Per Second</span><span class="sxs-lookup"><span data-stu-id="05fd9-102">Service: Calls Per Second</span></span>
<span data-ttu-id="05fd9-103">카운터 이름: Calls Per Second</span><span class="sxs-lookup"><span data-stu-id="05fd9-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="05fd9-104">Description</span><span class="sxs-lookup"><span data-stu-id="05fd9-104">Description</span></span>  
 <span data-ttu-id="05fd9-105">이 서비스에 대한 초당 호출 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="05fd9-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="05fd9-106">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="05fd9-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="05fd9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)에서 분자(N)는 마지막 샘플 기간 동안 수행되는 작업 수를 나타내고, 분모(D)는 해당 기간 동안 경과되는 눈금 수를 나타내며 F는 눈금의 주기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05fd9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
