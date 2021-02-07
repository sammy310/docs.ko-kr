---
description: '자세한 정보: 끝점: 초당 실패 한 호출 수'
title: '엔드포인트: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 262f0fdf0750e8fdb179d41d1a99788784270023
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759642"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="0c864-103">엔드포인트: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="0c864-103">Endpoint: Calls Failed Per Second</span></span>

<span data-ttu-id="0c864-104">카운터 이름: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="0c864-104">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0c864-105">설명</span><span class="sxs-lookup"><span data-stu-id="0c864-105">Description</span></span>  

 <span data-ttu-id="0c864-106">처리되지 않은 예외가 있고 초당 이 엔드포인트에서 받은 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0c864-106">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="0c864-107">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="0c864-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="0c864-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="0c864-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="0c864-109">이 카운터는 이 엔드포인트에서 처리되지 않은 예외가 발생할 때마다 증가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c864-109">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c864-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c864-110">See also</span></span>

- [<span data-ttu-id="0c864-111">계약 및 서비스에서 오류 지정 및 처리</span><span class="sxs-lookup"><span data-stu-id="0c864-111">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
