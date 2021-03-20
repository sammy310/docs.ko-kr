---
description: '자세히 알아보기: ICorProfilerCallback:: AppDomainShutdownFinished 메서드'
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
ms.openlocfilehash: 8cd45f73741bd26cb54fa85d7d6a186ebaeab5d8
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760693"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="12f1c-103">ICorProfilerCallback::AppDomainShutdownFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="12f1c-103">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>

<span data-ttu-id="12f1c-104">응용 프로그램 도메인이 프로세스에서 언로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="12f1c-104">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12f1c-105">구문</span><span class="sxs-lookup"><span data-stu-id="12f1c-105">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12f1c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12f1c-106">Parameters</span></span>

<span data-ttu-id="12f1c-107">`appDomainId` 진행 응용 프로그램의 어셈블리가 저장 된 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f1c-107">`appDomainId` [in] Identifies the domain in which the application's assemblies are stored.</span></span>

<span data-ttu-id="12f1c-108">`hrStatus` 진행 응용 프로그램 도메인이 성공적으로 언로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="12f1c-108">`hrStatus` [in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="12f1c-109">설명</span><span class="sxs-lookup"><span data-stu-id="12f1c-109">Remarks</span></span>  

 <span data-ttu-id="12f1c-110">`appDomainId` [ICorProfilerCallback:: AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) 메서드가 반환 된 후에는 값이 정보 요청에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12f1c-110">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="12f1c-111">응용 프로그램 도메인 언로드의 일부 부분은 콜백 후에도 계속 `AppDomainCreationFinished` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f1c-111">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="12f1c-112">의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12f1c-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="12f1c-113">그러나의 성공 HRESULT는 `hrStatus` 응용 프로그램 도메인 언로드의 첫 번째 부분만 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12f1c-113">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12f1c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12f1c-114">Requirements</span></span>  

 <span data-ttu-id="12f1c-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12f1c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12f1c-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12f1c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12f1c-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12f1c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12f1c-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12f1c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12f1c-119">참조</span><span class="sxs-lookup"><span data-stu-id="12f1c-119">See also</span></span>

- [<span data-ttu-id="12f1c-120">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12f1c-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
