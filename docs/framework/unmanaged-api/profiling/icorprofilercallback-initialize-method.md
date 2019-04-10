---
title: ICorProfilerCallback::Initialize 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16001c4af2bcd8aa8d5fff6b06fa8c275bc24cb9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191005"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="d5769-102">ICorProfilerCallback::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="d5769-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="d5769-103">새 공용 언어 런타임 (CLR) 응용 프로그램을 시작할 때마다 코드 프로파일러를 초기화 하기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5769-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5769-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5769-104">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5769-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5769-105">Parameters</span></span>  
 `pICorProfilerInfoUnk`  
 <span data-ttu-id="d5769-106">[에](/cpp/atl/iunknown) 프로파일러에 대해 쿼리해야 하는 인터페이스는 [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d5769-106">[in](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5769-107">설명</span><span class="sxs-lookup"><span data-stu-id="d5769-107">Remarks</span></span>  
 <span data-ttu-id="d5769-108">`Initialize` 호출은 변경할 수 없는 콜백을 사용 하도록 설정 (또는 사용 안 함) 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d5769-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="d5769-109">콜백 하 여 활성화 되 면 합니다 `Initialize` 호출을 사용 하 여 나중에 비활성화할 수 없습니다 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="d5769-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="d5769-110">COR_PRF_MONITOR_IMMUTABLE 값을 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거형 이벤트를 변경할 수 없는 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d5769-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5769-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5769-111">Requirements</span></span>  
 <span data-ttu-id="d5769-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5769-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5769-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5769-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5769-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5769-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d5769-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="d5769-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5769-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5769-116">See also</span></span>

- [<span data-ttu-id="d5769-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5769-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d5769-118">Shutdown 메서드</span><span class="sxs-lookup"><span data-stu-id="d5769-118">Shutdown Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
