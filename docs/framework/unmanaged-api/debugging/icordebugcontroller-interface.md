---
title: ICorDebugController 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
ms.openlocfilehash: e494bbb24e8f2245593e7945625e72e70ae1dde5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892763"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="f200b-102">ICorDebugController 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f200b-102">ICorDebugController Interface</span></span>

<span data-ttu-id="f200b-103"><xref:System.Diagnostics.Process>나 <xref:System.AppDomain> 같이 코드 실행 컨텍스트를 제어할 수 있는 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f200b-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f200b-104">Methods</span></span>  
  
|<span data-ttu-id="f200b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f200b-105">Method</span></span>|<span data-ttu-id="f200b-106">설명</span><span class="sxs-lookup"><span data-stu-id="f200b-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="f200b-107">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="f200b-108">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="f200b-109">Continue 메서드</span><span class="sxs-lookup"><span data-stu-id="f200b-109">Continue Method</span></span>](icordebugcontroller-continue-method.md)|<span data-ttu-id="f200b-110">[ICorDebugController:: Stop](icordebugcontroller-stop-method.md)호출 후 관리 되는 스레드의 실행을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="f200b-111">Detach 메서드</span><span class="sxs-lookup"><span data-stu-id="f200b-111">Detach Method</span></span>](icordebugcontroller-detach-method.md)|<span data-ttu-id="f200b-112">프로세스 또는 응용 프로그램 도메인에서 디버거를 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="f200b-113">EnumerateThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="f200b-113">EnumerateThreads Method</span></span>](icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="f200b-114">프로세스의 활성 관리 되는 스레드에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="f200b-115">HasQueuedCallbacks 메서드</span><span class="sxs-lookup"><span data-stu-id="f200b-115">HasQueuedCallbacks Method</span></span>](icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="f200b-116">지정 된 스레드에 대해 관리 되는 콜백이 현재 대기 중인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="f200b-117">IsRunning 메서드</span><span class="sxs-lookup"><span data-stu-id="f200b-117">IsRunning Method</span></span>](icordebugcontroller-isrunning-method.md)|<span data-ttu-id="f200b-118">프로세스의 스레드가 현재 자유롭게 실행 중인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="f200b-119">SetAllThreadsDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="f200b-119">SetAllThreadsDebugState Method</span></span>](icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="f200b-120">프로세스에 있는 모든 관리 되는 스레드의 디버그 상태를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="f200b-121">Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="f200b-121">Stop Method</span></span>](icordebugcontroller-stop-method.md)|<span data-ttu-id="f200b-122">프로세스에서 관리 코드를 실행 하는 모든 스레드에서 협조적 중지를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="f200b-123">Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="f200b-123">Terminate Method</span></span>](icordebugcontroller-terminate-method.md)|<span data-ttu-id="f200b-124">지정 된 종료 코드를 사용 하 여 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f200b-125">설명</span><span class="sxs-lookup"><span data-stu-id="f200b-125">Remarks</span></span>  
 <span data-ttu-id="f200b-126">에서 `ICorDebugController` 프로세스를 제어 하는 경우 범위에 프로세스의 모든 스레드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="f200b-127">가 `ICorDebugController` 응용 프로그램 도메인을 제어 하는 경우 해당 특정 응용 프로그램 도메인의 스레드만 범위에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f200b-128">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f200b-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f200b-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f200b-129">Requirements</span></span>  
 <span data-ttu-id="f200b-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f200b-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f200b-131">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f200b-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f200b-132">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f200b-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f200b-133">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f200b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f200b-134">참조</span><span class="sxs-lookup"><span data-stu-id="f200b-134">See also</span></span>

- [<span data-ttu-id="f200b-135">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f200b-135">Debugging Interfaces</span></span>](debugging-interfaces.md)
