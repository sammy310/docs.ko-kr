---
description: '자세한 정보: 서비스: 초당 실패 한 호출 수'
title: '서비스: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: b271d5076d0f0c89c4d33b124e0184584795466a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803362"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="2c673-103">서비스: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="2c673-103">Service: Calls Failed Per Second</span></span>

<span data-ttu-id="2c673-104">카운터 이름: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="2c673-104">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2c673-105">설명</span><span class="sxs-lookup"><span data-stu-id="2c673-105">Description</span></span>  

 <span data-ttu-id="2c673-106">초당 이 서비스에서 받은, 처리되지 않은 예외가 있는 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2c673-106">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="2c673-107">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 유형 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))입니다.</span><span class="sxs-lookup"><span data-stu-id="2c673-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="2c673-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="2c673-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="2c673-109">관리 코드에서 오류 조건이 발생하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c673-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="2c673-110">관리 코드에서 오류 조건이 발생하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c673-110">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="2c673-111">이 서비스에 처리되지 않은 예외가 있을 때마다 이 카운터가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="2c673-111">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c673-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c673-112">See also</span></span>

- [<span data-ttu-id="2c673-113">계약 및 서비스에서 오류 지정 및 처리</span><span class="sxs-lookup"><span data-stu-id="2c673-113">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
