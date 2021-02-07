---
description: '자세히 알아보기: 초당 거부 된 지연 메시지 수'
title: Queued Rejected Messages Per Second
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: d0d227a26a49921449786d2c9f885fac13a82bde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99744073"
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="2f0b6-103">Queued Rejected Messages Per Second</span><span class="sxs-lookup"><span data-stu-id="2f0b6-103">Queued Rejected Messages Per Second</span></span>

<span data-ttu-id="2f0b6-104">카운터 이름: Queued Messages Rejected Per Second</span><span class="sxs-lookup"><span data-stu-id="2f0b6-104">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2f0b6-105">설명</span><span class="sxs-lookup"><span data-stu-id="2f0b6-105">Description</span></span>  

 <span data-ttu-id="2f0b6-106">초당 이 서비스에 대기 중인 전송에 의해 거부된 메시지의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0b6-106">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="2f0b6-107">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0b6-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="2f0b6-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="2f0b6-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
