---
title: Calls Failed Per Second
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: 110ee5c264094f80d5c7c6542c3e388e758e1665
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163165"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="4e50c-102">Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="4e50c-102">Calls Failed Per Second</span></span>
<span data-ttu-id="4e50c-103">카운터 이름: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="4e50c-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="4e50c-104">설명</span><span class="sxs-lookup"><span data-stu-id="4e50c-104">Description</span></span>  
 <span data-ttu-id="4e50c-105">이 작업에 처리되지 않은 예외가 있는 초당 호출 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e50c-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="4e50c-106">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="4e50c-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="4e50c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="4e50c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="4e50c-108">이 작업에 처리 되지 않은 예외가 있을 때마다이 카운터가 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e50c-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e50c-109">참조</span><span class="sxs-lookup"><span data-stu-id="4e50c-109">See also</span></span>

- [<span data-ttu-id="4e50c-110">계약 및 서비스에서 오류 지정 및 처리</span><span class="sxs-lookup"><span data-stu-id="4e50c-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
