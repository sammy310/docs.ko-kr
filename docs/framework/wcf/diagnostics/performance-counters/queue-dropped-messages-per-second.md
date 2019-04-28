---
title: Queue Dropped Messages Per Second
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: f15b2db08ac4486377189a1533b653260d79024a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916164"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="d41f8-102">Queue Dropped Messages Per Second</span><span class="sxs-lookup"><span data-stu-id="d41f8-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="d41f8-103">카운터 이름: 큐에 대기 중인된 Messages Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="d41f8-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d41f8-104">설명</span><span class="sxs-lookup"><span data-stu-id="d41f8-104">Description</span></span>  
 <span data-ttu-id="d41f8-105">초당 이 서비스에 대기 중인 전송에서 손실된 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d41f8-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="d41f8-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음 수식을 사용 하 여 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d41f8-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="d41f8-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="d41f8-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
