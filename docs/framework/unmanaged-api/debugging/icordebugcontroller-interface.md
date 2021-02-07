---
description: '자세히 알아보기: ICorDebugController 인터페이스'
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
ms.openlocfilehash: 588c41b5b8d87589facd6085655ed0ad415ec3aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710753"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="553f5-103">ICorDebugController 인터페이스</span><span class="sxs-lookup"><span data-stu-id="553f5-103">ICorDebugController Interface</span></span>

<span data-ttu-id="553f5-104"><xref:System.Diagnostics.Process>나 <xref:System.AppDomain> 같이 코드 실행 컨텍스트를 제어할 수 있는 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-104">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="553f5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="553f5-105">Methods</span></span>  
  
|<span data-ttu-id="553f5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="553f5-106">Method</span></span>|<span data-ttu-id="553f5-107">설명</span><span class="sxs-lookup"><span data-stu-id="553f5-107">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="553f5-108">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-108">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="553f5-109">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-109">This method is obsolete.</span></span>|  
|[<span data-ttu-id="553f5-110">Continue 메서드</span><span class="sxs-lookup"><span data-stu-id="553f5-110">Continue Method</span></span>](icordebugcontroller-continue-method.md)|<span data-ttu-id="553f5-111">[ICorDebugController:: Stop](icordebugcontroller-stop-method.md)호출 후 관리 되는 스레드의 실행을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-111">Resumes execution of managed threads after a call to [ICorDebugController::Stop](icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="553f5-112">Detach 메서드</span><span class="sxs-lookup"><span data-stu-id="553f5-112">Detach Method</span></span>](icordebugcontroller-detach-method.md)|<span data-ttu-id="553f5-113">프로세스 또는 응용 프로그램 도메인에서 디버거를 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-113">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="553f5-114">EnumerateThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="553f5-114">EnumerateThreads Method</span></span>](icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="553f5-115">프로세스의 활성 관리 되는 스레드에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-115">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="553f5-116">HasQueuedCallbacks 메서드</span><span class="sxs-lookup"><span data-stu-id="553f5-116">HasQueuedCallbacks Method</span></span>](icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="553f5-117">지정 된 스레드에 대해 관리 되는 콜백이 현재 대기 중인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-117">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="553f5-118">IsRunning 메서드</span><span class="sxs-lookup"><span data-stu-id="553f5-118">IsRunning Method</span></span>](icordebugcontroller-isrunning-method.md)|<span data-ttu-id="553f5-119">프로세스의 스레드가 현재 자유롭게 실행 중인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-119">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="553f5-120">SetAllThreadsDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="553f5-120">SetAllThreadsDebugState Method</span></span>](icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="553f5-121">프로세스에 있는 모든 관리 되는 스레드의 디버그 상태를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-121">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="553f5-122">Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="553f5-122">Stop Method</span></span>](icordebugcontroller-stop-method.md)|<span data-ttu-id="553f5-123">프로세스에서 관리 코드를 실행 하는 모든 스레드에서 협조적 중지를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-123">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="553f5-124">Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="553f5-124">Terminate Method</span></span>](icordebugcontroller-terminate-method.md)|<span data-ttu-id="553f5-125">지정 된 종료 코드를 사용 하 여 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-125">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="553f5-126">설명</span><span class="sxs-lookup"><span data-stu-id="553f5-126">Remarks</span></span>  

 <span data-ttu-id="553f5-127">에서 프로세스를 제어 하는 경우 `ICorDebugController` 범위에 프로세스의 모든 스레드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-127">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="553f5-128">`ICorDebugController`가 응용 프로그램 도메인을 제어 하는 경우 해당 특정 응용 프로그램 도메인의 스레드만 범위에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-128">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="553f5-129">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="553f5-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="553f5-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="553f5-130">Requirements</span></span>  

 <span data-ttu-id="553f5-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="553f5-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="553f5-132">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="553f5-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="553f5-133">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="553f5-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="553f5-134">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="553f5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553f5-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="553f5-135">See also</span></span>

- [<span data-ttu-id="553f5-136">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="553f5-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
