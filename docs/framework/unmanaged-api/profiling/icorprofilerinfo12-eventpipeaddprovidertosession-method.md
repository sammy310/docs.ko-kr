---
description: '자세히 알아보기: ICorProfilerInfo12:: EventPipeAddProviderToSession 메서드'
title: 'ICorProfilerInfo12:: EventPipeAddProviderToSession 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeAddProviderToSession
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 70654660c496211c20459ef9ba37dfbd96b829b3
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805690"
---
# <a name="icorprofilerinfo12eventpipeaddprovidertosession-method"></a><span data-ttu-id="4923b-103">ICorProfilerInfo12:: EventPipeAddProviderToSession 메서드</span><span class="sxs-lookup"><span data-stu-id="4923b-103">ICorProfilerInfo12::EventPipeAddProviderToSession Method</span></span>

<span data-ttu-id="4923b-104">기존 EventPipe 세션에 공급자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4923b-104">Adds a provider to an existing EventPipe session.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="4923b-105">구문</span><span class="sxs-lookup"><span data-stu-id="4923b-105">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeAddProviderToSession(
        [in] EVENTPIPE_SESSION                 session,
        [in] COR_PRF_EVENTPIPE_PROVIDER_CONFIG providerConfig);
```  
  
## <a name="parameters"></a><span data-ttu-id="4923b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4923b-106">Parameters</span></span>

<span data-ttu-id="4923b-107">`session` 진행 공급자를 추가할 세션의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4923b-107">`session` [in] The ID of the session to add the provider to.</span></span>

<span data-ttu-id="4923b-108">`providerConfig` 진행 `COR_PRF_EVENTPIPE_PROVIDER_CONFIG` 세션에 추가할 공급자를 설명 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="4923b-108">`providerConfig` [in] A `COR_PRF_EVENTPIPE_PROVIDER_CONFIG` describing the provider to add to the session.</span></span>

## <a name="requirements"></a><span data-ttu-id="4923b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4923b-109">Requirements</span></span>  

<span data-ttu-id="4923b-110">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4923b-110">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="4923b-111">**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4923b-111">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4923b-112">참조</span><span class="sxs-lookup"><span data-stu-id="4923b-112">See also</span></span>

- [<span data-ttu-id="4923b-113">EventPipe 개요</span><span class="sxs-lookup"><span data-stu-id="4923b-113">EventPipe Overview</span></span>](../../../core/diagnostics/eventpipe.md)
- [<span data-ttu-id="4923b-114">잘 알려진 EventProviders</span><span class="sxs-lookup"><span data-stu-id="4923b-114">Well Known EventProviders</span></span>](../../../core/diagnostics/well-known-event-providers.md)
- [<span data-ttu-id="4923b-115">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4923b-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="4923b-116">ICorProfilerCallback10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4923b-116">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="4923b-117">ICorProfilerInfo12 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4923b-117">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
- [<span data-ttu-id="4923b-118">COR_PRF_EVENTPIPE_PROVIDER_CONFIG 구조체</span><span class="sxs-lookup"><span data-stu-id="4923b-118">COR_PRF_EVENTPIPE_PROVIDER_CONFIG Structure</span></span>](cor-prf-eventpipe-provider-config-structure.md)
