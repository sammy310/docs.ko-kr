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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9aaf7325b8e7e65aa98904513cc7efe94e35087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041810"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="144a1-102">ICorProfilerCallback::RuntimeSuspendAborted 메서드</span><span class="sxs-lookup"><span data-stu-id="144a1-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="144a1-103">런타임에 발생 하는 런타임 일시 중단 된는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="144a1-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="144a1-104">구문</span><span class="sxs-lookup"><span data-stu-id="144a1-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="144a1-105">설명</span><span class="sxs-lookup"><span data-stu-id="144a1-105">Remarks</span></span>  
 <span data-ttu-id="144a1-106">런타임 일시 중단 두 스레드가 동시에 런타임에서 일시 중단 하려고 할 경우 중단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="144a1-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="144a1-107">중 하나는 [icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) 콜백 또는 `RuntimeSuspendAborted` 콜백 단일 스레드가 다음 발생을 [icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="144a1-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="144a1-108">합니다 `RuntimeSuspendAborted` callback은 동일한 스레드에서 발생 하는 `RuntimeSuspendStarted` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="144a1-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="144a1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="144a1-109">Requirements</span></span>  
 <span data-ttu-id="144a1-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="144a1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="144a1-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="144a1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="144a1-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="144a1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="144a1-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="144a1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="144a1-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="144a1-114">See also</span></span>

- [<span data-ttu-id="144a1-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="144a1-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
