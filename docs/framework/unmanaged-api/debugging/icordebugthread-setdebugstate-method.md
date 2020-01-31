---
title: ICorDebugThread::SetDebugState 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
ms.openlocfilehash: b7678c64a085a0d4951d398595b9be89af8eeb6b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791436"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="d8bb6-102">ICorDebugThread::SetDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="d8bb6-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="d8bb6-103">이 ICorDebugThread의 디버깅 상태를 설명 하는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8bb6-104">구문</span><span class="sxs-lookup"><span data-stu-id="d8bb6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8bb6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8bb6-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="d8bb6-106">진행 이 스레드의 디버깅 상태를 지정 하는 CorDebugThreadState 열거형 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8bb6-107">주의</span><span class="sxs-lookup"><span data-stu-id="d8bb6-107">Remarks</span></span>  
 <span data-ttu-id="d8bb6-108">`SetDebugState` 스레드의 현재 디버그 상태를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="d8bb6-109">"현재 디버그 상태"는 실제 현재 상태가 아닌 프로세스를 계속 해야 하는 경우 디버그 상태를 나타냅니다. 이에 대 한 일반 값은 THREAD_RUN입니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUN.</span></span> <span data-ttu-id="d8bb6-110">디버거만 스레드의 디버그 상태에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="d8bb6-111">디버그 상태는 계속 해 서 진행 되므로 여러 스레드를 계속 THREAD_SUSPENDed 유지 하려는 경우 한 번만 설정할 수 있으며 그 후에는 걱정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="d8bb6-112">스레드를 일시 중단 하 고 프로세스를 다시 시작 하면 교착 상태가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="d8bb6-113">이는 스레드와 프로세스의 내장 품질 이며 디자인 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="d8bb6-114">디버거는 스레드를 비동기적으로 중단 하 고 다시 시작 하 여 교착 상태를 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="d8bb6-115">스레드의 사용자 상태에 USER_UNSAFE_POINT 포함 된 경우 스레드는 GC (가비지 수집)를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="d8bb6-116">즉, 일시 중단 된 스레드는 교착 상태를 일으킬 가능성이 훨씬 높습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="d8bb6-117">이미 큐에 대기 된 디버그 이벤트에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="d8bb6-118">따라서 디버거는 스레드를 일시 중단 하거나 다시 시작 하기 전에 [ICorDebugController:: HasQueuedCallbacks](icordebugcontroller-hasqueuedcallbacks-method.md)를 호출 하 여 전체 이벤트 큐를 드레이닝 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="d8bb6-119">그렇지 않으면 스레드가 이미 일시 중단 된 것으로 판단 되는 이벤트를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8bb6-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8bb6-120">Requirements</span></span>  
 <span data-ttu-id="d8bb6-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8bb6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8bb6-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8bb6-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8bb6-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8bb6-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8bb6-124">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8bb6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
