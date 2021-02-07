---
description: '자세히 알아보기: ICorProfilerCallback2 인터페이스'
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
ms.openlocfilehash: b6a6fa62d8d1b119ce1a52b06cb562c6da32b1a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705527"
---
# <a name="icorprofilercallback2-interface"></a><span data-ttu-id="d7a9f-103">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7a9f-103">ICorProfilerCallback2 Interface</span></span>

<span data-ttu-id="d7a9f-104">프로파일러가 구독할 이벤트를 발생 시킬 때 CLR (공용 언어 런타임)에서 코드 프로파일러에 알리는 데 사용 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-104">Provides methods that are used by the common language runtime (CLR) to notify a code profiler when the events to which the profiler has subscribed occur.</span></span> <span data-ttu-id="d7a9f-105">`ICorProfilerCallback2`인터페이스는 [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-105">The `ICorProfilerCallback2` interface is an extension of the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span> <span data-ttu-id="d7a9f-106">즉, .NET Framework 버전 2.0에 도입 된 새 콜백을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-106">That is, it provides new callbacks introduced in the .NET Framework version 2.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7a9f-107">각 메서드 구현은 성공 시 S_OK 값을 가진 HRESULT를 반환 해야 합니다. 그렇지 않으면 실패 시 E_FAIL.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-107">Each method implementation must return an HRESULT having a value of S_OK on success or E_FAIL on failure.</span></span> <span data-ttu-id="d7a9f-108">현재 CLR은 [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md)를 제외 하 고 각 콜백에서 반환 되는 HRESULT를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-108">Currently, the CLR ignores the HRESULT that is returned by each callback except [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7a9f-109">메서드</span><span class="sxs-lookup"><span data-stu-id="d7a9f-109">Methods</span></span>  
  
|<span data-ttu-id="d7a9f-110">메서드</span><span class="sxs-lookup"><span data-stu-id="d7a9f-110">Method</span></span>|<span data-ttu-id="d7a9f-111">설명</span><span class="sxs-lookup"><span data-stu-id="d7a9f-111">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7a9f-112">FinalizeableObjectQueued 메서드</span><span class="sxs-lookup"><span data-stu-id="d7a9f-112">FinalizeableObjectQueued Method</span></span>](icorprofilercallback2-finalizeableobjectqueued-method.md)|<span data-ttu-id="d7a9f-113">종료자를 사용 하는 개체가 해당 메서드를 실행 하기 위해 종료자 스레드에 대기 되었음을 코드 프로파일러에 알립니다 `Finalize` .</span><span class="sxs-lookup"><span data-stu-id="d7a9f-113">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>|  
|[<span data-ttu-id="d7a9f-114">GarbageCollectionFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="d7a9f-114">GarbageCollectionFinished Method</span></span>](icorprofilercallback2-garbagecollectionfinished-method.md)|<span data-ttu-id="d7a9f-115">가비지 수집이 완료 되었으며이에 대해 모든 가비지 수집 콜백이 실행 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-115">Notifies the profiler that a garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>|  
|[<span data-ttu-id="d7a9f-116">GarbageCollectionStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="d7a9f-116">GarbageCollectionStarted Method</span></span>](icorprofilercallback2-garbagecollectionstarted-method.md)|<span data-ttu-id="d7a9f-117">가비지 수집이 시작 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-117">Notifies the code profiler that a garbage collection has started.</span></span>|  
|[<span data-ttu-id="d7a9f-118">HandleCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="d7a9f-118">HandleCreated Method</span></span>](icorprofilercallback2-handlecreated-method.md)|<span data-ttu-id="d7a9f-119">가비지 수집 핸들이 생성 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-119">Notifies the code profiler that a garbage collection handle has been created.</span></span>|  
|[<span data-ttu-id="d7a9f-120">HandleDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="d7a9f-120">HandleDestroyed Method</span></span>](icorprofilercallback2-handledestroyed-method.md)|<span data-ttu-id="d7a9f-121">가비지 수집 핸들이 소멸 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-121">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>|  
|[<span data-ttu-id="d7a9f-122">RootReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="d7a9f-122">RootReferences2 Method</span></span>](icorprofilercallback2-rootreferences2-method.md)|<span data-ttu-id="d7a9f-123">가비지 수집이 발생 한 후 루트 참조에 대해 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-123">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="d7a9f-124">이 메서드는 [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) 메서드를 확장 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-124">This method is an extension of the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) method.</span></span>|  
|[<span data-ttu-id="d7a9f-125">SurvivingReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="d7a9f-125">SurvivingReferences Method</span></span>](icorprofilercallback2-survivingreferences-method.md)|<span data-ttu-id="d7a9f-126">가비지 수집에서 남은 개체 참조에 대해 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-126">Notifies the profiler about object references that have survived a garbage collection.</span></span>|  
|[<span data-ttu-id="d7a9f-127">ThreadNameChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="d7a9f-127">ThreadNameChanged Method</span></span>](icorprofilercallback2-threadnamechanged-method.md)|<span data-ttu-id="d7a9f-128">스레드의 이름이 변경 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-128">Notifies the code profiler that the name of a thread has changed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7a9f-129">설명</span><span class="sxs-lookup"><span data-stu-id="d7a9f-129">Remarks</span></span>  

 <span data-ttu-id="d7a9f-130">CLR은 `ICorProfilerCallback` (또는) 인터페이스의 메서드를 호출 `ICorProfilerCallback2` 하 여 프로파일러가 구독 한 이벤트가 발생할 때 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-130">The CLR calls a method in the `ICorProfilerCallback` (or `ICorProfilerCallback2`) interface to notify the profiler when an event, to which the profiler had subscribed, occurs.</span></span> <span data-ttu-id="d7a9f-131">이 인터페이스는 CLR이 코드 프로파일러와 통신 하는 데 사용 하는 기본 콜백 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-131">This is the primary callback interface through which the CLR communicates with the code profiler.</span></span>  
  
 <span data-ttu-id="d7a9f-132">코드 프로파일러는 인터페이스의 메서드를 구현 해야 합니다 `ICorProfilerCallback` .</span><span class="sxs-lookup"><span data-stu-id="d7a9f-132">A code profiler must implement the methods of the `ICorProfilerCallback` interface.</span></span> <span data-ttu-id="d7a9f-133">.NET Framework 2.0 이상 버전의 경우 프로파일러는 메서드도 구현 해야 합니다 `ICorProfilerCallback2` .</span><span class="sxs-lookup"><span data-stu-id="d7a9f-133">For the .NET Framework 2.0 and later versions, the profiler must also implement the `ICorProfilerCallback2` methods.</span></span> <span data-ttu-id="d7a9f-134">각 메서드 구현은 성공 시 S_OK 값을 가진 HRESULT를 반환 해야 합니다. 그렇지 않으면 실패 시 E_FAIL.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-134">Each method implementation must return an HRESULT having a value of S_OK on success or E_FAIL on failure.</span></span> <span data-ttu-id="d7a9f-135">현재 CLR은 [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md)를 제외 하 고 각 콜백에서 반환 되는 HRESULT를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-135">Currently, the CLR ignores the HRESULT that is returned by each callback except [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md).</span></span>  
  
 <span data-ttu-id="d7a9f-136">코드 프로파일러는 및 인터페이스를 구현 하는 COM 개체, Microsoft Windows 레지스트리에 등록 해야 `ICorProfilerCallback` 합니다 `ICorProfilerCallback2` .</span><span class="sxs-lookup"><span data-stu-id="d7a9f-136">A code profiler must register in the Microsoft Windows registry, its COM object that implements the `ICorProfilerCallback` and `ICorProfilerCallback2` interfaces.</span></span> <span data-ttu-id="d7a9f-137">코드 프로파일러는 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)를 호출 하 여 알림을 수신 하려는 이벤트를 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-137">A code profiler subscribes to the events for which it wants to receive notification by calling [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="d7a9f-138">이는 일반적으로 프로파일러의 [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)구현에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-138">This is usually done in the profiler's implementation of [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md).</span></span> <span data-ttu-id="d7a9f-139">그러면 프로파일러가 실행 중인 런타임 프로세스에서 발생 하거나 이벤트를 발생 시킬 때 런타임에서 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-139">The profiler is then able to receive notification from the runtime when an event is about to occur or has just occurred in an executing runtime process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7a9f-140">프로파일러는 단일 COM 개체를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-140">The profiler registers a single COM object.</span></span> <span data-ttu-id="d7a9f-141">프로파일러가 .NET Framework 버전 1.0 또는 1.1를 대상으로 하는 경우 해당 COM 개체는의 메서드만 구현 하면 `ICorProfilerCallback` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-141">If the profiler is targeting .NET Framework version 1.0 or 1.1, that COM object need only implement the methods of `ICorProfilerCallback`.</span></span> <span data-ttu-id="d7a9f-142">.NET Framework 버전 2.0 이상을 대상으로 하는 경우에는 COM 개체도의 메서드를 구현 해야 합니다 `ICorProfilerCallback2` .</span><span class="sxs-lookup"><span data-stu-id="d7a9f-142">If it is targeting .NET Framework version 2.0 and later, the COM object must also implement the methods of `ICorProfilerCallback2`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7a9f-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7a9f-143">Requirements</span></span>  

 <span data-ttu-id="d7a9f-144">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7a9f-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7a9f-145">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7a9f-145">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7a9f-146">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7a9f-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7a9f-147">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7a9f-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a9f-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7a9f-148">See also</span></span>

- [<span data-ttu-id="d7a9f-149">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7a9f-149">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d7a9f-150">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7a9f-150">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d7a9f-151">ICorProfilerCallback3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7a9f-151">ICorProfilerCallback3 Interface</span></span>](icorprofilercallback3-interface.md)
- [<span data-ttu-id="d7a9f-152">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7a9f-152">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
