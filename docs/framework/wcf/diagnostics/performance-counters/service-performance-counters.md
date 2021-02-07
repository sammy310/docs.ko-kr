---
description: '자세한 정보: Service 성능 카운터'
title: 서비스 성능 카운터
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 16f6f2548cf7f92b64264ac606423c69e62cd110
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686039"
---
# <a name="service-performance-counters"></a><span data-ttu-id="78dd6-103">서비스 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="78dd6-103">Service Performance Counters</span></span>

<span data-ttu-id="78dd6-104">서비스 성능 카운터는 서비스 동작을 전반적으로 측정하며 전체 서비스 성능을 진단하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78dd6-104">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="78dd6-105">이러한 카운터는 성능 모니터(Perfmon.exe)에서 볼 때 `ServiceModelService 4.0.0.0` 성능 개체 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78dd6-105">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="78dd6-106">인스턴스 이름은 다음 패턴으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="78dd6-106">The instances are named using the following pattern:</span></span>  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> <span data-ttu-id="78dd6-107">성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78dd6-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="78dd6-108">WCF (Windows Communication Foundation) 카운터 인스턴스 이름이 최대 길이를 초과 하면 WCF는 인스턴스 이름의 일부를 해시 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="78dd6-108">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78dd6-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78dd6-109">See also</span></span>

- [<span data-ttu-id="78dd6-110">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="78dd6-110">Performance Counters</span></span>](index.md)
