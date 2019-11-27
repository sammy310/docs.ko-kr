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
ms.openlocfilehash: 8ff7d5a593388bd3a584e031aea411dfdb6c9845
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445204"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="76291-102">ICorProfilerCallback::AppDomainShutdownFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="76291-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="76291-103">응용 프로그램 도메인이 프로세스에서 언로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="76291-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76291-104">구문</span><span class="sxs-lookup"><span data-stu-id="76291-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76291-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76291-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="76291-106">진행 응용 프로그램의 어셈블리가 저장 된 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="76291-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="76291-107">진행 응용 프로그램 도메인이 성공적으로 언로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="76291-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76291-108">설명</span><span class="sxs-lookup"><span data-stu-id="76291-108">Remarks</span></span>  
 <span data-ttu-id="76291-109">[ICorProfilerCallback:: AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) 메서드가 반환 된 후에는 `appDomainId` 값이 정보 요청에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76291-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="76291-110">응용 프로그램 도메인 언로드의 일부 부분은 `AppDomainCreationFinished` 콜백 후에도 계속 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76291-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="76291-111">`hrStatus` 오류 HRESULT는 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="76291-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="76291-112">그러나 `hrStatus`의 성공 HRESULT는 응용 프로그램 도메인 언로드의 첫 번째 부분만 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="76291-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76291-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76291-113">Requirements</span></span>  
 <span data-ttu-id="76291-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76291-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76291-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="76291-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="76291-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76291-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76291-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76291-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76291-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="76291-118">See also</span></span>

- [<span data-ttu-id="76291-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76291-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
