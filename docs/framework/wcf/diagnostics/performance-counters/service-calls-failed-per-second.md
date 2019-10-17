---
title: '서비스: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: 5431144a4618b146a10dfaa3bbdaae34c519319e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72315792"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="9241e-102">서비스: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="9241e-102">Service: Calls Failed Per Second</span></span>
<span data-ttu-id="9241e-103">카운터 이름: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="9241e-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9241e-104">설명</span><span class="sxs-lookup"><span data-stu-id="9241e-104">Description</span></span>  
 <span data-ttu-id="9241e-105">초당 이 서비스에서 받은, 처리되지 않은 예외가 있는 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9241e-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="9241e-106">이 카운터는 다음 수식을 사용 하 여 값을 계산 하는 성능 카운터 형식 [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)입니다.</span><span class="sxs-lookup"><span data-stu-id="9241e-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="9241e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="9241e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="9241e-108">관리 코드에서 오류 조건이 발생하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="9241e-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="9241e-109">관리 코드에서 오류 조건이 발생하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="9241e-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="9241e-110">이 서비스에 처리되지 않은 예외가 있을 때마다 이 카운터가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="9241e-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9241e-111">참조</span><span class="sxs-lookup"><span data-stu-id="9241e-111">See also</span></span>

- [<span data-ttu-id="9241e-112">계약 및 서비스에서 오류 지정 및 처리</span><span class="sxs-lookup"><span data-stu-id="9241e-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
