---
title: Calls Failed Per Second
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: aa8cd4c2d9f642b525b2b9ccb931c4f2101a5129
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421783"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="7b19a-102">Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="7b19a-102">Calls Failed Per Second</span></span>
<span data-ttu-id="7b19a-103">카운터 이름: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="7b19a-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="7b19a-104">설명</span><span class="sxs-lookup"><span data-stu-id="7b19a-104">Description</span></span>  
 <span data-ttu-id="7b19a-105">이 작업에 처리되지 않은 예외가 있는 초당 호출 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="7b19a-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="7b19a-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음 수식을 사용 하 여 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b19a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7b19a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="7b19a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="7b19a-108">이 작업에서 처리 되지 않은 예외가 발생 될 때마다이 카운터가 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b19a-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b19a-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="7b19a-109">See also</span></span>

- [<span data-ttu-id="7b19a-110">계약 및 서비스에서 오류 지정 및 처리</span><span class="sxs-lookup"><span data-stu-id="7b19a-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
