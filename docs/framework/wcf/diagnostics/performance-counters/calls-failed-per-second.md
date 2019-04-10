---
title: Calls Failed Per Second
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: ff9320b0990a0543bbb1da553d040ff5a4b4fed9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178622"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="29d6f-102">Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="29d6f-102">Calls Failed Per Second</span></span>
<span data-ttu-id="29d6f-103">카운터 이름: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="29d6f-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="29d6f-104">설명</span><span class="sxs-lookup"><span data-stu-id="29d6f-104">Description</span></span>  
 <span data-ttu-id="29d6f-105">이 작업에 처리되지 않은 예외가 있는 초당 호출 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="29d6f-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="29d6f-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음 수식을 사용 하 여 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29d6f-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="29d6f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="29d6f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="29d6f-108">이 작업에 처리되지 않은 예외가 있을 때마다 이 카운터가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="29d6f-108">This counter is incremented everytime there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d6f-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="29d6f-109">See also</span></span>

- [<span data-ttu-id="29d6f-110">계약 및 서비스에서 오류 지정 및 처리</span><span class="sxs-lookup"><span data-stu-id="29d6f-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
