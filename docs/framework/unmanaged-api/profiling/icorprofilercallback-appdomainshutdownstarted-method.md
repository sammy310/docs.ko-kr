---
title: ICorProfilerCallback::AppDomainShutdownStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
ms.openlocfilehash: 6edf498d506a0ca914124a284c0da3f869f28130
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790213"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="082bd-102">ICorProfilerCallback::AppDomainShutdownStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="082bd-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="082bd-103">응용 프로그램 도메인이 프로세스에서 언로드되고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="082bd-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="082bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="082bd-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="082bd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="082bd-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="082bd-106">\[in] 응용 프로그램의 어셈블리가 저장 된 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="082bd-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="082bd-107">주의</span><span class="sxs-lookup"><span data-stu-id="082bd-107">Remarks</span></span>  
 <span data-ttu-id="082bd-108">`appDomainId` 값은 `AppDomainShutdownStarted` 메서드가 반환 된 후 정보 요청에 대해 유효 하지 않습니다 .이는 프로파일러에서이 응용 프로그램 도메인에 대 한 정보를 가져올 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="082bd-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="082bd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="082bd-109">Requirements</span></span>  
 <span data-ttu-id="082bd-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="082bd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="082bd-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="082bd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="082bd-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="082bd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="082bd-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="082bd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="082bd-114">참조</span><span class="sxs-lookup"><span data-stu-id="082bd-114">See also</span></span>

- [<span data-ttu-id="082bd-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="082bd-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
