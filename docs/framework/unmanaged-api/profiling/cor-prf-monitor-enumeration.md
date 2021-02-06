---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_MONITOR'
title: COR_PRF_MONITOR 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
ms.openlocfilehash: 5b0bd17713e47e40982e88f33721bf7d6d27fd00
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657792"
---
# <a name="cor_prf_monitor-enumeration"></a><span data-ttu-id="a7ed0-103">COR_PRF_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="a7ed0-103">COR_PRF_MONITOR Enumeration</span></span>

<span data-ttu-id="a7ed0-104">프로파일러가 구독하려는 동작, 기능 또는 이벤트를 지정하는 데 사용되는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-104">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ed0-105">구문</span><span class="sxs-lookup"><span data-stu-id="a7ed0-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="a7ed0-106">구성원</span><span class="sxs-lookup"><span data-stu-id="a7ed0-106">Members</span></span>  

 <span data-ttu-id="a7ed0-107">다음 섹션에서는 `COR_PRF_MONITOR` 범주별로 열거형 멤버를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-107">The following sections list `COR_PRF_MONITOR` enumeration members by category.</span></span> <span data-ttu-id="a7ed0-108">범주는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-108">The categories are:</span></span>  
  
- [<span data-ttu-id="a7ed0-109">플래그가 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="a7ed0-109">No flags set</span></span>](#None)  
  
- [<span data-ttu-id="a7ed0-110">콜백 플래그</span><span class="sxs-lookup"><span data-stu-id="a7ed0-110">Callback flags</span></span>](#Callback)  
  
- [<span data-ttu-id="a7ed0-111">기능 사용 플래그</span><span class="sxs-lookup"><span data-stu-id="a7ed0-111">Feature-enabling flags</span></span>](#Feature)  
  
- [<span data-ttu-id="a7ed0-112">구성 플래그</span><span class="sxs-lookup"><span data-stu-id="a7ed0-112">Configuration flags</span></span>](#Config)  
  
- [<span data-ttu-id="a7ed0-113">복합 플래그</span><span class="sxs-lookup"><span data-stu-id="a7ed0-113">Composite flags</span></span>](#Composite)  
  
<a name="None"></a>

### <a name="no-flags-set"></a><span data-ttu-id="a7ed0-114">플래그 설정 없음</span><span class="sxs-lookup"><span data-stu-id="a7ed0-114">No flags set</span></span>  
  
|<span data-ttu-id="a7ed0-115">멤버</span><span class="sxs-lookup"><span data-stu-id="a7ed0-115">Member</span></span>|<span data-ttu-id="a7ed0-116">설명</span><span class="sxs-lookup"><span data-stu-id="a7ed0-116">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|<span data-ttu-id="a7ed0-117">플래그가 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-117">No flags are set.</span></span>|  
  
<a name="Callback"></a>

### <a name="callback-flags"></a><span data-ttu-id="a7ed0-118">콜백 플래그</span><span class="sxs-lookup"><span data-stu-id="a7ed0-118">Callback flags</span></span>  
  
|<span data-ttu-id="a7ed0-119">멤버</span><span class="sxs-lookup"><span data-stu-id="a7ed0-119">Member</span></span>|<span data-ttu-id="a7ed0-120">설명</span><span class="sxs-lookup"><span data-stu-id="a7ed0-120">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="a7ed0-121">모든 콜백 이벤트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-121">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|<span data-ttu-id="a7ed0-122">`AppDomainCreation*` `AppDomainShutdown*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 및 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-122">Controls the `AppDomainCreation*` and `AppDomainShutdown*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|<span data-ttu-id="a7ed0-123">`AssemblyLoad*` `AssemblyUnload*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 및 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-123">Controls the `AssemblyLoad*` and `AssemblyUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|<span data-ttu-id="a7ed0-124">`JITCachedFunctionSearch*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-124">Controls the `JITCachedFunctionSearch*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span><br /><br /> <span data-ttu-id="a7ed0-125">이 플래그의 동작은 .NET Framework 버전 2.0에서 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-125">The behavior of this flag is changed in the .NET Framework version 2.0.</span></span>|  
|`COR_PRF_MONITOR_CCW`|<span data-ttu-id="a7ed0-126">`COMClassicVTable*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-126">Controls the `COMClassicVTable*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLASS_LOADS`|<span data-ttu-id="a7ed0-127">`ClassLoad*` `ClassUnload*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 및 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-127">Controls the `ClassLoad*` and `ClassUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|<span data-ttu-id="a7ed0-128">`ExceptionCLRCatcher*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-128">Controls the `ExceptionCLRCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|<span data-ttu-id="a7ed0-129">[ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) 및 [managedtounmanagedtransition](icorprofilercallback-managedtounmanagedtransition-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-129">Controls the [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) and [ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface</span></span>|  
|`COR_PRF_MONITOR_ENTERLEAVE`|<span data-ttu-id="a7ed0-130">`FunctionEnter*`, `FunctionLeave*` 및 `FunctionTailCall*` [프로 파일링 전역 정적 함수](profiling-global-static-functions.md)를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-130">Controls the `FunctionEnter*`,  `FunctionLeave*`, and `FunctionTailCall*`[profiling global static functions](profiling-global-static-functions.md).</span></span>|  
|`COR_PRF_MONITOR_EXCEPTIONS`|<span data-ttu-id="a7ed0-131">ICorProfilerCallback 인터페이스에서 [exceptionthrown](icorprofilercallback-exceptionthrown-method.md) 된 콜백과 `ExceptionSearch*` , `ExceptionOSHandler*` , `ExceptionUnwind*` 및 `ExceptionCatcher*` 콜백을 [](icorprofilercallback-interface.md) 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-131">Controls the [ExceptionThrown](icorprofilercallback-exceptionthrown-method.md) callback and the `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, and `ExceptionCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|<span data-ttu-id="a7ed0-132">[ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-132">Controls the [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_GC`|<span data-ttu-id="a7ed0-133">인터페이스에서 [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md),   [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md),  [movedreferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md),  [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md),   [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md),  [rootreferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md),  [handledestroyed](icorprofilercallback2-handledestroyed-method.md)및 [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) 콜백을 제어 합니다 `ICorProfilerCallback*` .</span><span class="sxs-lookup"><span data-stu-id="a7ed0-133">Controls the [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md),   [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md),  [MovedReferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md),  [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md),   [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md),  [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md),  [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md), and [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) callbacks in the `ICorProfilerCallback*` interfaces.</span></span> <span data-ttu-id="a7ed0-134">`COR_PRF_MONITOR_GC`이 할당 되 면 동시 가비지 수집이 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-134">When `COR_PRF_MONITOR_GC` is allocated, concurrent garbage collection is turned off.</span></span>|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|<span data-ttu-id="a7ed0-135">`JITCompilation*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md)및 [JITInlining](icorprofilercallback-jitinlining-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-135">Controls the `JITCompilation*`, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md), and [JITInlining](icorprofilercallback-jitinlining-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_MODULE_LOADS`|<span data-ttu-id="a7ed0-136">`ModuleLoad*` `ModuleUnload*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서, 및 [ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-136">Controls the `ModuleLoad*`,  `ModuleUnload*`, and [ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|<span data-ttu-id="a7ed0-137">[ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스의 [objectallocated](icorprofilercallback-objectallocated-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-137">Controls the [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING`|<span data-ttu-id="a7ed0-138">`Remoting*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-138">Controls the `Remoting*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|<span data-ttu-id="a7ed0-139">`Remoting*` 콜백이 비동기 이벤트를 모니터링하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-139">Controls whether the `Remoting*` callbacks will monitor asynchronous events.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|<span data-ttu-id="a7ed0-140">`Remoting*` 콜백으로 쿠키가 전달되는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-140">Controls whether a cookie is passed to the `Remoting*` callbacks.</span></span>|  
|`COR_PRF_MONITOR_SUSPENDS`|<span data-ttu-id="a7ed0-141">`RuntimeSuspend*` `RuntimeResume*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서,, [runtimethreadsuspended](icorprofilercallback-runtimethreadsuspended-method.md)및 [runtimethreadsuspended](icorprofilercallback-runtimethreadresumed-method.md) 된 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-141">Controls the `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md), and [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_THREADS`|<span data-ttu-id="a7ed0-142">[ICorProfilerCallback](icorprofilercallback-interface.md) 및 [ICorProfilerCallback2](icorprofilercallback2-interface.md) 인터페이스에서 [threadcreated](icorprofilercallback-threadcreated-method.md), [threadcreated](icorprofilercallback-threaddestroyed-method.md)된 [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)및 [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-142">Controls the [ThreadCreated](icorprofilercallback-threadcreated-method.md),  [ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md),  [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md), and [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) and [ICorProfilerCallback2](icorprofilercallback2-interface.md) interfaces.</span></span>|  
  
<a name="Feature"></a>

### <a name="feature-enabling-flags"></a><span data-ttu-id="a7ed0-143">기능 사용 플래그</span><span class="sxs-lookup"><span data-stu-id="a7ed0-143">Feature-enabling flags</span></span>  
  
|<span data-ttu-id="a7ed0-144">멤버</span><span class="sxs-lookup"><span data-stu-id="a7ed0-144">Member</span></span>|<span data-ttu-id="a7ed0-145">설명</span><span class="sxs-lookup"><span data-stu-id="a7ed0-145">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|<span data-ttu-id="a7ed0-146">`ClassID`FunctionEnter2 콜백에서 반환 된 값으로 [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) 메서드를 호출 하 여 제네릭 함수에 대해 정확한를 검색할 수 있도록 합니다 `COR_PRF_FRAME_INFO` . [](functionenter2-function.md)</span><span class="sxs-lookup"><span data-stu-id="a7ed0-146">Enables the retrieval of an exact `ClassID` for a generic function by calling the [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method with a `COR_PRF_FRAME_INFO` value returned by the [FunctionEnter2](functionenter2-function.md) callback.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|<span data-ttu-id="a7ed0-147">[FunctionEnter2](functionenter2-function.md) Callback 또는 [FunctionEnter3WithInfo](functionenter3withinfo-function.md) callback 및 [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) 메서드를 사용 하 여 인수 추적을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-147">Enables argument tracing using the [FunctionEnter2](functionenter2-function.md) callback or the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) callback and the [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|<span data-ttu-id="a7ed0-148">[FunctionLeave2](functionleave2-function.md) Callback 또는 [FunctionLeave3WithInfo](functionleave3withinfo-function.md) callback 및 [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) 메서드를 사용 하 여 반환 값을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-148">Enables tracing of return values by using the [FunctionLeave2](functionleave2-function.md) callback or the [FunctionLeave3WithInfo](functionleave3withinfo-function.md) callback and [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|<span data-ttu-id="a7ed0-149">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-149">Deprecated.</span></span><br /><br /> <span data-ttu-id="a7ed0-150">프로세스 내 디버깅은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-150">In process debugging is not supported.</span></span> <span data-ttu-id="a7ed0-151">이 플래그는 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-151">This flag has no effect.</span></span>|  
|`COR_PRF_ENABLE_JIT_MAPS`|<span data-ttu-id="a7ed0-152">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-152">Deprecated.</span></span><br /><br /> <span data-ttu-id="a7ed0-153">프로파일러가 [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md)를 사용 하 여 IL-네이티브 맵을 가져올 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-153">Allows the profiler to obtain IL-to-native maps by using [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md).</span></span> <span data-ttu-id="a7ed0-154">.NET Framework 2.0부터는 런타임이 항상 IL-네이티브 맵을 추적하므로 이 플래그는 항상 설정되어 있는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-154">Starting with the .NET Framework 2.0, the runtime always tracks IL-to-native maps; therefore, this flag is always considered to be set.</span></span>|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|<span data-ttu-id="a7ed0-155">프로파일러가 개체 할당 알림을 받고자 할 수 있음을 런타임에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-155">Informs the runtime that the profiler may want object allocation notifications.</span></span> <span data-ttu-id="a7ed0-156">이 플래그는 초기화 중에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-156">This flag must be set during initialization.</span></span> <span data-ttu-id="a7ed0-157">이를 통해 프로파일러는 나중에 플래그를 사용 하 여 `COR_PRF_MONITOR_OBJECT_ALLOCATED` [objectallocated](icorprofilercallback-objectallocated-method.md) 된 콜백을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-157">It allows the profiler to subsequently use the `COR_PRF_MONITOR_OBJECT_ALLOCATED` flag to receive [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callbacks.</span></span>|  
|`COR_PRF_ENABLE_REJIT`|<span data-ttu-id="a7ed0-158">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) 및 [requestrevert](icorprofilerinfo4-requestrevert-method.md) 메서드를 호출할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-158">Enables calls to the [RequestReJIT](icorprofilerinfo4-requestrejit-method.md) and [RequestRevert](icorprofilerinfo4-requestrevert-method.md) methods.</span></span> <span data-ttu-id="a7ed0-159">프로파일러는 시작 시 이 플래그를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-159">The profiler must set this flag on startup.</span></span>  <span data-ttu-id="a7ed0-160">프로파일러가 이 플래그를 지정하는 경우에는 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-160">If the profiler specifies this flag, it must also specify `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span></span>|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|<span data-ttu-id="a7ed0-161">[DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) 메서드를 호출할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-161">Enables calls to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>|  
  
<a name="Config"></a>

### <a name="configuration-flags"></a><span data-ttu-id="a7ed0-162">구성 플래그</span><span class="sxs-lookup"><span data-stu-id="a7ed0-162">Configuration flags</span></span>  
  
|<span data-ttu-id="a7ed0-163">멤버</span><span class="sxs-lookup"><span data-stu-id="a7ed0-163">Member</span></span>|<span data-ttu-id="a7ed0-164">설명</span><span class="sxs-lookup"><span data-stu-id="a7ed0-164">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|<span data-ttu-id="a7ed0-165">프로파일러 향상 이미지를 비롯한 모든 네이티브 이미지의 로드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-165">Prevents all native images (including profiler-enhanced images) from loading.</span></span>  <span data-ttu-id="a7ed0-166">이 플래그와 `COR_PRF_USE_PROFILE_IMAGES` 플래그가 모두 지정되어 있으면 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-166">If this flag and the `COR_PRF_USE_PROFILE_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
|`COR_PRF_DISABLE_INLINING`|<span data-ttu-id="a7ed0-167">모든 인라인 처리를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-167">Disables all inlining.</span></span>|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|<span data-ttu-id="a7ed0-168">모든 코드 최적화를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-168">Disables all code optimizations.</span></span>|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|<span data-ttu-id="a7ed0-169">일반적으로는 완전 신뢰 어셈블리에 대해 JIT(Just-In-Time) 컴파일 및 클래스 로드 중에 수행되는 보안 투명도 확인을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-169">Disables security transparency checks that are normally done during just-in-time (JIT) compilation and class loading for full-trust assemblies.</span></span> <span data-ttu-id="a7ed0-170">이 경우 일부 계측을 보다 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-170">This can make some instrumentation easier to perform.</span></span>|  
|`COR_PRF_USE_PROFILE_IMAGES`|<span data-ttu-id="a7ed0-171">네이티브 이미지 검색에서 프로파일러 향상 이미지를 찾도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-171">Causes the native image search to look for profiler-enhanced images.</span></span> <span data-ttu-id="a7ed0-172">지정한 어셈블리의 프로파일러 향상 이미지가 없으면 공용 언어 런타임이 해당 어셈블리에 대해 JIT로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-172">If no profiler-enhanced image is found for a given assembly, the common language runtime falls back to JIT for that assembly.</span></span> <span data-ttu-id="a7ed0-173">이 플래그와 `COR_PRF_DISABLE_ALL_NGEN_IMAGES` 플래그가 모두 지정되어 있으면 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-173">If this flag and the `COR_PRF_DISABLE_ALL_NGEN_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
  
<a name="Composite"></a>

### <a name="composite-flags"></a><span data-ttu-id="a7ed0-174">복합 플래그</span><span class="sxs-lookup"><span data-stu-id="a7ed0-174">Composite flags</span></span>  
  
|<span data-ttu-id="a7ed0-175">멤버</span><span class="sxs-lookup"><span data-stu-id="a7ed0-175">Member</span></span>|<span data-ttu-id="a7ed0-176">설명</span><span class="sxs-lookup"><span data-stu-id="a7ed0-176">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ALL`|<span data-ttu-id="a7ed0-177">모든 `COR_PRF_MONITOR` 플래그 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-177">Represents all `COR_PRF_MONITOR` flag values.</span></span>|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="a7ed0-178">실행 중인 앱에 프로파일러를 연결한 후에 설정할 수 있는 모든 `COR_PRF_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-178">Represents all `COR_PRF_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span> <span data-ttu-id="a7ed0-179">구문 섹션에는 이 비트 마스크에 있는 개별 플래그가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-179">The syntax section indicates the individual flags that are present in this bitmask.</span></span>|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="a7ed0-180">모든 콜백 이벤트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-180">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_IMMUTABLE`|<span data-ttu-id="a7ed0-181">초기화 중에만 설정할 수 있는 모든 `COR_PRF_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-181">Represents all `COR_PRF_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="a7ed0-182">초기화 후에 이러한 플래그를 변경하려고 하면 오류를 나타내는 `HRESULT` 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-182">Trying to change any of these flags after initialization returns an `HRESULT` value that indicates failure.</span></span>|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="a7ed0-183">프로필 향상 이미지가 필요한 모든 `COR_PRF_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-183">Represents all `COR_PRF_MONITOR` flags that require profile-enhanced images.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7ed0-184">설명</span><span class="sxs-lookup"><span data-stu-id="a7ed0-184">Remarks</span></span>  

 <span data-ttu-id="a7ed0-185">`COR_PRF_MONITOR`값은 [ICorProfilerInfo:: geteventmask](icorprofilerinfo-geteventmask-method.md) 및 [ICorProfilerInfo:: seteventmask](icorprofilerinfo-seteventmask-method.md) 메서드와 함께 사용 되어 공용 언어 런타임에서 프로파일러에 대해 수행 하는 이벤트 알림을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-185">A `COR_PRF_MONITOR` value is used with the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods to define the event notifications that the common language runtime makes to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7ed0-186">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7ed0-186">Requirements</span></span>  

 <span data-ttu-id="a7ed0-187">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7ed0-187">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7ed0-188">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7ed0-188">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7ed0-189">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7ed0-189">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7ed0-190">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7ed0-190">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ed0-191">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7ed0-191">See also</span></span>

- [<span data-ttu-id="a7ed0-192">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="a7ed0-192">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="a7ed0-193">GetEventMask 메서드</span><span class="sxs-lookup"><span data-stu-id="a7ed0-193">GetEventMask Method</span></span>](icorprofilerinfo-geteventmask-method.md)
- [<span data-ttu-id="a7ed0-194">SetEventMask 메서드</span><span class="sxs-lookup"><span data-stu-id="a7ed0-194">SetEventMask Method</span></span>](icorprofilerinfo-seteventmask-method.md)
