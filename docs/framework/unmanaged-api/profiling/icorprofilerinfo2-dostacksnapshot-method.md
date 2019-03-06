---
title: ICorProfilerInfo2::DoStackSnapshot 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3a558ad6f87995d6c0a0d164cf96376fba12da4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485267"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a><span data-ttu-id="8cc19-102">ICorProfilerInfo2::DoStackSnapshot 메서드</span><span class="sxs-lookup"><span data-stu-id="8cc19-102">ICorProfilerInfo2::DoStackSnapshot Method</span></span>
<span data-ttu-id="8cc19-103">스택에 지정된 된 스레드에 대 한 관리 되는 프레임에 설명 하 고는 콜백을 통해 프로파일러에 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-103">Walks the managed frames on the stack for the specified thread, and sends information to the profiler through a callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cc19-104">구문</span><span class="sxs-lookup"><span data-stu-id="8cc19-104">Syntax</span></span>  
  
```  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cc19-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8cc19-105">Parameters</span></span>  
 `thread`  
 <span data-ttu-id="8cc19-106">[in] 대상 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-106">[in] The ID of the target thread.</span></span>  
  
 <span data-ttu-id="8cc19-107">에 null을 전달 `thread` 현재 스레드에 대 한 스냅숏을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-107">Passing null in `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="8cc19-108">경우는 `ThreadID` 의 다른 스레드에 전달 되는는 CLR (공용 언어 런타임) 스레드를 일시 중단 스냅숏을 수행 하 고 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-108">If a `ThreadID` of a different thread is passed, the common language runtime (CLR) suspends that thread, performs the snapshot, and resumes.</span></span>  
  
 `callback`  
 <span data-ttu-id="8cc19-109">[in] 구현에 대 한 포인터를 [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) 관리 되는 각 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보를 사용 하 여 프로파일러를 제공 하기 위해 CLR에서 호출 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="8cc19-109">[in] A pointer to the implementation of the [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) method, which is called by the CLR to provide the profiler with information on each managed frame and each run of unmanaged frames.</span></span>  
  
 <span data-ttu-id="8cc19-110">`StackSnapshotCallback` 메서드 프로파일러 기록기에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-110">The `StackSnapshotCallback` method is implemented by the profiler writer.</span></span>  
  
 `infoFlags`  
 <span data-ttu-id="8cc19-111">[in] 값을 [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) 하 여 각 프레임에 대 한 다시 전달할 데이터의 양을 지정 하는 열거 `StackSnapshotCallback`합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-111">[in] A value of the [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumeration, which specifies the amount of data to be passed back for each frame by `StackSnapshotCallback`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="8cc19-112">[in] 통해 직접 전달 되는 클라이언트 데이터에 대 한 포인터를 `StackSnapshotCallback` 콜백 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-112">[in] A pointer to the client data, which is passed straight through to the `StackSnapshotCallback` callback function.</span></span>  
  
 `context`  
 <span data-ttu-id="8cc19-113">[in] Win32에 대 한 포인터 `CONTEXT` 스택 워크를 초기값으로 사용 되는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-113">[in] A pointer to a Win32 `CONTEXT` structure, which is used to seed the stack walk.</span></span> <span data-ttu-id="8cc19-114">Win32 `CONTEXT` 구조 CPU 레지스터의 값을 포함 하 고 특정 시점에 CPU의 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-114">The Win32 `CONTEXT` structure contains values of the CPU registers and represents the state of the CPU at a particular moment in time.</span></span>  
  
 <span data-ttu-id="8cc19-115">초기값 스택의 최상위 관리 되지 않는 도우미 코드에는 스택 워크를 시작할 위치를 결정 하는 CLR를 수 있습니다. 그렇지 않으면 초기값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-115">The seed helps the CLR determine where to begin the stack walk, if the top of the stack is unmanaged helper code; otherwise, the seed is ignored.</span></span> <span data-ttu-id="8cc19-116">비동기 워크 초기값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-116">A seed must be supplied for an asynchronous walk.</span></span> <span data-ttu-id="8cc19-117">동기 연습을 수행 하는 없는 초기값이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-117">If you are doing a synchronous walk, no seed is necessary.</span></span>  
  
 <span data-ttu-id="8cc19-118">합니다 `context` 매개 변수는 COR_PRF_SNAPSHOT_CONTEXT 플래그에 전달 된 경우에 유효 합니다 `infoFlags` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-118">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in the `infoFlags` parameter.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="8cc19-119">[in] 크기를 `CONTEXT` 에서 참조 하는 구조는 `context` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-119">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cc19-120">설명</span><span class="sxs-lookup"><span data-stu-id="8cc19-120">Remarks</span></span>  
 <span data-ttu-id="8cc19-121">에 대 한 null 전달 `thread` 현재 스레드에 대 한 스냅숏을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-121">Passing null for `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="8cc19-122">대상 스레드가 일시 중단 된 경우에 스냅숏은 다른 스레드의 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-122">Snapshots can be taken of other threads only if the target thread is suspended at the time.</span></span>  
  
 <span data-ttu-id="8cc19-123">프로파일러를 스택을 하고자 하는 경우 호출 `DoStackSnapshot`합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-123">When the profiler wants to walk the stack, it calls `DoStackSnapshot`.</span></span> <span data-ttu-id="8cc19-124">CLR 해당 호출에서 반환 되기 전에 호출 하면 `StackSnapshotCallback` 여러 번 번 각각에 대 한 관리 되는 프레임 (또는 관리 되지 않는 프레임 실행) 스택에 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-124">Before the CLR returns from that call, it calls your `StackSnapshotCallback` several times, once for each managed frame (or run of unmanaged frames) on the stack.</span></span> <span data-ttu-id="8cc19-125">관리 되지 않는 프레임에 발생 하는 경우를 검색 해야 해당 사용자가 직접.</span><span class="sxs-lookup"><span data-stu-id="8cc19-125">When unmanaged frames are encountered, you must walk them yourself.</span></span>  
  
 <span data-ttu-id="8cc19-126">스택 워크는 순서는 반대 프레임 스택에 푸시된 방법입니다. (마지막 푸시) 첫 번째, 기본 (첫 번째 푸시) 프레임별 마지막 리프입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-126">The order in which the stack is walked is the reverse of how the frames were pushed onto the stack: leaf (last-pushed) frame first, main (first-pushed) frame last.</span></span>  
  
 <span data-ttu-id="8cc19-127">관리 되는 스택 워크에 프로파일러를 프로그래밍 하는 방법에 대 한 자세한 내용은 참조 하세요. [Profiler Stack Walking.NET Framework 2.0 in에서: Basics and Beyond](https://go.microsoft.com/fwlink/?LinkId=73638)합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-127">For more information about how to program the profiler to walk managed stacks, see [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](https://go.microsoft.com/fwlink/?LinkId=73638).</span></span>  
  
 <span data-ttu-id="8cc19-128">다음 섹션에 설명 된 대로 스택 워크가 동기적 이거나 비동기적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-128">A stack walk can be synchronous or asynchronous, as explained in the following sections.</span></span>  
  
## <a name="synchronous-stack-walk"></a><span data-ttu-id="8cc19-129">동기 스택 워크</span><span class="sxs-lookup"><span data-stu-id="8cc19-129">Synchronous Stack Walk</span></span>  
 <span data-ttu-id="8cc19-130">동기 스택 워크가 콜백에 응답에서 현재 스레드의 스택이 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-130">A synchronous stack walk involves walking the stack of the current thread in response to a callback.</span></span> <span data-ttu-id="8cc19-131">시드 또는 일시 중단에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-131">It does not require seeding or suspending.</span></span>  
  
 <span data-ttu-id="8cc19-132">동기 할 프로파일러의 중 하나를 호출 하는 CLR에 대 한 응답에서 호출 하면 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (또는 [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) 메서드를 호출 하면 `DoStackSnapshot` 의 스택을 탐색 하는 현재 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-132">You make a synchronous call when, in response to the CLR calling one of your profiler's [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (or [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) methods, you call `DoStackSnapshot` to walk the stack of the current thread.</span></span> <span data-ttu-id="8cc19-133">스택의 모양은 알림을에서 같은 확인 하려는 경우에 유용 [icorprofilercallback:: Objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-133">This is useful when you want to see what the stack looks like at a notification such as [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span> <span data-ttu-id="8cc19-134">호출 하면 `DoStackSnapshot` 내에서 사용자 `ICorProfilerCallback` 에서 null을 전달 하는 메서드를 합니다 `context` 및 `thread` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-134">You just call `DoStackSnapshot` from within your `ICorProfilerCallback` method, passing null in the `context` and `thread` parameters.</span></span>  
  
## <a name="asynchronous-stack-walk"></a><span data-ttu-id="8cc19-135">비동기 스택 워크</span><span class="sxs-lookup"><span data-stu-id="8cc19-135">Asynchronous Stack Walk</span></span>  
 <span data-ttu-id="8cc19-136">비동기 스택 워크에는 다른 스레드의 스택을 또는 콜백을 있지만 현재 스레드의 명령 포인터를 하이재킹 하 여 응답에 없는 현재 스레드의 스택을 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-136">An asynchronous stack walk entails walking the stack of a different thread, or walking the stack of the current thread, not in response to a callback, but by hijacking the current thread's instruction pointer.</span></span> <span data-ttu-id="8cc19-137">비동기 워크 필요한 경우 스택의 최상위 플랫폼의 포함 되지 않은 비관리 코드에는 초기값 호출 (PInvoke) 또는 COM 호출 되지만 CLR 자체의 도우미 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-137">An asynchronous walk requires a seed if the top of the stack is unmanaged code that is not part of a platform invoke (PInvoke) or COM call, but helper code in the CLR itself.</span></span> <span data-ttu-id="8cc19-138">예를 들어-just-in-time (JIT) 컴파일 또는 가비지 수집 수행 하는 코드는 도우미 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-138">For example, code that does just-in-time (JIT) compiling or garbage collection is helper code.</span></span>  
  
 <span data-ttu-id="8cc19-139">직접 대상 스레드가 일시 중단 하 여 초기값을 가져와야 하 고 해당 스택 탐색 최상위 찾을 때까지 직접 관리 되는 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-139">You obtain a seed by directly suspending the target thread and walking its stack yourself, until you find the topmost managed frame.</span></span> <span data-ttu-id="8cc19-140">대상 스레드가 일시 중단 한 후에 대상 스레드의 현재 등록 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-140">After the target thread is suspended, get the target thread's current register context.</span></span> <span data-ttu-id="8cc19-141">다음으로, 레지스터 컨텍스트로 호출 하 여 관리 되지 않는 코드를 가리키는지 여부를 결정 [icorprofilerinfo:: Getfunctionfromip](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) -반환 하는 경우는 `FunctionID` 0과 같지 프레임은 관리 되지 않는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-141">Next, determine whether the register context points to unmanaged code by calling [ICorProfilerInfo::GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) — if it returns a `FunctionID` equal to zero, the frame is unmanaged code.</span></span> <span data-ttu-id="8cc19-142">이제 첫 번째 관리 되는 프레임에 도달 하 고 해당 프레임에 대 한 등록 컨텍스트를 기반으로 초기값 컨텍스트에서 계산 될 때까지 스택의 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-142">Now, walk the stack until you reach the first managed frame, and then calculate the seed context based on the register context for that frame.</span></span>  
  
 <span data-ttu-id="8cc19-143">호출 `DoStackSnapshot` 비동기 스택 워크를 시작 하려면 초기값 컨텍스트를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-143">Call `DoStackSnapshot` with your seed context to begin the asynchronous stack walk.</span></span> <span data-ttu-id="8cc19-144">시드를 제공 하지 않는 경우 `DoStackSnapshot` 스택의 맨 위에 있는 관리 되는 프레임을 건너뛸 수 있습니다 하 고 결과적으로 표시 됩니다 스택 워크가 불완전 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-144">If you do not supply a seed, `DoStackSnapshot` might skip managed frames at the top of the stack and, consequently, will give you an incomplete stack walk.</span></span> <span data-ttu-id="8cc19-145">JIT 컴파일 또는 네이티브 이미지 생성기 (Ngen.exe)를 가리켜야 초기값을 제공한 경우-코드 생성 그렇지 않으면 `DoStackSnapshot` CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-145">If you do supply a seed, it must point to JIT-compiled or Native Image Generator (Ngen.exe)-generated code; otherwise, `DoStackSnapshot` returns the failure code, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span></span>  
  
 <span data-ttu-id="8cc19-146">비동기 스택 워크 쉽게 교착 상태가 발생 하거나 이러한 지침을 따르지 않으면 액세스 위반을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-146">Asynchronous stack walks can easily cause deadlocks or access violations, unless you follow these guidelines:</span></span>  
  
-   <span data-ttu-id="8cc19-147">스레드를 직접 일시 중단 하면 관리 코드에 실행 된 적이 없는 스레드에서만 다른 스레드는 일시 중단 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-147">When you directly suspend threads, remember that only a thread that has never run managed code can suspend another thread.</span></span>  
  
-   <span data-ttu-id="8cc19-148">항상 블록에 [icorprofilercallback:: Threaddestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) 스레드의 스택 워크가 완료 될 때까지 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-148">Always block in your [ICorProfilerCallback::ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) callback until that thread's stack walk is complete.</span></span>  
  
-   <span data-ttu-id="8cc19-149">프로파일러 가비지 컬렉션을 트리거할 수 있는 CLR 함수를 호출 하는 동안 잠금을 유지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-149">Do not hold a lock while your profiler calls into a CLR function that can trigger a garbage collection.</span></span> <span data-ttu-id="8cc19-150">즉, 소유 하는 스레드에 가비지 수집을 트리거하는 호출을 해야 하는 경우에 잠금을 포함 되지 않은 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-150">That is, do not hold a lock if the owning thread might make a call that triggers a garbage collection.</span></span>  
  
 <span data-ttu-id="8cc19-151">이기도 교착 상태의 위험이 호출 하는 경우 `DoStackSnapshot` 별도 대상 스레드의 스택을 탐색할 수 있도록 프로파일러 만든 스레드에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-151">There is also a risk of deadlock if you call `DoStackSnapshot` from a thread that your profiler has created so that you can walk the stack of a separate target thread.</span></span> <span data-ttu-id="8cc19-152">특정 처음 만든 스레드가 들어가기 `ICorProfilerInfo*` 메서드 (포함 하 여 `DoStackSnapshot`), CLR 스레드별, CLR과 관련 된 해당 스레드에서 초기화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-152">The first time the thread you created enters certain `ICorProfilerInfo*` methods (including `DoStackSnapshot`), the CLR will perform per-thread, CLR-specific initialization on that thread.</span></span> <span data-ttu-id="8cc19-153">프로파일러 대상 스레드가 해당 스택 워크를 시도 하는 일시 중단 및 해당 대상 스레드가이 스레드별 초기화를 수행 하는 데 필요한 잠금을 소유한에 발생 하는 경우 교착 상태가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-153">If your profiler has suspended the target thread whose stack you are trying to walk, and if that target thread happened to own a lock necessary for performing this per-thread initialization, a deadlock will occur.</span></span> <span data-ttu-id="8cc19-154">이 교착 상태를 방지 하려면 초기에 호출 확인 `DoStackSnapshot` 프로파일러에서 만든 스레드를 탐색 하에서 별도 스레드를 대상으로 하지만 대상 스레드를 먼저 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-154">To avoid this deadlock, make an initial call into `DoStackSnapshot` from your profiler-created thread to walk a separate target thread, but do not suspend the target thread first.</span></span> <span data-ttu-id="8cc19-155">이 초기 호출 스레드를 초기화 하는 교착 상태 없이 완료할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-155">This initial call ensures that the per-thread initialization can complete without deadlock.</span></span> <span data-ttu-id="8cc19-156">하는 경우 `DoStackSnapshot` 성공 하 고 하나 이상의 프레임을 보고 해당 지점을 지나서 모든 대상 스레드 및 호출을 일시 중지 하려면 해당 프로파일러 만든 스레드에 대 한 안전 하 게 됩니다 `DoStackSnapshot` 대상 스레드의 스택 워크를 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cc19-156">If `DoStackSnapshot` succeeds and reports at least one frame, after that point, it will be safe for that profiler-created thread to suspend any target thread and call `DoStackSnapshot` to walk the stack of that target thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cc19-157">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8cc19-157">Requirements</span></span>  
 <span data-ttu-id="8cc19-158">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8cc19-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cc19-159">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8cc19-159">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8cc19-160">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cc19-160">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cc19-161">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cc19-161">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cc19-162">참고자료</span><span class="sxs-lookup"><span data-stu-id="8cc19-162">See also</span></span>
- [<span data-ttu-id="8cc19-163">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8cc19-163">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="8cc19-164">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8cc19-164">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
