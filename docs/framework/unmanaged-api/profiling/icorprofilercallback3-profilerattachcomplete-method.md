---
title: ICorProfilerCallback3::ProfilerAttachComplete 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerAttachComplete Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type:
- apiref
ms.openlocfilehash: 4c5b8f18424ba54d9e8e14ba0a518a89e0d54796
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439471"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="e1982-102">ICorProfilerCallback3::ProfilerAttachComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="e1982-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="e1982-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) catch-up methods.</span><span class="sxs-lookup"><span data-stu-id="e1982-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1982-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1982-104">Syntax</span></span>  
  
```cpp  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e1982-105">주의</span><span class="sxs-lookup"><span data-stu-id="e1982-105">Remarks</span></span>  
 <span data-ttu-id="e1982-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method is called.</span><span class="sxs-lookup"><span data-stu-id="e1982-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="e1982-107">다음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1982-107">It indicates the following:</span></span>  
  
- <span data-ttu-id="e1982-108">`InitializeForAttach`에서 프로파일러가 요청한 콜백이 활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e1982-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
- <span data-ttu-id="e1982-109">이제 프로파일러가 누락된 알림에 대해 염려하지 않고 연결된 ID에서 후속 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1982-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="e1982-110">CLR은 이 콜백의 반환 값을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="e1982-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1982-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1982-111">Requirements</span></span>  
 <span data-ttu-id="e1982-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1982-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1982-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e1982-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e1982-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1982-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1982-115">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1982-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1982-116">참조</span><span class="sxs-lookup"><span data-stu-id="e1982-116">See also</span></span>

- [<span data-ttu-id="e1982-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1982-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e1982-118">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1982-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="e1982-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1982-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="e1982-120">프로파일링</span><span class="sxs-lookup"><span data-stu-id="e1982-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
