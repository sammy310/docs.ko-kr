---
title: 서비스 성능 카운터
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: f3e3a798bf04f24aaea03b5d70762d52b67a82f0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252831"
---
# <a name="service-performance-counters"></a><span data-ttu-id="de5b6-102">서비스 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="de5b6-102">Service Performance Counters</span></span>

<span data-ttu-id="de5b6-103">서비스 성능 카운터는 서비스 동작을 전반적으로 측정하며 전체 서비스 성능을 진단하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5b6-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="de5b6-104">이러한 카운터는 성능 모니터(Perfmon.exe)에서 볼 때 `ServiceModelService 4.0.0.0` 성능 개체 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5b6-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="de5b6-105">인스턴스 이름은 다음 패턴으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="de5b6-105">The instances are named using the following pattern:</span></span>  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> <span data-ttu-id="de5b6-106">성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5b6-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="de5b6-107">WCF (Windows Communication Foundation) 카운터 인스턴스 이름이 최대 길이를 초과 하면 WCF는 인스턴스 이름의 일부를 해시 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="de5b6-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de5b6-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de5b6-108">See also</span></span>

- [<span data-ttu-id="de5b6-109">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="de5b6-109">Performance Counters</span></span>](index.md)
