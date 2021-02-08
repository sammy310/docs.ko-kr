---
description: '자세히 알아보기: ICorDebug 인터페이스'
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
ms.openlocfilehash: b989013f7eb54e163feeb965e10448a3a1756e3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772525"
---
# <a name="icordebug-interface"></a><span data-ttu-id="63f31-103">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63f31-103">ICorDebug Interface</span></span>

<span data-ttu-id="63f31-104">개발자가 CLR (공용 언어 런타임) 환경에서 응용 프로그램을 디버그할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-104">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63f31-105">혼합 모드 (관리 코드 및 네이티브 코드) 디버깅은 Windows 95, Windows 98, Windows ME 또는 비 x86 플랫폼 (예: IA64 및 AMD64)에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-105">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63f31-106">메서드</span><span class="sxs-lookup"><span data-stu-id="63f31-106">Methods</span></span>  
  
|<span data-ttu-id="63f31-107">메서드</span><span class="sxs-lookup"><span data-stu-id="63f31-107">Method</span></span>|<span data-ttu-id="63f31-108">설명</span><span class="sxs-lookup"><span data-stu-id="63f31-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63f31-109">CanLaunchOrAttach 메서드</span><span class="sxs-lookup"><span data-stu-id="63f31-109">CanLaunchOrAttach Method</span></span>](icordebug-canlaunchorattach-method.md)|<span data-ttu-id="63f31-110">현재 컴퓨터 및 런타임 구성의 컨텍스트 내에서 새 프로세스를 시작 하거나 지정 된 프로세스에 연결할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-110">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="63f31-111">CreateProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="63f31-111">CreateProcess Method</span></span>](icordebug-createprocess-method.md)|<span data-ttu-id="63f31-112">디버거를 제어할 때 프로세스 및 해당 기본 스레드를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-112">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="63f31-113">DebugActiveProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="63f31-113">DebugActiveProcess Method</span></span>](icordebug-debugactiveprocess-method.md)|<span data-ttu-id="63f31-114">디버거를 기존 프로세스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-114">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="63f31-115">EnumerateProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="63f31-115">EnumerateProcesses Method</span></span>](icordebug-enumerateprocesses-method.md)|<span data-ttu-id="63f31-116">디버깅 중인 프로세스에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-116">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="63f31-117">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="63f31-117">GetProcess Method</span></span>](icordebug-getprocess-method.md)|<span data-ttu-id="63f31-118">지정 된 프로세스 ID를 사용 하 여 "ICorDebugProcess" 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-118">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="63f31-119">Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="63f31-119">Initialize Method</span></span>](icordebug-initialize-method.md)|<span data-ttu-id="63f31-120">초기화는 `ICorDebug` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-120">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="63f31-121">SetManagedHandler 메서드</span><span class="sxs-lookup"><span data-stu-id="63f31-121">SetManagedHandler Method</span></span>](icordebug-setmanagedhandler-method.md)|<span data-ttu-id="63f31-122">관리 되는 이벤트에 대 한 이벤트 처리기 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-122">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="63f31-123">SetUnmanagedHandler 메서드</span><span class="sxs-lookup"><span data-stu-id="63f31-123">SetUnmanagedHandler Method</span></span>](icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="63f31-124">관리 되지 않는 이벤트에 대 한 이벤트 처리기 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-124">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="63f31-125">Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="63f31-125">Terminate Method</span></span>](icordebug-terminate-method.md)|<span data-ttu-id="63f31-126">개체를 종료 `ICorDebug` 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-126">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63f31-127">설명</span><span class="sxs-lookup"><span data-stu-id="63f31-127">Remarks</span></span>  

 <span data-ttu-id="63f31-128">`ICorDebug` 디버거 프로세스에 대 한 이벤트 처리 루프를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-128">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="63f31-129">디버거는이 인터페이스를 해제 하기 전에 디버깅 중인 모든 프로세스에서 [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) 콜백이 대기 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-129">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="63f31-130">`ICorDebug`개체는 모든 추가 관리 디버깅을 제어 하는 초기 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-130">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="63f31-131">.NET Framework 버전 1.0 및 1.1에서이 개체는 `CoClass` COM에서 만든 개체 였습니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-131">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="63f31-132">.NET Framework 버전 2.0에서이 개체는 더 이상 `CoClass` 개체가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-132">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="63f31-133">버전을 인식 하는 [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) 함수를 통해 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-133">It must be created by the [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="63f31-134">이 새 생성 함수를 사용 하면 클라이언트는 특정 버전의 디버깅 API를 에뮬레이션 하는의 특정 구현을 가져올 수 있습니다 `ICorDebug` .</span><span class="sxs-lookup"><span data-stu-id="63f31-134">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63f31-135">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63f31-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63f31-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63f31-136">Requirements</span></span>  

 <span data-ttu-id="63f31-137">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63f31-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63f31-138">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63f31-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63f31-139">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63f31-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63f31-140">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63f31-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f31-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63f31-141">See also</span></span>

- [<span data-ttu-id="63f31-142">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63f31-142">Debugging Interfaces</span></span>](debugging-interfaces.md)
