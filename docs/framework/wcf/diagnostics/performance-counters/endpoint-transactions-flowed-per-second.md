---
title: '엔드포인트: Transactions Flowed Per Second'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 9391651eaaca130ef47ddee9daa95b1f8c116892
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553794"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="f8786-102">엔드포인트: Transactions Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="f8786-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="f8786-103">카운터 이름: Transactions Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="f8786-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f8786-104">Description</span><span class="sxs-lookup"><span data-stu-id="f8786-104">Description</span></span>  
 <span data-ttu-id="f8786-105">이 엔드포인트에서 작업에 적용된 초당 트랜잭션의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8786-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="f8786-106">엔드포인트에 전송된 메시지에 트랜잭션 ID가 있을 때마다 이 카운터가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8786-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="f8786-107">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="f8786-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="f8786-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="f8786-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
