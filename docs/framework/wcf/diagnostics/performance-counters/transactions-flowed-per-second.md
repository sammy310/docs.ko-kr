---
title: Transactions Flowed Per Second
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: b47219bd58a9b6c4401baa73177928ddca5b6a8b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254144"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="f85a9-102">Transactions Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="f85a9-102">Transactions Flowed Per Second</span></span>

<span data-ttu-id="f85a9-103">카운터 이름: Transactions Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="f85a9-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="f85a9-104">Description</span><span class="sxs-lookup"><span data-stu-id="f85a9-104">Description</span></span>  

 <span data-ttu-id="f85a9-105">이 작업에 적용된 초당 트랜잭션의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f85a9-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="f85a9-106">작업에 전송된 메시지에 트랜잭션 ID가 있을 때마다 이 카운터가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="f85a9-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="f85a9-107">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="f85a9-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="f85a9-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="f85a9-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
