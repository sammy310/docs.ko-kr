---
title: ICorDebugUnmanagedCallback::DebugEvent 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1c75e1844fca4e592faa924a55432dd42fa7355
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772625"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a><span data-ttu-id="4a92a-102">ICorDebugUnmanagedCallback::DebugEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="4a92a-102">ICorDebugUnmanagedCallback::DebugEvent Method</span></span>
<span data-ttu-id="4a92a-103">네이티브 이벤트가 발생 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-103">Notifies the debugger that a native event has been fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a92a-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a92a-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a92a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a92a-105">Parameters</span></span>  
 `pDebugEvent`  
 <span data-ttu-id="4a92a-106">[in] 네이티브 이벤트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-106">[in] A pointer to the native event.</span></span>  
  
 `fOutOfBand`  
 <span data-ttu-id="4a92a-107">[in] `true`디버거 호출 될 때까지 관리 되지 않는 이벤트가 발생 한 후 관리 되는 프로세스 상태를 사용 하 여 상호 작용 수 없는 경우 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)이 고, 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-107">[in] `true`, if interaction with the managed process state is impossible after an unmanaged event occurs, until the debugger calls [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a92a-108">설명</span><span class="sxs-lookup"><span data-stu-id="4a92a-108">Remarks</span></span>  
 <span data-ttu-id="4a92a-109">디버깅 중인 스레드의 Win32 스레드 인 경우에 디버깅 인터페이스는 Win32의 모든 멤버를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="4a92a-109">If the thread being debugged is a Win32 thread, do not use any members of the Win32 debugging interface.</span></span> <span data-ttu-id="4a92a-110">호출할 수 있습니다 `ICorDebugController::Continue` Win32 스레드에서만 및 지난 대역의 이벤트를 계속 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-110">You can call `ICorDebugController::Continue` only on a Win32 thread and only when continuing past an out-of-band event.</span></span>  
  
 <span data-ttu-id="4a92a-111">`DebugEvent` 콜백 콜백에 대 한 표준 규칙을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-111">The `DebugEvent` callback does not follow the standard rules for callbacks.</span></span> <span data-ttu-id="4a92a-112">호출 하는 경우 `DebugEvent`프로세스에 원시 됩니다, OS 디버그 상태를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-112">When you call `DebugEvent`, the process will be in the raw, OS-debug stopped state.</span></span> <span data-ttu-id="4a92a-113">프로세스 동기화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-113">The process will not be synchronized.</span></span> <span data-ttu-id="4a92a-114">중첩 된 다른 따를 수 있는 관리 코드에 대 한 정보에 대 한 요청을 충족 하기 위해 필요한 경우 동기화 된 상태로 자동으로 입력 됩니다 `DebugEvent` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-114">It will automatically enter the synchronized state when necessary to satisfy requests for information about managed code, which may result in other nested `DebugEvent` callbacks.</span></span>  
  
 <span data-ttu-id="4a92a-115">호출 [icordebugprocess:: Clearcurrentexception](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) 프로세스를 계속 하기 전에 예외 이벤트를 무시 하는 프로세스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-115">Call [ICorDebugProcess::ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) on the process to ignore an exception event before continuing the process.</span></span> <span data-ttu-id="4a92a-116">이 메서드를 호출 DBG_EXCEPTION_NOT_HANDLED 대신 DBG_CONTINUE 계속 요청을 전송 하 고 자동으로 대역의 중단점 및 단일 단계 예외를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-116">Calling this method sends DBG_CONTINUE instead of DBG_EXCEPTION_NOT_HANDLED on the continue request, and automatically clears out-of-band breakpoints and single-step exceptions.</span></span> <span data-ttu-id="4a92a-117">대역의 이벤트는 시간과 처리 중인 대역 내 이벤트는 이미 디버깅 중인 응용 프로그램 중지 표시 하는 경우에 언제 든 지 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-117">Out-of-band events can come at any time, even when the application being debugged appears stopped and when an outstanding in-band event already exists.</span></span>  
  
 <span data-ttu-id="4a92a-118">.NET framework 버전 2.0에서 디버거 대역의 중단점 이벤트 지난 즉시 계속 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-118">In the .NET Framework version 2.0, the debugger should immediately continue past an out-of-band breakpoint event.</span></span> <span data-ttu-id="4a92a-119">디버거를 사용 해야 합니다 [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) 및 [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) 메서드를 추가 하 고 중단점을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-119">The debugger should be using the [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) and [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) methods to add and remove breakpoints.</span></span> <span data-ttu-id="4a92a-120">이러한 메서드는 자동으로 대역의 중단점을 통해 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-120">These methods will skip over any out-of-band breakpoints automatically.</span></span> <span data-ttu-id="4a92a-121">따라서 발송 된 밴드를만 중단점을 원시 중단점은 명령 스트림을 win32 호출과 같은 이미 있어야 `DebugBreak` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-121">Thus, the only out-of-band breakpoints that get dispatched should be raw breakpoints that are already in the instruction stream, such as a call to the Win32 `DebugBreak` function.</span></span> <span data-ttu-id="4a92a-122">사용 하지 마세요 `ICorDebugProcess::ClearCurrentException`, [icordebugprocess:: Getthreadcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)를 [icordebugprocess:: Setthreadcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), 또는 다른 어떤 멤버도 합니다 [디버깅 API](../../../../docs/framework/unmanaged-api/debugging/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a92a-122">Do not try to use `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), or any other member of the [debugging API](../../../../docs/framework/unmanaged-api/debugging/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a92a-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a92a-123">Requirements</span></span>  
 <span data-ttu-id="4a92a-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a92a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a92a-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a92a-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a92a-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a92a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a92a-127">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a92a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a92a-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a92a-128">See also</span></span>

- [<span data-ttu-id="4a92a-129">ICorDebugUnmanagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a92a-129">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
