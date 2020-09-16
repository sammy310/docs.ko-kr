---
title: '엔드포인트: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 97e887bd04cd7a755ce38914ace6de39ac871687
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545718"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="24a40-102">엔드포인트: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="24a40-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="24a40-103">카운터 이름: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="24a40-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="24a40-104">Description</span><span class="sxs-lookup"><span data-stu-id="24a40-104">Description</span></span>  
 <span data-ttu-id="24a40-105">처리되지 않은 예외가 있고 초당 이 엔드포인트에서 받은 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="24a40-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="24a40-106">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="24a40-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="24a40-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="24a40-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="24a40-108">이 카운터는 이 엔드포인트에서 처리되지 않은 예외가 발생할 때마다 증가됩니다.</span><span class="sxs-lookup"><span data-stu-id="24a40-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24a40-109">참조</span><span class="sxs-lookup"><span data-stu-id="24a40-109">See also</span></span>

- [<span data-ttu-id="24a40-110">계약 및 서비스에서 오류 지정 및 처리</span><span class="sxs-lookup"><span data-stu-id="24a40-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
