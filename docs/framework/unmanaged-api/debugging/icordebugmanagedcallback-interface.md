---
description: '자세히 알아보기: ICorDebugManagedCallback 인터페이스'
title: ICorDebugManagedCallback 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback
helpviewer_keywords:
- ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: b47f1d61-c7dc-4196-b926-0b08c94f7041
topic_type:
- apiref
ms.openlocfilehash: 0dd33e4295caa8f5ae41c65d9bd10152737156ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722817"
---
# <a name="icordebugmanagedcallback-interface"></a><span data-ttu-id="68bf6-103">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68bf6-103">ICorDebugManagedCallback Interface</span></span>

<span data-ttu-id="68bf6-104">디버거 콜백을 처리하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-104">Provides methods to process debugger callbacks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="68bf6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-105">Methods</span></span>  
  
|<span data-ttu-id="68bf6-106">메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-106">Method</span></span>|<span data-ttu-id="68bf6-107">설명</span><span class="sxs-lookup"><span data-stu-id="68bf6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68bf6-108">Break 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-108">Break Method</span></span>](icordebugmanagedcallback-break-method.md)|<span data-ttu-id="68bf6-109"><xref:System.Reflection.Emit.OpCodes.Break>코드 스트림의 명령이 실행 될 때 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-109">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>|  
|[<span data-ttu-id="68bf6-110">Breakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-110">Breakpoint Method</span></span>](icordebugmanagedcallback-breakpoint-method.md)|<span data-ttu-id="68bf6-111">중단점에 도달 하면 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-111">Notifies the debugger when a breakpoint is encountered.</span></span>|  
|[<span data-ttu-id="68bf6-112">BreakpointSetError 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-112">BreakpointSetError Method</span></span>](icordebugmanagedcallback-breakpointseterror-method.md)|<span data-ttu-id="68bf6-113">CLR (공용 언어 런타임)이 함수가 JIT (just-in-time) 컴파일 전에 설정 된 중단점을 정확 하 게 바인딩하지 못했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-113">Notifies the debugger that the common language runtime (CLR) was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>|  
|[<span data-ttu-id="68bf6-114">ControlCTrap 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-114">ControlCTrap Method</span></span>](icordebugmanagedcallback-controlctrap-method.md)|<span data-ttu-id="68bf6-115">디버깅 중인 프로세스에서 CTRL + C가 트랩 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-115">Notifies the debugger that a CTRL+C is trapped in the process being debugged.</span></span>|  
|[<span data-ttu-id="68bf6-116">CreateAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-116">CreateAppDomain Method</span></span>](icordebugmanagedcallback-createappdomain-method.md)|<span data-ttu-id="68bf6-117">응용 프로그램 도메인이 생성 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-117">Notifies the debugger that an application domain has been created.</span></span>|  
|[<span data-ttu-id="68bf6-118">CreateProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-118">CreateProcess Method</span></span>](icordebugmanagedcallback-createprocess-method.md)|<span data-ttu-id="68bf6-119">프로세스가 처음으로 연결 되거나 시작 된 경우 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-119">Notifies the debugger when a process has been attached or started for the first time.</span></span>|  
|[<span data-ttu-id="68bf6-120">CreateThread 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-120">CreateThread Method</span></span>](icordebugmanagedcallback-createthread-method.md)|<span data-ttu-id="68bf6-121">스레드가 관리 코드 실행을 시작 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-121">Notifies the debugger that a thread has started executing managed code.</span></span>|  
|[<span data-ttu-id="68bf6-122">DebuggerError 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-122">DebuggerError Method</span></span>](icordebugmanagedcallback-debuggererror-method.md)|<span data-ttu-id="68bf6-123">CLR에서 이벤트를 처리 하려고 시도 하는 동안 오류가 발생 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-123">Notifies the debugger that an error has occurred while attempting to handle an event from the CLR.</span></span>|  
|[<span data-ttu-id="68bf6-124">EditAndContinueRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-124">EditAndContinueRemap Method</span></span>](icordebugmanagedcallback-editandcontinueremap-method.md)|<span data-ttu-id="68bf6-125">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-125">Deprecated.</span></span> <span data-ttu-id="68bf6-126">다시 매핑 이벤트가 IDE에 전송 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-126">Notifies the debugger that a remap event has been sent to the IDE.</span></span>|  
|[<span data-ttu-id="68bf6-127">EvalComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-127">EvalComplete Method</span></span>](icordebugmanagedcallback-evalcomplete-method.md)|<span data-ttu-id="68bf6-128">평가가 완료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-128">Notifies the debugger that an evaluation has been completed.</span></span>|  
|[<span data-ttu-id="68bf6-129">EvalException 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-129">EvalException Method</span></span>](icordebugmanagedcallback-evalexception-method.md)|<span data-ttu-id="68bf6-130">처리 되지 않은 예외를 사용 하 여 평가가 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-130">Notifies the debugger that an evaluation has been terminated with an unhandled exception.</span></span>|  
|[<span data-ttu-id="68bf6-131">Exception 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-131">Exception Method</span></span>](icordebugmanagedcallback-exception-method.md)|<span data-ttu-id="68bf6-132">관리 코드에서 예외가 throw 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-132">Notifies the debugger that an exception has been thrown from managed code.</span></span>|  
|[<span data-ttu-id="68bf6-133">ExitAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-133">ExitAppDomain Method</span></span>](icordebugmanagedcallback-exitappdomain-method.md)|<span data-ttu-id="68bf6-134">응용 프로그램 도메인이 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-134">Notifies the debugger that an application domain has exited.</span></span>|  
|[<span data-ttu-id="68bf6-135">ExitProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-135">ExitProcess Method</span></span>](icordebugmanagedcallback-exitprocess-method.md)|<span data-ttu-id="68bf6-136">프로세스가 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-136">Notifies the debugger that a process has exited.</span></span>|  
|[<span data-ttu-id="68bf6-137">ExitThread 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-137">ExitThread Method</span></span>](icordebugmanagedcallback-exitthread-method.md)|<span data-ttu-id="68bf6-138">관리 코드를 실행 하는 스레드가 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-138">Notifies the debugger that a thread that was executing managed code has exited.</span></span>|  
|[<span data-ttu-id="68bf6-139">LoadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-139">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)|<span data-ttu-id="68bf6-140">CLR 어셈블리가 성공적으로 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-140">Notifies the debugger that a CLR assembly has been successfully loaded.</span></span>|  
|[<span data-ttu-id="68bf6-141">LoadClass 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-141">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)|<span data-ttu-id="68bf6-142">클래스가 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-142">Notifies the debugger that a class has been loaded.</span></span>|  
|[<span data-ttu-id="68bf6-143">LoadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-143">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)|<span data-ttu-id="68bf6-144">CLR 모듈이 성공적으로 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-144">Notifies the debugger that a CLR module has been successfully loaded.</span></span>|  
|[<span data-ttu-id="68bf6-145">LogMessage 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-145">LogMessage Method</span></span>](icordebugmanagedcallback-logmessage-method.md)|<span data-ttu-id="68bf6-146">CLR 관리 스레드가 클래스의 메서드를 호출 하 여 이벤트를 기록 했음을 디버거에 알립니다 <xref:System.Diagnostics.EventLog> .</span><span class="sxs-lookup"><span data-stu-id="68bf6-146">Notifies the debugger that a CLR managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>|  
|[<span data-ttu-id="68bf6-147">LogSwitch 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-147">LogSwitch Method</span></span>](icordebugmanagedcallback-logswitch-method.md)|<span data-ttu-id="68bf6-148"><xref:System.Diagnostics.Switch>디버깅/추적 스위치를 만들거나 수정 하거나 삭제 하기 위해 CLR 관리 스레드에서 클래스의 메서드를 호출 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-148">Notifies the debugger that a CLR managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>|  
|[<span data-ttu-id="68bf6-149">NameChange 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-149">NameChange Method</span></span>](icordebugmanagedcallback-namechange-method.md)|<span data-ttu-id="68bf6-150">응용 프로그램 도메인 또는 스레드의 이름이 변경 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-150">Notifies the debugger that the name of either an application domain or thread has changed.</span></span>|  
|[<span data-ttu-id="68bf6-151">StepComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-151">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)|<span data-ttu-id="68bf6-152">단계가 완료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-152">Notifies the debugger that a step has completed.</span></span>|  
|[<span data-ttu-id="68bf6-153">UnloadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-153">UnloadAssembly Method</span></span>](icordebugmanagedcallback-unloadassembly-method.md)|<span data-ttu-id="68bf6-154">CLR 어셈블리가 언로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-154">Notifies the debugger that a CLR assembly has been unloaded.</span></span>|  
|[<span data-ttu-id="68bf6-155">UnloadClass 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-155">UnloadClass Method</span></span>](icordebugmanagedcallback-unloadclass-method.md)|<span data-ttu-id="68bf6-156">클래스가 언로드되고 있음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-156">Notifies the debugger that a class is being unloaded.</span></span>|  
|[<span data-ttu-id="68bf6-157">UnloadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-157">UnloadModule Method</span></span>](icordebugmanagedcallback-unloadmodule-method.md)|<span data-ttu-id="68bf6-158">CLR 모듈 (DLL)이 언로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-158">Notifies the debugger that a CLR module (DLL) has been unloaded.</span></span>|  
|[<span data-ttu-id="68bf6-159">UpdateModuleSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="68bf6-159">UpdateModuleSymbols Method</span></span>](icordebugmanagedcallback-updatemodulesymbols-method.md)|<span data-ttu-id="68bf6-160">CLR 모듈의 기호가 변경 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-160">Notifies the debugger that the symbols for a CLR module have changed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68bf6-161">설명</span><span class="sxs-lookup"><span data-stu-id="68bf6-161">Remarks</span></span>  

 <span data-ttu-id="68bf6-162">모든 콜백은 동일한 스레드에서 호출 되며 동기화 된 상태의 프로세스와 함께 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-162">All callbacks are serialized, called in the same thread, and called with the process in the synchronized state.</span></span>  
  
 <span data-ttu-id="68bf6-163">각 콜백 구현에서는 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 를 호출 하 여 실행을 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-163">Each callback implementation must call [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to resume execution.</span></span> <span data-ttu-id="68bf6-164">`ICorDebugController::Continue`콜백이 반환 되기 전에가 호출 되지 않으면 프로세스가 중지 된 상태로 유지 되 고가 호출 될 때까지 이벤트 콜백이 더 이상 발생 하지 않습니다 `ICorDebugController::Continue` .</span><span class="sxs-lookup"><span data-stu-id="68bf6-164">If `ICorDebugController::Continue` is not called before the callback returns, the process will remain stopped and no more event callbacks will occur until `ICorDebugController::Continue` is called.</span></span>  
  
 <span data-ttu-id="68bf6-165">디버거는 .NET Framework 버전 2.0 응용 프로그램을 디버깅 하는 경우 [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) 을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-165">A debugger must implement [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) if it is debugging .NET Framework version 2.0 applications.</span></span> <span data-ttu-id="68bf6-166">또는의 인스턴스 `ICorDebugManagedCallback` 는 `ICorDebugManagedCallback2` [ICorDebug:: setmanagedhandler](icordebug-setmanagedhandler-method.md)에 콜백 개체로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-166">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68bf6-167">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68bf6-167">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68bf6-168">요구 사항</span><span class="sxs-lookup"><span data-stu-id="68bf6-168">Requirements</span></span>  

 <span data-ttu-id="68bf6-169">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68bf6-169">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68bf6-170">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68bf6-170">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68bf6-171">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68bf6-171">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68bf6-172">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68bf6-172">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68bf6-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68bf6-173">See also</span></span>

- [<span data-ttu-id="68bf6-174">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68bf6-174">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="68bf6-175">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68bf6-175">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="68bf6-176">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68bf6-176">Debugging Interfaces</span></span>](debugging-interfaces.md)
