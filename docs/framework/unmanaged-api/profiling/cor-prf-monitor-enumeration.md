---
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
ms.openlocfilehash: 1ff167121a5bb752c70edd2c5901133503326bea
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500808"
---
# <a name="cor_prf_monitor-enumeration"></a><span data-ttu-id="685e2-102">COR_PRF_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="685e2-102">COR_PRF_MONITOR Enumeration</span></span>
<span data-ttu-id="685e2-103">프로파일러가 구독하려는 동작, 기능 또는 이벤트를 지정하는 데 사용되는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-103">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="685e2-104">구문</span><span class="sxs-lookup"><span data-stu-id="685e2-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="685e2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="685e2-105">Members</span></span>  
 <span data-ttu-id="685e2-106">다음 섹션에서는 `COR_PRF_MONITOR` 범주별로 열거형 멤버를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-106">The following sections list `COR_PRF_MONITOR` enumeration members by category.</span></span> <span data-ttu-id="685e2-107">범주는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-107">The categories are:</span></span>  
  
- [<span data-ttu-id="685e2-108">플래그가 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="685e2-108">No flags set</span></span>](#None)  
  
- [<span data-ttu-id="685e2-109">콜백 플래그</span><span class="sxs-lookup"><span data-stu-id="685e2-109">Callback flags</span></span>](#Callback)  
  
- [<span data-ttu-id="685e2-110">기능 사용 플래그</span><span class="sxs-lookup"><span data-stu-id="685e2-110">Feature-enabling flags</span></span>](#Feature)  
  
- [<span data-ttu-id="685e2-111">구성 플래그</span><span class="sxs-lookup"><span data-stu-id="685e2-111">Configuration flags</span></span>](#Config)  
  
- [<span data-ttu-id="685e2-112">복합 플래그</span><span class="sxs-lookup"><span data-stu-id="685e2-112">Composite flags</span></span>](#Composite)  
  
<a name="None"></a>
### <a name="no-flags-set"></a><span data-ttu-id="685e2-113">플래그 설정 없음</span><span class="sxs-lookup"><span data-stu-id="685e2-113">No flags set</span></span>  
  
|<span data-ttu-id="685e2-114">멤버</span><span class="sxs-lookup"><span data-stu-id="685e2-114">Member</span></span>|<span data-ttu-id="685e2-115">설명</span><span class="sxs-lookup"><span data-stu-id="685e2-115">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|<span data-ttu-id="685e2-116">플래그가 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-116">No flags are set.</span></span>|  
  
<a name="Callback"></a>
### <a name="callback-flags"></a><span data-ttu-id="685e2-117">콜백 플래그</span><span class="sxs-lookup"><span data-stu-id="685e2-117">Callback flags</span></span>  
  
|<span data-ttu-id="685e2-118">멤버</span><span class="sxs-lookup"><span data-stu-id="685e2-118">Member</span></span>|<span data-ttu-id="685e2-119">설명</span><span class="sxs-lookup"><span data-stu-id="685e2-119">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="685e2-120">모든 콜백 이벤트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-120">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|<span data-ttu-id="685e2-121">`AppDomainCreation*` `AppDomainShutdown*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 및 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-121">Controls the `AppDomainCreation*` and `AppDomainShutdown*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|<span data-ttu-id="685e2-122">`AssemblyLoad*` `AssemblyUnload*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 및 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-122">Controls the `AssemblyLoad*` and `AssemblyUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|<span data-ttu-id="685e2-123">`JITCachedFunctionSearch*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-123">Controls the `JITCachedFunctionSearch*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span><br /><br /> <span data-ttu-id="685e2-124">이 플래그의 동작은 .NET Framework 버전 2.0에서 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-124">The behavior of this flag is changed in the .NET Framework version 2.0.</span></span>|  
|`COR_PRF_MONITOR_CCW`|<span data-ttu-id="685e2-125">`COMClassicVTable*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-125">Controls the `COMClassicVTable*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLASS_LOADS`|<span data-ttu-id="685e2-126">`ClassLoad*` `ClassUnload*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 및 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-126">Controls the `ClassLoad*` and `ClassUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|<span data-ttu-id="685e2-127">`ExceptionCLRCatcher*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-127">Controls the `ExceptionCLRCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|<span data-ttu-id="685e2-128">[ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) 및 [managedtounmanagedtransition](icorprofilercallback-managedtounmanagedtransition-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-128">Controls the [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) and [ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface</span></span>|  
|`COR_PRF_MONITOR_ENTERLEAVE`|<span data-ttu-id="685e2-129">`FunctionEnter*`, `FunctionLeave*` 및 `FunctionTailCall*` [프로 파일링 전역 정적 함수](profiling-global-static-functions.md)를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-129">Controls the `FunctionEnter*`,  `FunctionLeave*`, and `FunctionTailCall*`[profiling global static functions](profiling-global-static-functions.md).</span></span>|  
|`COR_PRF_MONITOR_EXCEPTIONS`|<span data-ttu-id="685e2-130">ICorProfilerCallback 인터페이스에서 [exceptionthrown](icorprofilercallback-exceptionthrown-method.md) 된 콜백과 `ExceptionSearch*` , `ExceptionOSHandler*` , `ExceptionUnwind*` 및 `ExceptionCatcher*` 콜백을 [ICorProfilerCallback](icorprofilercallback-interface.md) 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-130">Controls the [ExceptionThrown](icorprofilercallback-exceptionthrown-method.md) callback and the `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, and `ExceptionCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|<span data-ttu-id="685e2-131">[ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-131">Controls the [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_GC`|<span data-ttu-id="685e2-132">인터페이스에서 [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), [movedreferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md), [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md), [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md), [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md), [rootreferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md), [handledestroyed](icorprofilercallback2-handledestroyed-method.md)및 [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) 콜백을 제어 합니다 `ICorProfilerCallback*` .</span><span class="sxs-lookup"><span data-stu-id="685e2-132">Controls the [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md),   [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md),  [MovedReferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md),  [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md),   [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md),  [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md),  [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md), and [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) callbacks in the `ICorProfilerCallback*` interfaces.</span></span> <span data-ttu-id="685e2-133">`COR_PRF_MONITOR_GC`이 할당 되 면 동시 가비지 수집이 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-133">When `COR_PRF_MONITOR_GC` is allocated, concurrent garbage collection is turned off.</span></span>|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|<span data-ttu-id="685e2-134">`JITCompilation*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md)및 [JITInlining](icorprofilercallback-jitinlining-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-134">Controls the `JITCompilation*`, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md), and [JITInlining](icorprofilercallback-jitinlining-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_MODULE_LOADS`|<span data-ttu-id="685e2-135">`ModuleLoad*` `ModuleUnload*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서, 및 [ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-135">Controls the `ModuleLoad*`,  `ModuleUnload*`, and [ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|<span data-ttu-id="685e2-136">[ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스의 [objectallocated](icorprofilercallback-objectallocated-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-136">Controls the [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING`|<span data-ttu-id="685e2-137">`Remoting*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-137">Controls the `Remoting*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|<span data-ttu-id="685e2-138">`Remoting*` 콜백이 비동기 이벤트를 모니터링하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-138">Controls whether the `Remoting*` callbacks will monitor asynchronous events.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|<span data-ttu-id="685e2-139">`Remoting*` 콜백으로 쿠키가 전달되는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-139">Controls whether a cookie is passed to the `Remoting*` callbacks.</span></span>|  
|`COR_PRF_MONITOR_SUSPENDS`|<span data-ttu-id="685e2-140">`RuntimeSuspend*` `RuntimeResume*` [ICorProfilerCallback](icorprofilercallback-interface.md) 인터페이스에서,, [runtimethreadsuspended](icorprofilercallback-runtimethreadsuspended-method.md)및 [runtimethreadsuspended](icorprofilercallback-runtimethreadresumed-method.md) 된 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-140">Controls the `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md), and [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_THREADS`|<span data-ttu-id="685e2-141">[ICorProfilerCallback](icorprofilercallback-interface.md) 및 [ICorProfilerCallback2](icorprofilercallback2-interface.md) 인터페이스에서 [threadcreated](icorprofilercallback-threadcreated-method.md), [threadcreated](icorprofilercallback-threaddestroyed-method.md)된 [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)및 [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-141">Controls the [ThreadCreated](icorprofilercallback-threadcreated-method.md),  [ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md),  [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md), and [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) and [ICorProfilerCallback2](icorprofilercallback2-interface.md) interfaces.</span></span>|  
  
<a name="Feature"></a>
### <a name="feature-enabling-flags"></a><span data-ttu-id="685e2-142">기능 사용 플래그</span><span class="sxs-lookup"><span data-stu-id="685e2-142">Feature-enabling flags</span></span>  
  
|<span data-ttu-id="685e2-143">멤버</span><span class="sxs-lookup"><span data-stu-id="685e2-143">Member</span></span>|<span data-ttu-id="685e2-144">설명</span><span class="sxs-lookup"><span data-stu-id="685e2-144">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|<span data-ttu-id="685e2-145">`ClassID`FunctionEnter2 콜백에서 반환 된 값으로 [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) 메서드를 호출 하 여 제네릭 함수에 대해 정확한를 검색할 수 있도록 합니다 `COR_PRF_FRAME_INFO` . [FunctionEnter2](functionenter2-function.md)</span><span class="sxs-lookup"><span data-stu-id="685e2-145">Enables the retrieval of an exact `ClassID` for a generic function by calling the [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method with a `COR_PRF_FRAME_INFO` value returned by the [FunctionEnter2](functionenter2-function.md) callback.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|<span data-ttu-id="685e2-146">[FunctionEnter2](functionenter2-function.md) Callback 또는 [FunctionEnter3WithInfo](functionenter3withinfo-function.md) callback 및 [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) 메서드를 사용 하 여 인수 추적을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-146">Enables argument tracing using the [FunctionEnter2](functionenter2-function.md) callback or the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) callback and the [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|<span data-ttu-id="685e2-147">[FunctionLeave2](functionleave2-function.md) Callback 또는 [FunctionLeave3WithInfo](functionleave3withinfo-function.md) callback 및 [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) 메서드를 사용 하 여 반환 값을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-147">Enables tracing of return values by using the [FunctionLeave2](functionleave2-function.md) callback or the [FunctionLeave3WithInfo](functionleave3withinfo-function.md) callback and [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|<span data-ttu-id="685e2-148">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-148">Deprecated.</span></span><br /><br /> <span data-ttu-id="685e2-149">프로세스 내 디버깅은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-149">In process debugging is not supported.</span></span> <span data-ttu-id="685e2-150">이 플래그는 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-150">This flag has no effect.</span></span>|  
|`COR_PRF_ENABLE_JIT_MAPS`|<span data-ttu-id="685e2-151">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-151">Deprecated.</span></span><br /><br /> <span data-ttu-id="685e2-152">프로파일러가 [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md)를 사용 하 여 IL-네이티브 맵을 가져올 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-152">Allows the profiler to obtain IL-to-native maps by using [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md).</span></span> <span data-ttu-id="685e2-153">.NET Framework 2.0부터는 런타임이 항상 IL-네이티브 맵을 추적하므로 이 플래그는 항상 설정되어 있는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-153">Starting with the .NET Framework 2.0, the runtime always tracks IL-to-native maps; therefore, this flag is always considered to be set.</span></span>|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|<span data-ttu-id="685e2-154">프로파일러가 개체 할당 알림을 받고자 할 수 있음을 런타임에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-154">Informs the runtime that the profiler may want object allocation notifications.</span></span> <span data-ttu-id="685e2-155">이 플래그는 초기화 중에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-155">This flag must be set during initialization.</span></span> <span data-ttu-id="685e2-156">이를 통해 프로파일러는 나중에 플래그를 사용 하 여 `COR_PRF_MONITOR_OBJECT_ALLOCATED` [objectallocated](icorprofilercallback-objectallocated-method.md) 된 콜백을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-156">It allows the profiler to subsequently use the `COR_PRF_MONITOR_OBJECT_ALLOCATED` flag to receive [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callbacks.</span></span>|  
|`COR_PRF_ENABLE_REJIT`|<span data-ttu-id="685e2-157">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) 및 [requestrevert](icorprofilerinfo4-requestrevert-method.md) 메서드를 호출할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-157">Enables calls to the [RequestReJIT](icorprofilerinfo4-requestrejit-method.md) and [RequestRevert](icorprofilerinfo4-requestrevert-method.md) methods.</span></span> <span data-ttu-id="685e2-158">프로파일러는 시작 시 이 플래그를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-158">The profiler must set this flag on startup.</span></span>  <span data-ttu-id="685e2-159">프로파일러가 이 플래그를 지정하는 경우에는 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-159">If the profiler specifies this flag, it must also specify `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span></span>|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|<span data-ttu-id="685e2-160">[DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) 메서드를 호출할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-160">Enables calls to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>|  
  
<a name="Config"></a>
### <a name="configuration-flags"></a><span data-ttu-id="685e2-161">구성 플래그</span><span class="sxs-lookup"><span data-stu-id="685e2-161">Configuration flags</span></span>  
  
|<span data-ttu-id="685e2-162">멤버</span><span class="sxs-lookup"><span data-stu-id="685e2-162">Member</span></span>|<span data-ttu-id="685e2-163">설명</span><span class="sxs-lookup"><span data-stu-id="685e2-163">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|<span data-ttu-id="685e2-164">프로파일러 향상 이미지를 비롯한 모든 네이티브 이미지의 로드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-164">Prevents all native images (including profiler-enhanced images) from loading.</span></span>  <span data-ttu-id="685e2-165">이 플래그와 `COR_PRF_USE_PROFILE_IMAGES` 플래그가 모두 지정되어 있으면 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-165">If this flag and the `COR_PRF_USE_PROFILE_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
|`COR_PRF_DISABLE_INLINING`|<span data-ttu-id="685e2-166">모든 인라인 처리를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-166">Disables all inlining.</span></span>|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|<span data-ttu-id="685e2-167">모든 코드 최적화를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-167">Disables all code optimizations.</span></span>|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|<span data-ttu-id="685e2-168">일반적으로는 완전 신뢰 어셈블리에 대해 JIT(Just-In-Time) 컴파일 및 클래스 로드 중에 수행되는 보안 투명도 확인을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-168">Disables security transparency checks that are normally done during just-in-time (JIT) compilation and class loading for full-trust assemblies.</span></span> <span data-ttu-id="685e2-169">이 경우 일부 계측을 보다 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-169">This can make some instrumentation easier to perform.</span></span>|  
|`COR_PRF_USE_PROFILE_IMAGES`|<span data-ttu-id="685e2-170">네이티브 이미지 검색에서 프로파일러 향상 이미지를 찾도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-170">Causes the native image search to look for profiler-enhanced images.</span></span> <span data-ttu-id="685e2-171">지정한 어셈블리의 프로파일러 향상 이미지가 없으면 공용 언어 런타임이 해당 어셈블리에 대해 JIT로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-171">If no profiler-enhanced image is found for a given assembly, the common language runtime falls back to JIT for that assembly.</span></span> <span data-ttu-id="685e2-172">이 플래그와 `COR_PRF_DISABLE_ALL_NGEN_IMAGES` 플래그가 모두 지정되어 있으면 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-172">If this flag and the `COR_PRF_DISABLE_ALL_NGEN_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
  
<a name="Composite"></a>
### <a name="composite-flags"></a><span data-ttu-id="685e2-173">복합 플래그</span><span class="sxs-lookup"><span data-stu-id="685e2-173">Composite flags</span></span>  
  
|<span data-ttu-id="685e2-174">멤버</span><span class="sxs-lookup"><span data-stu-id="685e2-174">Member</span></span>|<span data-ttu-id="685e2-175">설명</span><span class="sxs-lookup"><span data-stu-id="685e2-175">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ALL`|<span data-ttu-id="685e2-176">모든 `COR_PRF_MONITOR` 플래그 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-176">Represents all `COR_PRF_MONITOR` flag values.</span></span>|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="685e2-177">실행 중인 앱에 프로파일러를 연결한 후에 설정할 수 있는 모든 `COR_PRF_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-177">Represents all `COR_PRF_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span> <span data-ttu-id="685e2-178">구문 섹션에는 이 비트 마스크에 있는 개별 플래그가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-178">The syntax section indicates the individual flags that are present in this bitmask.</span></span>|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="685e2-179">모든 콜백 이벤트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-179">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_IMMUTABLE`|<span data-ttu-id="685e2-180">초기화 중에만 설정할 수 있는 모든 `COR_PRF_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-180">Represents all `COR_PRF_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="685e2-181">초기화 후에 이러한 플래그를 변경하려고 하면 오류를 나타내는 `HRESULT` 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-181">Trying to change any of these flags after initialization returns an `HRESULT` value that indicates failure.</span></span>|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="685e2-182">프로필 향상 이미지가 필요한 모든 `COR_PRF_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-182">Represents all `COR_PRF_MONITOR` flags that require profile-enhanced images.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="685e2-183">설명</span><span class="sxs-lookup"><span data-stu-id="685e2-183">Remarks</span></span>  
 <span data-ttu-id="685e2-184">`COR_PRF_MONITOR`값은 [ICorProfilerInfo:: geteventmask](icorprofilerinfo-geteventmask-method.md) 및 [ICorProfilerInfo:: seteventmask](icorprofilerinfo-seteventmask-method.md) 메서드와 함께 사용 되어 공용 언어 런타임에서 프로파일러에 대해 수행 하는 이벤트 알림을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="685e2-184">A `COR_PRF_MONITOR` value is used with the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods to define the event notifications that the common language runtime makes to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="685e2-185">요구 사항</span><span class="sxs-lookup"><span data-stu-id="685e2-185">Requirements</span></span>  
 <span data-ttu-id="685e2-186">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="685e2-186">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="685e2-187">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="685e2-187">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="685e2-188">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="685e2-188">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="685e2-189">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="685e2-189">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685e2-190">참고 항목</span><span class="sxs-lookup"><span data-stu-id="685e2-190">See also</span></span>

- [<span data-ttu-id="685e2-191">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="685e2-191">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="685e2-192">GetEventMask 메서드</span><span class="sxs-lookup"><span data-stu-id="685e2-192">GetEventMask Method</span></span>](icorprofilerinfo-geteventmask-method.md)
- [<span data-ttu-id="685e2-193">SetEventMask 메서드</span><span class="sxs-lookup"><span data-stu-id="685e2-193">SetEventMask Method</span></span>](icorprofilerinfo-seteventmask-method.md)
