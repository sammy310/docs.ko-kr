---
title: 서비스 성능 카운터
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 4ce0efbeb0a1d6f2409bb976102b8ec8821d5cdc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848990"
---
# <a name="service-performance-counters"></a><span data-ttu-id="74cd9-102">서비스 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="74cd9-102">Service Performance Counters</span></span>
<span data-ttu-id="74cd9-103">서비스 성능 카운터는 서비스 동작을 전반적으로 측정하며 전체 서비스 성능을 진단하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74cd9-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="74cd9-104">이러한 카운터는 성능 모니터(Perfmon.exe)에서 볼 때 `ServiceModelService 4.0.0.0` 성능 개체 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74cd9-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="74cd9-105">인스턴스 이름은 다음 패턴으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="74cd9-105">The instances are named using the following pattern:</span></span>  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> <span data-ttu-id="74cd9-106">성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74cd9-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="74cd9-107">WCF (Windows Communication Foundation) 카운터 인스턴스 이름이 최대 길이를 초과 하면 WCF는 인스턴스 이름의 일부를 해시 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="74cd9-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74cd9-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="74cd9-108">See also</span></span>

- [<span data-ttu-id="74cd9-109">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="74cd9-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
