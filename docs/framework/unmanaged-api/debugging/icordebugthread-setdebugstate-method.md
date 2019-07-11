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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66f60b2342b6ff64f1329cbe57032291d5139384
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770593"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="23e66-102">ICorDebugThread::SetDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="23e66-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="23e66-103">이 ICorDebugThread 디버깅 상태를 설명 하는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23e66-104">구문</span><span class="sxs-lookup"><span data-stu-id="23e66-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23e66-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="23e66-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="23e66-106">[in] 이 스레드에 대 한 디버깅 상태를 지정 하는 CorDebugThreadState 열거형 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23e66-107">설명</span><span class="sxs-lookup"><span data-stu-id="23e66-107">Remarks</span></span>  
 <span data-ttu-id="23e66-108">`SetDebugState` 스레드의 현재 디버그 상태를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="23e66-109">("현재 디버그 상태" 상태를 나타내는 디버그 프로세스가 계속 될 실제 현재 상태가 아니라 경우입니다.) 이 일반적인 값은 THREAD_RUNNING입니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="23e66-110">디버거만 스레드 디버그 상태에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="23e66-111">디버그 상태 수행할 마지막 간에 계속 되 면 여러 통해 THREAD_SUSPENDed 계속 스레드를 유지 하려는 경우 한 번에 설정할 하 고 이후에 없는 걱정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="23e66-112">스레드를 일시 중단 및 재개 하는 프로세스는 일반적으로 그럴 가능성은 있지만 교착 상태에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="23e66-113">스레드 및 프로세스를 내장 품질 이며 의도적인입니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="23e66-114">비동기적으로 디버거를 중단 하 고는 스레드는 교착 상태를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="23e66-115">스레드의 사용자 상태 USER_UNSAFE_POINT를 포함 하는 경우 스레드는 GC (가비지 수집)를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="23e66-116">즉, 일시 중단 된 스레드 확률이 훨씬 더 높은 교착 상태를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="23e66-117">이 이벤트 이미 큐에 대기 하는 디버그를 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="23e66-118">디버거가 전체 이벤트 큐를 드레이닝 해야 하므로 (호출한 [icordebugcontroller:: Hasqueuedcallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) 중단 또는 스레드를 다시 시작 하기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="23e66-119">그렇지 않으면 이미 일시 중단 된 것으로 간주 된 스레드에서 이벤트가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e66-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23e66-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="23e66-120">Requirements</span></span>  
 <span data-ttu-id="23e66-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="23e66-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23e66-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23e66-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23e66-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23e66-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23e66-124">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23e66-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
