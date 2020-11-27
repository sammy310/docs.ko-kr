---
title: Call Duration
ms.date: 03/30/2017
ms.assetid: e4973ec3-3c66-4c0b-b5d0-294b62c83f7d
ms.openlocfilehash: 99b4f62182c7864fd32b878373814e85926025b5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285501"
---
# <a name="calls-duration"></a><span data-ttu-id="c79e0-102">Call Duration</span><span class="sxs-lookup"><span data-stu-id="c79e0-102">Calls Duration</span></span>

<span data-ttu-id="c79e0-103">카운터 이름: 호출 기간</span><span class="sxs-lookup"><span data-stu-id="c79e0-103">Counter Name: Calls Duration</span></span>  
  
## <a name="description"></a><span data-ttu-id="c79e0-104">Description</span><span class="sxs-lookup"><span data-stu-id="c79e0-104">Description</span></span>  

 <span data-ttu-id="c79e0-105">이 작업에 대한 평균 호출 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="c79e0-105">The average duration of calls to this operation.</span></span> <span data-ttu-id="c79e0-106">평균 기간은 (N1-N0)/(D1-D0) 공식을 사용해 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="c79e0-106">The average duration is calculated based on this equation: (N1-N0)/(D1-D0).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="c79e0-107">비동기 WCF 서비스에서 사용 되는 경우 Calls Duration 카운터는 항상-1을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c79e0-107">When used on an asynchronous WCF service the Calls Duration counter will always return -1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c79e0-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c79e0-108">See also</span></span>

- <span data-ttu-id="c79e0-109">[PERF_AVERAGE_TIMER](/previous-versions/windows/embedded/ms938538(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="c79e0-109">[PERF_AVERAGE_TIMER](/previous-versions/windows/embedded/ms938538(v=msdn.10))</span></span>
