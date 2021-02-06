---
description: '자세히 알아보기: 신뢰할 수 있는 메시징 메시지 초당 삭제 된 메시지 수'
title: Reliable Messaging Messages Dropped Per Second
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 6132316f100cecdba357a6da071e23de8c9a2181
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655112"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="81c75-103">Reliable Messaging Messages Dropped Per Second</span><span class="sxs-lookup"><span data-stu-id="81c75-103">Reliable Messaging Messages Dropped Per Second</span></span>

<span data-ttu-id="81c75-104">카운터 이름: Reliable Messaging Sessions Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="81c75-104">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="81c75-105">설명</span><span class="sxs-lookup"><span data-stu-id="81c75-105">Description</span></span>  

 <span data-ttu-id="81c75-106">이 서비스에서 초당 손실된 신뢰할 수 있는 메시징 메시지의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="81c75-106">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="81c75-107">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="81c75-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="81c75-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="81c75-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
