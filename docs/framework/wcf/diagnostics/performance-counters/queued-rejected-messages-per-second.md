---
title: Queued Rejected Messages Per Second
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 5ffef15801745eb0496676ea17a1a2b10c9e4707
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552637"
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="c22f0-102">Queued Rejected Messages Per Second</span><span class="sxs-lookup"><span data-stu-id="c22f0-102">Queued Rejected Messages Per Second</span></span>
<span data-ttu-id="c22f0-103">카운터 이름: Queued Messages Rejected Per Second</span><span class="sxs-lookup"><span data-stu-id="c22f0-103">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c22f0-104">Description</span><span class="sxs-lookup"><span data-stu-id="c22f0-104">Description</span></span>  
 <span data-ttu-id="c22f0-105">초당 이 서비스에 대기 중인 전송에 의해 거부된 메시지의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c22f0-105">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="c22f0-106">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="c22f0-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c22f0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="c22f0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
