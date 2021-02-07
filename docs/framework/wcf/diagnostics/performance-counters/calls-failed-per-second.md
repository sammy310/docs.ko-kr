---
description: '자세한 정보: 초당 실패 한 호출'
title: Calls Failed Per Second
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: 3961754eb73743a1213922f7c9e1bd164334cd6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759720"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="887d7-103">Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="887d7-103">Calls Failed Per Second</span></span>

<span data-ttu-id="887d7-104">카운터 이름: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="887d7-104">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="887d7-105">설명</span><span class="sxs-lookup"><span data-stu-id="887d7-105">Description</span></span>  

 <span data-ttu-id="887d7-106">이 작업에 처리되지 않은 예외가 있는 초당 호출 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="887d7-106">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="887d7-107">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="887d7-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="887d7-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="887d7-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="887d7-109">이 작업에 처리 되지 않은 예외가 있을 때마다이 카운터가 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="887d7-109">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="887d7-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="887d7-110">See also</span></span>

- [<span data-ttu-id="887d7-111">계약 및 서비스에서 오류 지정 및 처리</span><span class="sxs-lookup"><span data-stu-id="887d7-111">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
