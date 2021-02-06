---
description: '다음에 대 한 자세한 정보: 끝점: 초당 이동 하는 트랜잭션 수'
title: '엔드포인트: Transactions Flowed Per Second'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 96a122b97bce703b0a0e00c6e74f72c980253652
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655359"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="98760-103">엔드포인트: Transactions Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="98760-103">Endpoint: Transactions Flowed Per Second</span></span>

<span data-ttu-id="98760-104">카운터 이름: Transactions Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="98760-104">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="98760-105">설명</span><span class="sxs-lookup"><span data-stu-id="98760-105">Description</span></span>  

 <span data-ttu-id="98760-106">이 엔드포인트에서 작업에 적용된 초당 트랜잭션의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98760-106">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="98760-107">엔드포인트에 전송된 메시지에 트랜잭션 ID가 있을 때마다 이 카운터가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="98760-107">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="98760-108">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="98760-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="98760-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="98760-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
