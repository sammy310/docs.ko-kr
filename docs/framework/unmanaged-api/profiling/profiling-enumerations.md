---
title: 프로파일링 열거형
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: bc90743fb348c31bd2f7487c1573ec38a43bd3af
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447453"
---
# <a name="profiling-enumerations"></a><span data-ttu-id="48d0a-102">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-102">Profiling Enumerations</span></span>
<span data-ttu-id="48d0a-103">이 섹션에서는 프로파일링 API에서 사용하는 관리되지 않는 열거형에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-103">This section describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48d0a-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="48d0a-104">In This Section</span></span>  
 [<span data-ttu-id="48d0a-105">COR_PRF_CLAUSE_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-105">COR_PRF_CLAUSE_TYPE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)  
 <span data-ttu-id="48d0a-106">코드에서 방금 시작되거나 끝난 예외 절 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-106">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
 [<span data-ttu-id="48d0a-107">COR_PRF_CODEGEN_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-107">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)  
 <span data-ttu-id="48d0a-108">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="48d0a-108">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
 [<span data-ttu-id="48d0a-109">COR_PRF_FINALIZER_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-109">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md)  
 <span data-ttu-id="48d0a-110">개체에 대한 종료자를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-110">Describes the finalizer for an object.</span></span>  
  
 [<span data-ttu-id="48d0a-111">COR_PRF_GC_GENERATION 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-111">COR_PRF_GC_GENERATION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)  
 <span data-ttu-id="48d0a-112">가비지 수집 생성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-112">Identifies a garbage collection generation.</span></span>  
  
 [<span data-ttu-id="48d0a-113">COR_PRF_GC_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-113">COR_PRF_GC_REASON Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)  
 <span data-ttu-id="48d0a-114">가비지 컬렉션이 수행되는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-114">Indicates the reason that garbage collection is occurring.</span></span>  
  
 [<span data-ttu-id="48d0a-115">COR_PRF_GC_ROOT_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-115">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md)  
 <span data-ttu-id="48d0a-116">가비지 수집기 루트의 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-116">Indicates properties of a garbage collector root.</span></span>  
  
 [<span data-ttu-id="48d0a-117">COR_PRF_GC_ROOT_KIND 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-117">COR_PRF_GC_ROOT_KIND Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md)  
 <span data-ttu-id="48d0a-118">Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="48d0a-118">Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
 [<span data-ttu-id="48d0a-119">COR_PRF_HIGH_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-119">COR_PRF_HIGH_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)  
 <span data-ttu-id="48d0a-120">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span><span class="sxs-lookup"><span data-stu-id="48d0a-120">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
 [<span data-ttu-id="48d0a-121">COR_PRF_JIT_CACHE 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-121">COR_PRF_JIT_CACHE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md)  
 <span data-ttu-id="48d0a-122">캐시된 함수 검색의 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-122">Indicates the result of a cached function search.</span></span>  
  
 [<span data-ttu-id="48d0a-123">COR_PRF_MISC 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-123">COR_PRF_MISC Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-misc-enumeration.md)  
 <span data-ttu-id="48d0a-124">특수 식별자를 지정하는 상수 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-124">Contains constant values that specify special identifiers.</span></span>  
  
 [<span data-ttu-id="48d0a-125">COR_PRF_MODULE_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-125">COR_PRF_MODULE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md)  
 <span data-ttu-id="48d0a-126">모듈의 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-126">Specifies the properties of a module.</span></span>  
  
 [<span data-ttu-id="48d0a-127">COR_PRF_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-127">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 <span data-ttu-id="48d0a-128">프로파일러가 구독하려는 동작, 기능 또는 이벤트를 지정하는 데 사용되는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-128">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
 [<span data-ttu-id="48d0a-129">COR_PRF_RUNTIME_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-129">COR_PRF_RUNTIME_TYPE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-runtime-type-enumeration.md)  
 <span data-ttu-id="48d0a-130">공용 언어 런타임의 버전을 나타내는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-130">Contains values that indicate the version of the common language runtime.</span></span>  
  
 [<span data-ttu-id="48d0a-131">COR_PRF_SNAPSHOT_INFO 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-131">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)  
 <span data-ttu-id="48d0a-132">프로파일러 `StackSnapshotCallback` 함수에 대한 각 호출에서 스택 스냅샷과 함께 다시 전달할 데이터의 양을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-132">Specifies how much data to pass back with a stack snapshot in each call to the profiler's `StackSnapshotCallback` function.</span></span>  
  
 [<span data-ttu-id="48d0a-133">COR_PRF_STATIC_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-133">COR_PRF_STATIC_TYPE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)  
 <span data-ttu-id="48d0a-134">필드가 정적인지 여부와 정적인 경우 필드에 적용될 정적 품질을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-134">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span>  
  
 [<span data-ttu-id="48d0a-135">COR_PRF_SUSPEND_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-135">COR_PRF_SUSPEND_REASON Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)  
 <span data-ttu-id="48d0a-136">런타임이 일시 중단된 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-136">Indicates the reason that the runtime was suspended.</span></span>  
  
 [<span data-ttu-id="48d0a-137">COR_PRF_TRANSITION_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="48d0a-137">COR_PRF_TRANSITION_REASON Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)  
 <span data-ttu-id="48d0a-138">관리 코드에서 비관리 코드로 전환 또는 그 반대의 경우로 전환하는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48d0a-138">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="48d0a-139">관련 단원</span><span class="sxs-lookup"><span data-stu-id="48d0a-139">Related Sections</span></span>  
 [<span data-ttu-id="48d0a-140">프로파일링 개요</span><span class="sxs-lookup"><span data-stu-id="48d0a-140">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="48d0a-141">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48d0a-141">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="48d0a-142">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="48d0a-142">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="48d0a-143">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="48d0a-143">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
