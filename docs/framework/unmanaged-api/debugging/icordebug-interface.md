---
title: ICorDebug 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
ms.openlocfilehash: 66b50bad0e8d2622922da96c213643ac3be83a9e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895366"
---
# <a name="icordebug-interface"></a><span data-ttu-id="d36a6-102">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d36a6-102">ICorDebug Interface</span></span>
<span data-ttu-id="d36a6-103">개발자가 CLR (공용 언어 런타임) 환경에서 응용 프로그램을 디버그할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d36a6-104">혼합 모드 (관리 코드 및 네이티브 코드) 디버깅은 Windows 95, Windows 98, Windows ME 또는 비 x86 플랫폼 (예: IA64 및 AMD64)에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d36a6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d36a6-105">Methods</span></span>  
  
|<span data-ttu-id="d36a6-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d36a6-106">Method</span></span>|<span data-ttu-id="d36a6-107">설명</span><span class="sxs-lookup"><span data-stu-id="d36a6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d36a6-108">CanLaunchOrAttach 메서드</span><span class="sxs-lookup"><span data-stu-id="d36a6-108">CanLaunchOrAttach Method</span></span>](icordebug-canlaunchorattach-method.md)|<span data-ttu-id="d36a6-109">현재 컴퓨터 및 런타임 구성의 컨텍스트 내에서 새 프로세스를 시작 하거나 지정 된 프로세스에 연결할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="d36a6-110">CreateProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="d36a6-110">CreateProcess Method</span></span>](icordebug-createprocess-method.md)|<span data-ttu-id="d36a6-111">디버거를 제어할 때 프로세스 및 해당 기본 스레드를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="d36a6-112">DebugActiveProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="d36a6-112">DebugActiveProcess Method</span></span>](icordebug-debugactiveprocess-method.md)|<span data-ttu-id="d36a6-113">디버거를 기존 프로세스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="d36a6-114">EnumerateProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="d36a6-114">EnumerateProcesses Method</span></span>](icordebug-enumerateprocesses-method.md)|<span data-ttu-id="d36a6-115">디버깅 중인 프로세스에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="d36a6-116">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="d36a6-116">GetProcess Method</span></span>](icordebug-getprocess-method.md)|<span data-ttu-id="d36a6-117">지정 된 프로세스 ID를 사용 하 여 "ICorDebugProcess" 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="d36a6-118">Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="d36a6-118">Initialize Method</span></span>](icordebug-initialize-method.md)|<span data-ttu-id="d36a6-119">`ICorDebug` 개체를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="d36a6-120">SetManagedHandler 메서드</span><span class="sxs-lookup"><span data-stu-id="d36a6-120">SetManagedHandler Method</span></span>](icordebug-setmanagedhandler-method.md)|<span data-ttu-id="d36a6-121">관리 되는 이벤트에 대 한 이벤트 처리기 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="d36a6-122">SetUnmanagedHandler 메서드</span><span class="sxs-lookup"><span data-stu-id="d36a6-122">SetUnmanagedHandler Method</span></span>](icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="d36a6-123">관리 되지 않는 이벤트에 대 한 이벤트 처리기 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="d36a6-124">Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="d36a6-124">Terminate Method</span></span>](icordebug-terminate-method.md)|<span data-ttu-id="d36a6-125">개체를 `ICorDebug` 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d36a6-126">설명</span><span class="sxs-lookup"><span data-stu-id="d36a6-126">Remarks</span></span>  
 <span data-ttu-id="d36a6-127">`ICorDebug`디버거 프로세스에 대 한 이벤트 처리 루프를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="d36a6-128">디버거는이 인터페이스를 해제 하기 전에 디버깅 중인 모든 프로세스에서 [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) 콜백이 대기 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="d36a6-129">`ICorDebug` 개체는 모든 추가 관리 디버깅을 제어 하는 초기 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="d36a6-130">.NET Framework 버전 1.0 및 1.1에서이 개체는 `CoClass` COM에서 만든 개체 였습니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="d36a6-131">.NET Framework 버전 2.0에서이 개체는 더 이상 `CoClass` 개체가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="d36a6-132">버전을 인식 하는 [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) 함수를 통해 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="d36a6-133">이 새 생성 함수를 사용 하면 클라이언트는 특정 버전의 `ICorDebug`디버깅 API를 에뮬레이션 하는의 특정 구현을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d36a6-134">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d36a6-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d36a6-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d36a6-135">Requirements</span></span>  
 <span data-ttu-id="d36a6-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d36a6-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d36a6-137">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d36a6-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d36a6-138">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d36a6-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d36a6-139">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d36a6-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36a6-140">참조</span><span class="sxs-lookup"><span data-stu-id="d36a6-140">See also</span></span>

- [<span data-ttu-id="d36a6-141">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d36a6-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
