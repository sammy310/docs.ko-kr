---
description: '자세히 알아보기: ICorDebugProcess 인터페이스'
title: ICorDebugProcess 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
ms.openlocfilehash: 7172ee12bf450235db1c18601c8ff7de51435520
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746791"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="9ac0c-103">ICorDebugProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ac0c-103">ICorDebugProcess Interface</span></span>

<span data-ttu-id="9ac0c-104">관리 코드를 실행하는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-104">Represents a process that is executing managed code.</span></span> <span data-ttu-id="9ac0c-105">이 인터페이스는 ICorDebugController의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-105">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ac0c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-106">Methods</span></span>  
  
|<span data-ttu-id="9ac0c-107">메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-107">Method</span></span>|<span data-ttu-id="9ac0c-108">설명</span><span class="sxs-lookup"><span data-stu-id="9ac0c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ac0c-109">ClearCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-109">ClearCurrentException Method</span></span>](icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="9ac0c-110">지정 된 스레드에서 현재 관리 되지 않는 예외를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-110">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="9ac0c-111">EnableLogMessages 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-111">EnableLogMessages Method</span></span>](icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="9ac0c-112">디버거로 로그 메시지 보내기를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-112">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="9ac0c-113">EnumerateAppDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-113">EnumerateAppDomains Method</span></span>](icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="9ac0c-114">프로세스의 모든 응용 프로그램 도메인을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-114">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="9ac0c-115">EnumerateObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-115">EnumerateObjects Method</span></span>](icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="9ac0c-116">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-116">Not implemented.</span></span>|  
|[<span data-ttu-id="9ac0c-117">GetHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-117">GetHandle Method</span></span>](icordebugprocess-gethandle-method.md)|<span data-ttu-id="9ac0c-118">프로세스에 대 한 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-118">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="9ac0c-119">GetHelperThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-119">GetHelperThreadID Method</span></span>](icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="9ac0c-120">디버거의 내부 도우미 스레드에 대 한 OS (운영 체제) 스레드 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-120">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="9ac0c-121">GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-121">GetID Method</span></span>](icordebugprocess-getid-method.md)|<span data-ttu-id="9ac0c-122">프로세스의 OS (운영 체제) ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-122">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="9ac0c-123">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-123">GetObject Method</span></span>](icordebugprocess-getobject-method.md)|<span data-ttu-id="9ac0c-124">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-124">Not implemented.</span></span>|  
|[<span data-ttu-id="9ac0c-125">GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-125">GetThread Method</span></span>](icordebugprocess-getthread-method.md)|<span data-ttu-id="9ac0c-126">지정 된 OS 스레드 ID를 가진 ICorDebugThread 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-126">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="9ac0c-127">GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-127">GetThreadContext Method</span></span>](icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="9ac0c-128">지정 된 스레드에 대 한 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-128">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="9ac0c-129">IsOSSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-129">IsOSSuspended Method</span></span>](icordebugprocess-isossuspended-method.md)|<span data-ttu-id="9ac0c-130">디버거가 프로세스를 중지 한 결과로 스레드가 일시 중단 되었는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-130">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="9ac0c-131">IsTransitionStub 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-131">IsTransitionStub Method</span></span>](icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="9ac0c-132">관리 코드로의 전환을 유발 하는 스텁이 스텁 내에 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-132">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="9ac0c-133">ModifyLogSwitch 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-133">ModifyLogSwitch Method</span></span>](icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="9ac0c-134">지정 된 로그 스위치의 심각도 수준을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-134">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="9ac0c-135">ReadMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-135">ReadMemory Method</span></span>](icordebugprocess-readmemory-method.md)|<span data-ttu-id="9ac0c-136">프로세스에서 메모리를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-136">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="9ac0c-137">SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-137">SetThreadContext Method</span></span>](icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="9ac0c-138">지정 된 스레드에 대 한 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-138">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="9ac0c-139">ThreadForFiberCookie 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-139">ThreadForFiberCookie Method</span></span>](icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="9ac0c-140">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-140">Deprecated.</span></span>|  
|[<span data-ttu-id="9ac0c-141">WriteMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="9ac0c-141">WriteMemory Method</span></span>](icordebugprocess-writememory-method.md)|<span data-ttu-id="9ac0c-142">프로세스의 메모리 영역에 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-142">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ac0c-143">설명</span><span class="sxs-lookup"><span data-stu-id="9ac0c-143">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ac0c-144">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-144">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ac0c-145">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ac0c-145">Requirements</span></span>  

 <span data-ttu-id="9ac0c-146">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ac0c-146">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ac0c-147">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ac0c-147">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ac0c-148">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ac0c-148">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ac0c-149">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ac0c-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac0c-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ac0c-150">See also</span></span>

- [<span data-ttu-id="9ac0c-151">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ac0c-151">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="9ac0c-152">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ac0c-152">Debugging Interfaces</span></span>](debugging-interfaces.md)
