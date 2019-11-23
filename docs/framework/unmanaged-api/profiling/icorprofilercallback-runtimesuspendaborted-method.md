---
title: ICorProfilerCallback::RuntimeSuspendAborted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
ms.openlocfilehash: fb09a9422f2aeec239f9aef25fb61c731e0aa2e9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430615"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="735e5-102">ICorProfilerCallback::RuntimeSuspendAborted 메서드</span><span class="sxs-lookup"><span data-stu-id="735e5-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="735e5-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span><span class="sxs-lookup"><span data-stu-id="735e5-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="735e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="735e5-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="735e5-105">주의</span><span class="sxs-lookup"><span data-stu-id="735e5-105">Remarks</span></span>  
 <span data-ttu-id="735e5-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span><span class="sxs-lookup"><span data-stu-id="735e5-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="735e5-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="735e5-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="735e5-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span><span class="sxs-lookup"><span data-stu-id="735e5-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="735e5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="735e5-109">Requirements</span></span>  
 <span data-ttu-id="735e5-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="735e5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="735e5-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="735e5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="735e5-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="735e5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="735e5-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="735e5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735e5-114">참조</span><span class="sxs-lookup"><span data-stu-id="735e5-114">See also</span></span>

- [<span data-ttu-id="735e5-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="735e5-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
