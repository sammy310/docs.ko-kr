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
ms.openlocfilehash: 285bdd3f2a96d3c6cb0039382d9944e48c49971a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865911"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="4575f-102">ICorProfilerCallback::RuntimeSuspendAborted 메서드</span><span class="sxs-lookup"><span data-stu-id="4575f-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="4575f-103">런타임에서 발생 한 런타임 일시 중단이 중단 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4575f-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4575f-104">구문</span><span class="sxs-lookup"><span data-stu-id="4575f-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4575f-105">주의</span><span class="sxs-lookup"><span data-stu-id="4575f-105">Remarks</span></span>  
 <span data-ttu-id="4575f-106">두 스레드가 동시에 런타임을 일시 중단 하려고 하면 런타임 일시 중단이 중단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4575f-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="4575f-107">[ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback 또는 `RuntimeSuspendAborted` 콜백은 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback 다음에 나오는 단일 스레드에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4575f-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="4575f-108">`RuntimeSuspendAborted` 콜백은 `RuntimeSuspendStarted` 콜백과 동일한 스레드에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4575f-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4575f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4575f-109">Requirements</span></span>  
 <span data-ttu-id="4575f-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4575f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4575f-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4575f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4575f-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4575f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4575f-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4575f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4575f-114">참조</span><span class="sxs-lookup"><span data-stu-id="4575f-114">See also</span></span>

- [<span data-ttu-id="4575f-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4575f-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
