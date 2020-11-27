---
title: Transacted Operations Committed Per Second
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: deb29820aab09adad8825a299145772892117948
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250010"
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="29205-102">Transacted Operations Committed Per Second</span><span class="sxs-lookup"><span data-stu-id="29205-102">Transacted Operations Committed Per Second</span></span>

<span data-ttu-id="29205-103">카운터 이름: Transacted Operations Committed Per Second</span><span class="sxs-lookup"><span data-stu-id="29205-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="29205-104">Description</span><span class="sxs-lookup"><span data-stu-id="29205-104">Description</span></span>  

 <span data-ttu-id="29205-105">초당 이 서비스에서 커밋된 트랜잭션 작업 수입니다.</span><span class="sxs-lookup"><span data-stu-id="29205-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="29205-106">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="29205-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="29205-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="29205-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
