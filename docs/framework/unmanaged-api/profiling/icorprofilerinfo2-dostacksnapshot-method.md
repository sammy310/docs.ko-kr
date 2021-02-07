---
description: ICorProfilerInfo2::D oStackSnapshot 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: e30e11dfe04da1e7a5adfef004036507b724963d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753252"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a><span data-ttu-id="fc21d-103">ICorProfilerInfo2::DoStackSnapshot 메서드</span><span class="sxs-lookup"><span data-stu-id="fc21d-103">ICorProfilerInfo2::DoStackSnapshot Method</span></span>

<span data-ttu-id="fc21d-104">스택에서 관리 되는 프레임을 지정 된 스레드에 대해 보여 주고 콜백을 통해 프로파일러에 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-104">Walks the managed frames on the stack for the specified thread, and sends information to the profiler through a callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc21d-105">구문</span><span class="sxs-lookup"><span data-stu-id="fc21d-105">Syntax</span></span>  
  
```cpp  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc21d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc21d-106">Parameters</span></span>  

 `thread`  
 <span data-ttu-id="fc21d-107">진행 대상 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-107">[in] The ID of the target thread.</span></span>  
  
 <span data-ttu-id="fc21d-108">에서 null을 전달 하면 `thread` 현재 스레드의 스냅숏이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-108">Passing null in `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="fc21d-109">`ThreadID`다른 스레드의이 전달 되 면 CLR (공용 언어 런타임)은 해당 스레드를 일시 중단 하 고, 스냅숏을 수행 하 고,를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-109">If a `ThreadID` of a different thread is passed, the common language runtime (CLR) suspends that thread, performs the snapshot, and resumes.</span></span>  
  
 `callback`  
 <span data-ttu-id="fc21d-110">진행 [StackSnapshotCallback](stacksnapshotcallback-function.md) 메서드의 구현에 대 한 포인터로, 프로파일러에 관리 되는 각 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보를 제공 하기 위해 CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-110">[in] A pointer to the implementation of the [StackSnapshotCallback](stacksnapshotcallback-function.md) method, which is called by the CLR to provide the profiler with information on each managed frame and each run of unmanaged frames.</span></span>  
  
 <span data-ttu-id="fc21d-111">`StackSnapshotCallback`메서드는 프로파일러 작성기에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-111">The `StackSnapshotCallback` method is implemented by the profiler writer.</span></span>  
  
 `infoFlags`  
 <span data-ttu-id="fc21d-112">진행 각 프레임에 대해 다시 전달할 데이터의 양을 지정 하는 [COR_PRF_SNAPSHOT_INFO](cor-prf-snapshot-info-enumeration.md) 열거형의 값입니다 `StackSnapshotCallback` .</span><span class="sxs-lookup"><span data-stu-id="fc21d-112">[in] A value of the [COR_PRF_SNAPSHOT_INFO](cor-prf-snapshot-info-enumeration.md) enumeration, which specifies the amount of data to be passed back for each frame by `StackSnapshotCallback`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="fc21d-113">진행 콜백 함수로 직접 전달 되는 클라이언트 데이터에 대 한 포인터 `StackSnapshotCallback` 입니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-113">[in] A pointer to the client data, which is passed straight through to the `StackSnapshotCallback` callback function.</span></span>  
  
 `context`  
 <span data-ttu-id="fc21d-114">진행 `CONTEXT` 스택 워크의 초기값으로 사용 되는 Win32 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-114">[in] A pointer to a Win32 `CONTEXT` structure, which is used to seed the stack walk.</span></span> <span data-ttu-id="fc21d-115">Win32 `CONTEXT` 구조는 cpu 레지스터의 값을 포함 하며 특정 시점의 cpu 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-115">The Win32 `CONTEXT` structure contains values of the CPU registers and represents the state of the CPU at a particular moment in time.</span></span>  
  
 <span data-ttu-id="fc21d-116">초기값을 사용 하면 스택의 위쪽이 관리 되지 않는 도우미 코드 이면 CLR에서 스택 워크를 시작할 위치를 결정할 수 있습니다. 그렇지 않으면 초기값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-116">The seed helps the CLR determine where to begin the stack walk, if the top of the stack is unmanaged helper code; otherwise, the seed is ignored.</span></span> <span data-ttu-id="fc21d-117">비동기 워크에 대해 초기값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-117">A seed must be supplied for an asynchronous walk.</span></span> <span data-ttu-id="fc21d-118">동기식 연습을 수행 하는 경우 시드가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-118">If you are doing a synchronous walk, no seed is necessary.</span></span>  
  
 <span data-ttu-id="fc21d-119">매개 변수는 `context` COR_PRF_SNAPSHOT_CONTEXT 플래그가 매개 변수에 전달 된 경우에만 유효 `infoFlags` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-119">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in the `infoFlags` parameter.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="fc21d-120">진행 `CONTEXT` 매개 변수에서 참조 하는 구조체의 크기입니다 `context` .</span><span class="sxs-lookup"><span data-stu-id="fc21d-120">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc21d-121">설명</span><span class="sxs-lookup"><span data-stu-id="fc21d-121">Remarks</span></span>  

 <span data-ttu-id="fc21d-122">에 null을 전달 하면 `thread` 현재 스레드의 스냅숏이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-122">Passing null for `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="fc21d-123">대상 스레드가 현재 일시 중단 된 경우에만 다른 스레드에 대 한 스냅숏을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-123">Snapshots can be taken of other threads only if the target thread is suspended at the time.</span></span>  
  
 <span data-ttu-id="fc21d-124">프로파일러가 스택을 탐색 하려는 경우를 호출 `DoStackSnapshot` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-124">When the profiler wants to walk the stack, it calls `DoStackSnapshot`.</span></span> <span data-ttu-id="fc21d-125">CLR이 해당 호출에서 반환 되기 전에 `StackSnapshotCallback` 스택에서 각 관리 되는 프레임 (또는 관리 되지 않는 프레임의 실행)에 대해 한 번씩 여러 번 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-125">Before the CLR returns from that call, it calls your `StackSnapshotCallback` several times, once for each managed frame (or run of unmanaged frames) on the stack.</span></span> <span data-ttu-id="fc21d-126">관리 되지 않는 프레임이 발견 되 면 직접 탐색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-126">When unmanaged frames are encountered, you must walk them yourself.</span></span>  
  
 <span data-ttu-id="fc21d-127">스택이 푸시되는 순서는 프레임을 스택에 푸시하는 방법입니다. 리프 (마지막 푸시) 프레임 먼저, 주 (첫 번째 푸시) 프레임이 마지막입니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-127">The order in which the stack is walked is the reverse of how the frames were pushed onto the stack: leaf (last-pushed) frame first, main (first-pushed) frame last.</span></span>  
  
 <span data-ttu-id="fc21d-128">관리 되는 스택을 탐색 하기 위해 프로파일러를 프로그래밍 하는 방법에 대 한 자세한 내용은 [.NET Framework 2.0: 기본 사항 및 그 이상에서 프로파일러 스택 탐색](/previous-versions/dotnet/articles/bb264782(v=msdn.10))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fc21d-128">For more information about how to program the profiler to walk managed stacks, see [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](/previous-versions/dotnet/articles/bb264782(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="fc21d-129">다음 섹션에서 설명 하는 것 처럼 스택 워크는 동기식 또는 비동기식 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-129">A stack walk can be synchronous or asynchronous, as explained in the following sections.</span></span>  
  
## <a name="synchronous-stack-walk"></a><span data-ttu-id="fc21d-130">동기 스택 워크</span><span class="sxs-lookup"><span data-stu-id="fc21d-130">Synchronous Stack Walk</span></span>  

 <span data-ttu-id="fc21d-131">동기 스택 워크에는 콜백에 대 한 응답으로 현재 스레드의 스택을 탐색 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-131">A synchronous stack walk involves walking the stack of the current thread in response to a callback.</span></span> <span data-ttu-id="fc21d-132">시드 또는 일시 중단은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-132">It does not require seeding or suspending.</span></span>  
  
 <span data-ttu-id="fc21d-133">프로파일러가 프로파일러 [ICorProfilerCallback](icorprofilercallback-interface.md) (또는 [ICorProfilerCallback2](icorprofilercallback2-interface.md)) 메서드 중 하나를 호출 하는 경우를 호출 `DoStackSnapshot` 하 여 현재 스레드의 스택을 탐색 하는 경우 동기식 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-133">You make a synchronous call when, in response to the CLR calling one of your profiler's [ICorProfilerCallback](icorprofilercallback-interface.md) (or [ICorProfilerCallback2](icorprofilercallback2-interface.md)) methods, you call `DoStackSnapshot` to walk the stack of the current thread.</span></span> <span data-ttu-id="fc21d-134">이는 [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md)된 것과 같은 알림에서 스택이 어떻게 표시 되는지 확인 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-134">This is useful when you want to see what the stack looks like at a notification such as [ICorProfilerCallback::ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span></span> <span data-ttu-id="fc21d-135">메서드 내에서를 호출 하 여 `DoStackSnapshot` `ICorProfilerCallback` 및 매개 변수에 null을 전달 하기만 하면 `context` `thread` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-135">You just call `DoStackSnapshot` from within your `ICorProfilerCallback` method, passing null in the `context` and `thread` parameters.</span></span>  
  
## <a name="asynchronous-stack-walk"></a><span data-ttu-id="fc21d-136">비동기 스택 워크</span><span class="sxs-lookup"><span data-stu-id="fc21d-136">Asynchronous Stack Walk</span></span>  

 <span data-ttu-id="fc21d-137">비동기 스택 워크는 다른 스레드의 스택을 탐색 하거나 콜백에 대 한 응답으로는 아니지만 현재 스레드의 명령 포인터를 하이재킹 하 여 현재 스레드의 스택을 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-137">An asynchronous stack walk entails walking the stack of a different thread, or walking the stack of the current thread, not in response to a callback, but by hijacking the current thread's instruction pointer.</span></span> <span data-ttu-id="fc21d-138">스택의 맨 위에는 플랫폼 호출 (PInvoke) 또는 COM 호출의 일부가 아니지만 CLR 자체의 도우미 코드는 관리 되지 않는 코드를 사용 하는 경우 비동기 워크에 시드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-138">An asynchronous walk requires a seed if the top of the stack is unmanaged code that is not part of a platform invoke (PInvoke) or COM call, but helper code in the CLR itself.</span></span> <span data-ttu-id="fc21d-139">예를 들어 JIT (just-in-time) 컴파일 또는 가비지 수집을 수행 하는 코드는 도우미 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-139">For example, code that does just-in-time (JIT) compiling or garbage collection is helper code.</span></span>  
  
 <span data-ttu-id="fc21d-140">관리 되는 최상위 프레임을 찾을 때까지 대상 스레드를 직접 일시 중단 하 고 해당 스택을 직접 탐색 하 여 초기값을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-140">You obtain a seed by directly suspending the target thread and walking its stack yourself, until you find the topmost managed frame.</span></span> <span data-ttu-id="fc21d-141">대상 스레드를 일시 중단 한 후 대상 스레드의 현재 등록 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-141">After the target thread is suspended, get the target thread's current register context.</span></span> <span data-ttu-id="fc21d-142">그런 다음 [ICorProfilerInfo:: GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md) 를 호출 하 여 등록 컨텍스트가 비관리 코드를 가리키는지 여부를 확인 합니다 .이 값이 0을 반환 하면 `FunctionID` 프레임은 비관리 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-142">Next, determine whether the register context points to unmanaged code by calling [ICorProfilerInfo::GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md) — if it returns a `FunctionID` equal to zero, the frame is unmanaged code.</span></span> <span data-ttu-id="fc21d-143">이제 첫 번째 관리 되는 프레임에 도달할 때까지 스택을 탐색 한 다음 해당 프레임에 대 한 등록 컨텍스트를 기준으로 초기값 컨텍스트를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-143">Now, walk the stack until you reach the first managed frame, and then calculate the seed context based on the register context for that frame.</span></span>  
  
 <span data-ttu-id="fc21d-144">`DoStackSnapshot`초기값 컨텍스트를 사용 하 여를 호출 하 여 비동기 스택 워크를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-144">Call `DoStackSnapshot` with your seed context to begin the asynchronous stack walk.</span></span> <span data-ttu-id="fc21d-145">초기값을 제공 하지 않으면에서 `DoStackSnapshot` 스택 맨 위에 있는 관리 되는 프레임을 건너뛸 수 있으며, 따라서 완료 되지 않은 스택 워크가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-145">If you do not supply a seed, `DoStackSnapshot` might skip managed frames at the top of the stack and, consequently, will give you an incomplete stack walk.</span></span> <span data-ttu-id="fc21d-146">초기값을 제공 하는 경우 JIT 컴파일 또는 네이티브 이미지 생성기 (Ngen.exe) 생성 코드를 가리켜야 합니다. 그렇지 않으면 `DoStackSnapshot` CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-146">If you do supply a seed, it must point to JIT-compiled or Native Image Generator (Ngen.exe)-generated code; otherwise, `DoStackSnapshot` returns the failure code, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span></span>  
  
 <span data-ttu-id="fc21d-147">비동기 스택 워크는 이러한 지침을 따르지 않는 한 교착 상태 또는 액세스 위반을 쉽게 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-147">Asynchronous stack walks can easily cause deadlocks or access violations, unless you follow these guidelines:</span></span>  
  
- <span data-ttu-id="fc21d-148">스레드를 직접 일시 중단 하는 경우 관리 코드를 실행 하지 않는 스레드만 다른 스레드를 일시 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-148">When you directly suspend threads, remember that only a thread that has never run managed code can suspend another thread.</span></span>  
  
- <span data-ttu-id="fc21d-149">스레드의 스택 워크가 완료 될 때까지 [ICorProfilerCallback:: ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md) 된 콜백이 항상 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-149">Always block in your [ICorProfilerCallback::ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md) callback until that thread's stack walk is complete.</span></span>  
  
- <span data-ttu-id="fc21d-150">프로파일러가 가비지 수집을 트리거할 수 있는 CLR 함수를 호출 하는 동안에는 잠금을 보유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-150">Do not hold a lock while your profiler calls into a CLR function that can trigger a garbage collection.</span></span> <span data-ttu-id="fc21d-151">즉, 소유 하는 스레드에서 가비지 수집을 트리거하는 호출을 수행할 수 있는 경우 잠금을 보유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-151">That is, do not hold a lock if the owning thread might make a call that triggers a garbage collection.</span></span>  
  
 <span data-ttu-id="fc21d-152">프로파일러에서 만든 스레드에서를 호출 하 여 `DoStackSnapshot` 별도의 대상 스레드의 스택을 탐색할 수 있는 경우 교착 상태가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-152">There is also a risk of deadlock if you call `DoStackSnapshot` from a thread that your profiler has created so that you can walk the stack of a separate target thread.</span></span> <span data-ttu-id="fc21d-153">만든 스레드가 특정 메서드 (를 포함 하 여)에 처음으로 들어가면 `ICorProfilerInfo*` `DoStackSnapshot` clr은 해당 스레드에서 스레드별, clr 관련 초기화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-153">The first time the thread you created enters certain `ICorProfilerInfo*` methods (including `DoStackSnapshot`), the CLR will perform per-thread, CLR-specific initialization on that thread.</span></span> <span data-ttu-id="fc21d-154">프로파일러가 실행 하려는 스택 대상 스레드를 일시 중단 하 고 해당 대상 스레드가이 스레드 단위 초기화를 수행 하는 데 필요한 잠금을 소유 하 고 있는 경우 교착 상태가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-154">If your profiler has suspended the target thread whose stack you are trying to walk, and if that target thread happened to own a lock necessary for performing this per-thread initialization, a deadlock will occur.</span></span> <span data-ttu-id="fc21d-155">이 교착 상태를 방지 하려면 프로파일러에서 만든 스레드에서에 대 한 초기 호출을 수행 `DoStackSnapshot` 하 여 별도의 대상 스레드를 탐색 하 고 대상 스레드를 먼저 일시 중단 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="fc21d-155">To avoid this deadlock, make an initial call into `DoStackSnapshot` from your profiler-created thread to walk a separate target thread, but do not suspend the target thread first.</span></span> <span data-ttu-id="fc21d-156">이 초기 호출을 통해 스레드 단위 초기화가 교착 상태 없이 완료 될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-156">This initial call ensures that the per-thread initialization can complete without deadlock.</span></span> <span data-ttu-id="fc21d-157">`DoStackSnapshot`가 성공 하 고 하나 이상의 프레임을 보고 하는 경우 해당 시점 이후에 프로파일러에서 만든 스레드가 대상 스레드를 일시 중단 하 고를 호출 하 여 `DoStackSnapshot` 대상 스레드의 스택을 탐색 하는 것이 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc21d-157">If `DoStackSnapshot` succeeds and reports at least one frame, after that point, it will be safe for that profiler-created thread to suspend any target thread and call `DoStackSnapshot` to walk the stack of that target thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc21d-158">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc21d-158">Requirements</span></span>  

 <span data-ttu-id="fc21d-159">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc21d-159">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc21d-160">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc21d-160">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc21d-161">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc21d-161">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc21d-162">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc21d-162">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc21d-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc21d-163">See also</span></span>

- [<span data-ttu-id="fc21d-164">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc21d-164">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="fc21d-165">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc21d-165">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
