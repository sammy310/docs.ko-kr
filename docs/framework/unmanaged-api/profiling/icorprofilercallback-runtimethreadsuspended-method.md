---
description: '자세히 알아보기: ICorProfilerCallback:: RuntimeThreadSuspended 메서드'
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
ms.openlocfilehash: f7c2f5baf5a320375d9a2606ca05b13d522336be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657335"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="93871-103">ICorProfilerCallback::RuntimeThreadSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="93871-103">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>

<span data-ttu-id="93871-104">지정 된 스레드가 일시 중단 되었거나 일시 중단 됨을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="93871-104">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93871-105">구문</span><span class="sxs-lookup"><span data-stu-id="93871-105">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93871-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="93871-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="93871-107">진행 일시 중단 된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="93871-107">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93871-108">설명</span><span class="sxs-lookup"><span data-stu-id="93871-108">Remarks</span></span>  

 <span data-ttu-id="93871-109">이 `RuntimeThreadSuspended` 알림은 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) 와 연결 된 [ICorProfilerCallback:: Run esumestarted](icorprofilercallback-runtimeresumestarted-method.md) 콜백 사이에 언제 든 지 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93871-109">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="93871-110">[ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) 간에 발생 하는 알림은 `RuntimeResumeStarted` 비관리 코드에서 실행 되었으며 런타임에 대 한 진입 시 일시 중단 된 스레드에 대 한 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="93871-110">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="93871-111">일반적으로이 콜백은 스레드가 일시 중단 된 후에만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="93871-111">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="93871-112">그러나 현재 실행 중인 스레드 (이 콜백을 호출한 스레드가 일시 중단 된 스레드) 인 경우이 콜백은 스레드가 일시 중단 되기 직전에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="93871-112">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93871-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93871-113">Requirements</span></span>  

 <span data-ttu-id="93871-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93871-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93871-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="93871-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="93871-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93871-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93871-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93871-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93871-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93871-118">See also</span></span>

- [<span data-ttu-id="93871-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93871-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="93871-120">RuntimeThreadResumed 메서드</span><span class="sxs-lookup"><span data-stu-id="93871-120">RuntimeThreadResumed Method</span></span>](icorprofilercallback-runtimethreadresumed-method.md)
