---
description: 작업 성능 카운터에 대해 자세히 알아보세요.
title: 작업 성능 카운터
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: e0a503d4d8b178d5d3f4ef240bf84c4b02a581ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655203"
---
# <a name="operation-performance-counters"></a><span data-ttu-id="39828-103">작업 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="39828-103">Operation Performance Counters</span></span>

<span data-ttu-id="39828-104">작업 성능 카운터는 성능 모니터(Perfmon.exe)에서 볼 때 `ServiceModelOperation 4.0.0.0` 성능 개체 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39828-104">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="39828-105">각 작업에는 개별 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39828-105">Each operation has an individual instance.</span></span> <span data-ttu-id="39828-106">즉, 지정된 계약에 10개의 작업이 있는 경우 10개의 작업 카운터 인스턴스가 해당 계약에 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39828-106">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="39828-107">개체 인스턴스 이름은 다음 패턴으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="39828-107">The object instances are named using the following pattern:</span></span>  
  
`(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)`
  
 <span data-ttu-id="39828-108">이 카운터를 사용하면 호출이 사용되는 방법과 작업 진행 상태를 측정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39828-108">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="39828-109">성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39828-109">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="39828-110">WCF (Windows Communication Foundation) 카운터 인스턴스 이름이 최대 길이를 초과 하면 WCF는 인스턴스 이름의 일부를 해시 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="39828-110">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39828-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39828-111">See also</span></span>

- [<span data-ttu-id="39828-112">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="39828-112">Performance Counters</span></span>](index.md)
