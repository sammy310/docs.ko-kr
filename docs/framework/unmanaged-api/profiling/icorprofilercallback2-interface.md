---
title: ICorProfilerCallback2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2
helpviewer_keywords:
- ICorProfilerCallback2 interface [.NET Framework profiling]
ms.assetid: 4a261dba-450d-4f1f-8d98-865b58bfc992
topic_type:
- apiref
ms.openlocfilehash: 3b0e60602d2f36552c3e0e85ec51205b4128486b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499768"
---
# <a name="icorprofilercallback2-interface"></a><span data-ttu-id="5bf46-102">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bf46-102">ICorProfilerCallback2 Interface</span></span>
<span data-ttu-id="5bf46-103">프로파일러가 구독할 이벤트를 발생 시킬 때 CLR (공용 언어 런타임)에서 코드 프로파일러에 알리는 데 사용 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-103">Provides methods that are used by the common language runtime (CLR) to notify a code profiler when the events to which the profiler has subscribed occur.</span></span> <span data-ttu-id="5bf46-104">`ICorProfilerCallback2`인터페이스는 [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-104">The `ICorProfilerCallback2` interface is an extension of the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span> <span data-ttu-id="5bf46-105">즉, .NET Framework 버전 2.0에 도입 된 새 콜백을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-105">That is, it provides new callbacks introduced in the .NET Framework version 2.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5bf46-106">각 메서드 구현은 성공 시 S_OK 값을 가진 HRESULT를 반환 해야 합니다. 그렇지 않으면 실패 시 E_FAIL.</span><span class="sxs-lookup"><span data-stu-id="5bf46-106">Each method implementation must return an HRESULT having a value of S_OK on success or E_FAIL on failure.</span></span> <span data-ttu-id="5bf46-107">현재 CLR은 [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md)를 제외 하 고 각 콜백에서 반환 되는 HRESULT를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-107">Currently, the CLR ignores the HRESULT that is returned by each callback except [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5bf46-108">메서드</span><span class="sxs-lookup"><span data-stu-id="5bf46-108">Methods</span></span>  
  
|<span data-ttu-id="5bf46-109">방법</span><span class="sxs-lookup"><span data-stu-id="5bf46-109">Method</span></span>|<span data-ttu-id="5bf46-110">설명</span><span class="sxs-lookup"><span data-stu-id="5bf46-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5bf46-111">FinalizeableObjectQueued 메서드</span><span class="sxs-lookup"><span data-stu-id="5bf46-111">FinalizeableObjectQueued Method</span></span>](icorprofilercallback2-finalizeableobjectqueued-method.md)|<span data-ttu-id="5bf46-112">종료자를 사용 하는 개체가 해당 메서드를 실행 하기 위해 종료자 스레드에 대기 되었음을 코드 프로파일러에 알립니다 `Finalize` .</span><span class="sxs-lookup"><span data-stu-id="5bf46-112">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>|  
|[<span data-ttu-id="5bf46-113">GarbageCollectionFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="5bf46-113">GarbageCollectionFinished Method</span></span>](icorprofilercallback2-garbagecollectionfinished-method.md)|<span data-ttu-id="5bf46-114">가비지 수집이 완료 되었으며이에 대해 모든 가비지 수집 콜백이 실행 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-114">Notifies the profiler that a garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>|  
|[<span data-ttu-id="5bf46-115">GarbageCollectionStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="5bf46-115">GarbageCollectionStarted Method</span></span>](icorprofilercallback2-garbagecollectionstarted-method.md)|<span data-ttu-id="5bf46-116">가비지 수집이 시작 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-116">Notifies the code profiler that a garbage collection has started.</span></span>|  
|[<span data-ttu-id="5bf46-117">HandleCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="5bf46-117">HandleCreated Method</span></span>](icorprofilercallback2-handlecreated-method.md)|<span data-ttu-id="5bf46-118">가비지 수집 핸들이 생성 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-118">Notifies the code profiler that a garbage collection handle has been created.</span></span>|  
|[<span data-ttu-id="5bf46-119">HandleDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="5bf46-119">HandleDestroyed Method</span></span>](icorprofilercallback2-handledestroyed-method.md)|<span data-ttu-id="5bf46-120">가비지 수집 핸들이 소멸 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-120">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>|  
|[<span data-ttu-id="5bf46-121">RootReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="5bf46-121">RootReferences2 Method</span></span>](icorprofilercallback2-rootreferences2-method.md)|<span data-ttu-id="5bf46-122">가비지 수집이 발생 한 후 루트 참조에 대해 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-122">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="5bf46-123">이 메서드는 [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) 메서드를 확장 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-123">This method is an extension of the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) method.</span></span>|  
|[<span data-ttu-id="5bf46-124">SurvivingReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="5bf46-124">SurvivingReferences Method</span></span>](icorprofilercallback2-survivingreferences-method.md)|<span data-ttu-id="5bf46-125">가비지 수집에서 남은 개체 참조에 대해 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-125">Notifies the profiler about object references that have survived a garbage collection.</span></span>|  
|[<span data-ttu-id="5bf46-126">ThreadNameChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="5bf46-126">ThreadNameChanged Method</span></span>](icorprofilercallback2-threadnamechanged-method.md)|<span data-ttu-id="5bf46-127">스레드의 이름이 변경 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-127">Notifies the code profiler that the name of a thread has changed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bf46-128">설명</span><span class="sxs-lookup"><span data-stu-id="5bf46-128">Remarks</span></span>  
 <span data-ttu-id="5bf46-129">CLR은 `ICorProfilerCallback` (또는) 인터페이스의 메서드를 호출 `ICorProfilerCallback2` 하 여 프로파일러가 구독 한 이벤트가 발생할 때 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-129">The CLR calls a method in the `ICorProfilerCallback` (or `ICorProfilerCallback2`) interface to notify the profiler when an event, to which the profiler had subscribed, occurs.</span></span> <span data-ttu-id="5bf46-130">이 인터페이스는 CLR이 코드 프로파일러와 통신 하는 데 사용 하는 기본 콜백 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-130">This is the primary callback interface through which the CLR communicates with the code profiler.</span></span>  
  
 <span data-ttu-id="5bf46-131">코드 프로파일러는 인터페이스의 메서드를 구현 해야 합니다 `ICorProfilerCallback` .</span><span class="sxs-lookup"><span data-stu-id="5bf46-131">A code profiler must implement the methods of the `ICorProfilerCallback` interface.</span></span> <span data-ttu-id="5bf46-132">.NET Framework 2.0 이상 버전의 경우 프로파일러는 메서드도 구현 해야 합니다 `ICorProfilerCallback2` .</span><span class="sxs-lookup"><span data-stu-id="5bf46-132">For the .NET Framework 2.0 and later versions, the profiler must also implement the `ICorProfilerCallback2` methods.</span></span> <span data-ttu-id="5bf46-133">각 메서드 구현은 성공 시 S_OK 값을 가진 HRESULT를 반환 해야 합니다. 그렇지 않으면 실패 시 E_FAIL.</span><span class="sxs-lookup"><span data-stu-id="5bf46-133">Each method implementation must return an HRESULT having a value of S_OK on success or E_FAIL on failure.</span></span> <span data-ttu-id="5bf46-134">현재 CLR은 [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md)를 제외 하 고 각 콜백에서 반환 되는 HRESULT를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-134">Currently, the CLR ignores the HRESULT that is returned by each callback except [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md).</span></span>  
  
 <span data-ttu-id="5bf46-135">코드 프로파일러는 및 인터페이스를 구현 하는 COM 개체, Microsoft Windows 레지스트리에 등록 해야 `ICorProfilerCallback` 합니다 `ICorProfilerCallback2` .</span><span class="sxs-lookup"><span data-stu-id="5bf46-135">A code profiler must register in the Microsoft Windows registry, its COM object that implements the `ICorProfilerCallback` and `ICorProfilerCallback2` interfaces.</span></span> <span data-ttu-id="5bf46-136">코드 프로파일러는 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)를 호출 하 여 알림을 수신 하려는 이벤트를 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-136">A code profiler subscribes to the events for which it wants to receive notification by calling [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="5bf46-137">이는 일반적으로 프로파일러의 [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)구현에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-137">This is usually done in the profiler's implementation of [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md).</span></span> <span data-ttu-id="5bf46-138">그러면 프로파일러가 실행 중인 런타임 프로세스에서 발생 하거나 이벤트를 발생 시킬 때 런타임에서 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-138">The profiler is then able to receive notification from the runtime when an event is about to occur or has just occurred in an executing runtime process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5bf46-139">프로파일러는 단일 COM 개체를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-139">The profiler registers a single COM object.</span></span> <span data-ttu-id="5bf46-140">프로파일러가 .NET Framework 버전 1.0 또는 1.1를 대상으로 하는 경우 해당 COM 개체는의 메서드만 구현 하면 `ICorProfilerCallback` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bf46-140">If the profiler is targeting .NET Framework version 1.0 or 1.1, that COM object need only implement the methods of `ICorProfilerCallback`.</span></span> <span data-ttu-id="5bf46-141">.NET Framework 버전 2.0 이상을 대상으로 하는 경우에는 COM 개체도의 메서드를 구현 해야 합니다 `ICorProfilerCallback2` .</span><span class="sxs-lookup"><span data-stu-id="5bf46-141">If it is targeting .NET Framework version 2.0 and later, the COM object must also implement the methods of `ICorProfilerCallback2`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bf46-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bf46-142">Requirements</span></span>  
 <span data-ttu-id="5bf46-143">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bf46-143">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bf46-144">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5bf46-144">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5bf46-145">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bf46-145">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bf46-146">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bf46-146">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf46-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bf46-147">See also</span></span>

- [<span data-ttu-id="5bf46-148">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bf46-148">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="5bf46-149">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bf46-149">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5bf46-150">ICorProfilerCallback3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bf46-150">ICorProfilerCallback3 Interface</span></span>](icorprofilercallback3-interface.md)
- [<span data-ttu-id="5bf46-151">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bf46-151">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
