---
title: ICorProfilerCallback::AppDomainShutdownFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
ms.openlocfilehash: ddb2d6eeb75a118a12f681b354f6feccd1231c64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685390"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="6fca6-102">ICorProfilerCallback::AppDomainShutdownFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="6fca6-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>

<span data-ttu-id="6fca6-103">응용 프로그램 도메인이 프로세스에서 언로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6fca6-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fca6-104">구문</span><span class="sxs-lookup"><span data-stu-id="6fca6-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fca6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6fca6-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="6fca6-106">\[in] 응용 프로그램의 어셈블리가 저장 된 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fca6-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

- `hrStatus`

  <span data-ttu-id="6fca6-107">\[in] 응용 프로그램 도메인이 언로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="6fca6-107">\[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="6fca6-108">설명</span><span class="sxs-lookup"><span data-stu-id="6fca6-108">Remarks</span></span>  

 <span data-ttu-id="6fca6-109">`appDomainId` [ICorProfilerCallback:: AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) 메서드가 반환 된 후에는 값이 정보 요청에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fca6-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="6fca6-110">응용 프로그램 도메인 언로드의 일부 부분은 콜백 후에도 계속 `AppDomainCreationFinished` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fca6-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="6fca6-111">의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fca6-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="6fca6-112">그러나의 성공 HRESULT는 `hrStatus` 응용 프로그램 도메인 언로드의 첫 번째 부분만 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fca6-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fca6-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6fca6-113">Requirements</span></span>  

 <span data-ttu-id="6fca6-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fca6-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fca6-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6fca6-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6fca6-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fca6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fca6-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fca6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fca6-118">참조</span><span class="sxs-lookup"><span data-stu-id="6fca6-118">See also</span></span>

- [<span data-ttu-id="6fca6-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fca6-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
