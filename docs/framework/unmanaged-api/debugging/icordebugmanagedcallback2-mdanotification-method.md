---
title: ICorDebugManagedCallback2::MDANotification 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
ms.openlocfilehash: f850b3cd35fda8bd554b99e14553100008cb4eca
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208527"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="83d45-102">ICorDebugManagedCallback2::MDANotification 메서드</span><span class="sxs-lookup"><span data-stu-id="83d45-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="83d45-103">코드 실행이 디버깅 중인 응용 프로그램에서 MDA (관리 디버깅 도우미)를 발견 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d45-104">구문</span><span class="sxs-lookup"><span data-stu-id="83d45-104">Syntax</span></span>  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83d45-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83d45-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="83d45-106">진행 MDA가 발생 한 프로세스 또는 응용 프로그램 도메인을 노출 하는 ICorDebugController 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="83d45-107">디버거는 컨트롤러의 프로세스 또는 응용 프로그램 도메인에 대 한 가정을 하지 않아야 합니다. 하지만 항상 인터페이스를 쿼리하여 결정을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="83d45-108">진행 디버그 이벤트가 발생 한 관리 되는 스레드를 노출 하는 ICorDebugThread 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="83d45-109">MDA가 관리 되지 않는 스레드에서 발생 한 경우의 값은 `pThread` null입니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="83d45-110">MDA 개체 자체에서 OS (운영 체제) 스레드 ID를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="83d45-111">진행 MDA 정보를 노출 하는 [ICorDebugMDA](icordebugmda-interface.md) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-111">[in] A pointer to an [ICorDebugMDA](icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83d45-112">설명</span><span class="sxs-lookup"><span data-stu-id="83d45-112">Remarks</span></span>  
 <span data-ttu-id="83d45-113">MDA는 추론 경고 이며, 디버깅 중인 응용 프로그램의 실행을 계속 하기 위해 [ICorDebugController::](icordebugcontroller-continue-method.md) 를 호출 하는 경우를 제외 하 고 명시적 디버거 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="83d45-114">CLR (공용 언어 런타임)은 언제 든 지 어떤 mda가 발생 하는지, 어느 시점에서 어떤 데이터가 지정 된 MDA에 있는지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="83d45-115">따라서 디버거는 특정 MDA 패턴이 필요한 기능을 빌드하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="83d45-116">Mda가 발생 한 후 mda가 큐에 대기 되 고 즉시 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="83d45-117">런타임에서 mda를 발생 시킬 때 mda를 실행 하는 대신 MDA를 실행 하는 안전한 지점에 도달할 때까지 대기 해야 하는 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="83d45-118">또한 런타임은 대기 중인 콜백 집합 하나에서 많은 Mda를 실행할 수 있습니다 ("연결" 이벤트 작업과 유사).</span><span class="sxs-lookup"><span data-stu-id="83d45-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="83d45-119">디버거는 콜백에서 반환 된 직후 인스턴스에 대 한 참조를 해제 `ICorDebugMDA` 하 여 `MDANotification` CLR이 MDA에서 사용 하는 메모리를 재활용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="83d45-120">인스턴스를 해제 하면 많은 Mda가 발생 하는 경우 성능이 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d45-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83d45-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83d45-121">Requirements</span></span>  
 <span data-ttu-id="83d45-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83d45-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83d45-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83d45-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83d45-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83d45-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83d45-125">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83d45-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d45-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83d45-126">See also</span></span>

- [<span data-ttu-id="83d45-127">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="83d45-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="83d45-128">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83d45-128">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="83d45-129">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83d45-129">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
