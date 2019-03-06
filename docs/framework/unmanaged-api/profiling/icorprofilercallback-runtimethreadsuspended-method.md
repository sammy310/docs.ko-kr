---
title: ICorProfilerCallback::RuntimeThreadSuspended 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54d297f6915af59ad5a24dfdad9dca9397489edb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468171"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="16277-102">ICorProfilerCallback::RuntimeThreadSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="16277-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="16277-103">지정된 된 스레드가 일시 중단 됨 또는 일시 중단 하려고 합니다.는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="16277-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16277-104">구문</span><span class="sxs-lookup"><span data-stu-id="16277-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16277-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16277-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="16277-106">[in] 일시 중단 된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="16277-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16277-107">설명</span><span class="sxs-lookup"><span data-stu-id="16277-107">Remarks</span></span>  
 <span data-ttu-id="16277-108">`RuntimeThreadSuspended` 알림은 간에 언제 든 지 발생할 수 있습니다 합니다 [icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) 및 연결 된 [icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="16277-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="16277-109">사이 나타나는 알림 [icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) 및 `RuntimeResumeStarted` 스레드에서을 실행 했는 비관리 코드 및 런타임에 진입할 때 일시 중단 된 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16277-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="16277-110">일반적으로이 콜백은 스레드 중지 된 후에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="16277-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="16277-111">그러나 현재 실행 중인 스레드 (이 콜백을 호출 하는 스레드)가 일시 중단 하는 경우이 콜백은 스레드가 일시 중단 된 직전에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="16277-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16277-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16277-112">Requirements</span></span>  
 <span data-ttu-id="16277-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="16277-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16277-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="16277-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="16277-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16277-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16277-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16277-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16277-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="16277-117">See also</span></span>
- [<span data-ttu-id="16277-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16277-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="16277-119">RuntimeThreadResumed 메서드</span><span class="sxs-lookup"><span data-stu-id="16277-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
