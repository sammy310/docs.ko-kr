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
ms.openlocfilehash: 54f7dae511c8bf25dc96451e6477acf26655430a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503200"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="7fa02-102">ICorProfilerCallback::RuntimeThreadSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="7fa02-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="7fa02-103">지정 된 스레드가 일시 중단 되었거나 일시 중단 됨을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7fa02-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fa02-104">구문</span><span class="sxs-lookup"><span data-stu-id="7fa02-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fa02-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7fa02-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="7fa02-106">진행 일시 중단 된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7fa02-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fa02-107">설명</span><span class="sxs-lookup"><span data-stu-id="7fa02-107">Remarks</span></span>  
 <span data-ttu-id="7fa02-108">이 `RuntimeThreadSuspended` 알림은 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) 와 연결 된 [ICorProfilerCallback:: Run esumestarted](icorprofilercallback-runtimeresumestarted-method.md) 콜백 사이에 언제 든 지 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa02-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="7fa02-109">[ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) 간에 발생 하는 알림은 `RuntimeResumeStarted` 비관리 코드에서 실행 되었으며 런타임에 대 한 진입 시 일시 중단 된 스레드에 대 한 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="7fa02-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="7fa02-110">일반적으로이 콜백은 스레드가 일시 중단 된 후에만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa02-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="7fa02-111">그러나 현재 실행 중인 스레드 (이 콜백을 호출한 스레드가 일시 중단 된 스레드) 인 경우이 콜백은 스레드가 일시 중단 되기 직전에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa02-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fa02-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7fa02-112">Requirements</span></span>  
 <span data-ttu-id="7fa02-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7fa02-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fa02-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7fa02-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7fa02-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fa02-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fa02-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fa02-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa02-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fa02-117">See also</span></span>

- [<span data-ttu-id="7fa02-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fa02-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7fa02-119">RuntimeThreadResumed 메서드</span><span class="sxs-lookup"><span data-stu-id="7fa02-119">RuntimeThreadResumed Method</span></span>](icorprofilercallback-runtimethreadresumed-method.md)
