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
ms.openlocfilehash: 64df6a81eb23c20537238c702fd0c204d64d14bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434558"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="cec23-102">ICorProfilerCallback::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="cec23-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="cec23-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span><span class="sxs-lookup"><span data-stu-id="cec23-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cec23-104">구문</span><span class="sxs-lookup"><span data-stu-id="cec23-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cec23-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cec23-105">Parameters</span></span>  
 `pICorProfilerInfoUnk`  
 <span data-ttu-id="cec23-106">[in](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface pointer.</span><span class="sxs-lookup"><span data-stu-id="cec23-106">[in](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cec23-107">주의</span><span class="sxs-lookup"><span data-stu-id="cec23-107">Remarks</span></span>  
 <span data-ttu-id="cec23-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span><span class="sxs-lookup"><span data-stu-id="cec23-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="cec23-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="cec23-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="cec23-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span><span class="sxs-lookup"><span data-stu-id="cec23-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cec23-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cec23-111">Requirements</span></span>  
 <span data-ttu-id="cec23-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cec23-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cec23-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cec23-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cec23-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cec23-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cec23-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cec23-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec23-116">참조</span><span class="sxs-lookup"><span data-stu-id="cec23-116">See also</span></span>

- [<span data-ttu-id="cec23-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cec23-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cec23-118">Shutdown 메서드</span><span class="sxs-lookup"><span data-stu-id="cec23-118">Shutdown Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
