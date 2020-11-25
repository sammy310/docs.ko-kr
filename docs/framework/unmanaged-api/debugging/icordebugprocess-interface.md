---
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
ms.openlocfilehash: 7f9d4ac99234545ef75d9b91e6e84f79a133ffef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694921"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="c32e0-102">ICorDebugProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c32e0-102">ICorDebugProcess Interface</span></span>

<span data-ttu-id="c32e0-103">관리 코드를 실행하는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="c32e0-104">이 인터페이스는 ICorDebugController의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c32e0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-105">Methods</span></span>  
  
|<span data-ttu-id="c32e0-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-106">Method</span></span>|<span data-ttu-id="c32e0-107">설명</span><span class="sxs-lookup"><span data-stu-id="c32e0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c32e0-108">ClearCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-108">ClearCurrentException Method</span></span>](icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="c32e0-109">지정 된 스레드에서 현재 관리 되지 않는 예외를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="c32e0-110">EnableLogMessages 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-110">EnableLogMessages Method</span></span>](icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="c32e0-111">디버거로 로그 메시지 보내기를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="c32e0-112">EnumerateAppDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-112">EnumerateAppDomains Method</span></span>](icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="c32e0-113">프로세스의 모든 응용 프로그램 도메인을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="c32e0-114">EnumerateObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-114">EnumerateObjects Method</span></span>](icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="c32e0-115">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-115">Not implemented.</span></span>|  
|[<span data-ttu-id="c32e0-116">GetHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-116">GetHandle Method</span></span>](icordebugprocess-gethandle-method.md)|<span data-ttu-id="c32e0-117">프로세스에 대 한 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="c32e0-118">GetHelperThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-118">GetHelperThreadID Method</span></span>](icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="c32e0-119">디버거의 내부 도우미 스레드에 대 한 OS (운영 체제) 스레드 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="c32e0-120">GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-120">GetID Method</span></span>](icordebugprocess-getid-method.md)|<span data-ttu-id="c32e0-121">프로세스의 OS (운영 체제) ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="c32e0-122">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-122">GetObject Method</span></span>](icordebugprocess-getobject-method.md)|<span data-ttu-id="c32e0-123">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-123">Not implemented.</span></span>|  
|[<span data-ttu-id="c32e0-124">GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-124">GetThread Method</span></span>](icordebugprocess-getthread-method.md)|<span data-ttu-id="c32e0-125">지정 된 OS 스레드 ID를 가진 ICorDebugThread 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="c32e0-126">GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-126">GetThreadContext Method</span></span>](icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="c32e0-127">지정 된 스레드에 대 한 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="c32e0-128">IsOSSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-128">IsOSSuspended Method</span></span>](icordebugprocess-isossuspended-method.md)|<span data-ttu-id="c32e0-129">디버거가 프로세스를 중지 한 결과로 스레드가 일시 중단 되었는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="c32e0-130">IsTransitionStub 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-130">IsTransitionStub Method</span></span>](icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="c32e0-131">관리 코드로의 전환을 유발 하는 스텁이 스텁 내에 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="c32e0-132">ModifyLogSwitch 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-132">ModifyLogSwitch Method</span></span>](icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="c32e0-133">지정 된 로그 스위치의 심각도 수준을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="c32e0-134">ReadMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-134">ReadMemory Method</span></span>](icordebugprocess-readmemory-method.md)|<span data-ttu-id="c32e0-135">프로세스에서 메모리를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="c32e0-136">SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-136">SetThreadContext Method</span></span>](icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="c32e0-137">지정 된 스레드에 대 한 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="c32e0-138">ThreadForFiberCookie 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-138">ThreadForFiberCookie Method</span></span>](icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="c32e0-139">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-139">Deprecated.</span></span>|  
|[<span data-ttu-id="c32e0-140">WriteMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="c32e0-140">WriteMemory Method</span></span>](icordebugprocess-writememory-method.md)|<span data-ttu-id="c32e0-141">프로세스의 메모리 영역에 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c32e0-142">설명</span><span class="sxs-lookup"><span data-stu-id="c32e0-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c32e0-143">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c32e0-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c32e0-144">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c32e0-144">Requirements</span></span>  

 <span data-ttu-id="c32e0-145">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c32e0-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c32e0-146">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c32e0-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c32e0-147">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c32e0-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c32e0-148">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c32e0-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c32e0-149">참조</span><span class="sxs-lookup"><span data-stu-id="c32e0-149">See also</span></span>

- [<span data-ttu-id="c32e0-150">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c32e0-150">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="c32e0-151">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c32e0-151">Debugging Interfaces</span></span>](debugging-interfaces.md)
