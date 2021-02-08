---
description: '자세한 정보: 트랜잭션 작업 (의심 스러운 초당 트랜잭션 작업)'
title: Transacted Operations In Doubt Per Second
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: e4f8b8c9db1c92ea4348763cdc4a633f058dbaf2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771095"
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="cf241-103">Transacted Operations In Doubt Per Second</span><span class="sxs-lookup"><span data-stu-id="cf241-103">Transacted Operations In Doubt Per Second</span></span>

<span data-ttu-id="cf241-104">카운터 이름: Transacted Operations In Doubt Per Second</span><span class="sxs-lookup"><span data-stu-id="cf241-104">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cf241-105">설명</span><span class="sxs-lookup"><span data-stu-id="cf241-105">Description</span></span>  

 <span data-ttu-id="cf241-106">초당 이 서비스에서 확실하지 않은 결과가 있는 트랜잭션 작업의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cf241-106">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="cf241-107">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="cf241-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="cf241-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="cf241-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
