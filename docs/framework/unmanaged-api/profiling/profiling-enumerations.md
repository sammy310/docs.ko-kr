---
description: '자세한 정보: 프로 파일링 열거형'
title: 프로파일링 열거형
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: f202e70dd27654dd39740851549477d4a6bf77a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736754"
---
# <a name="profiling-enumerations"></a><span data-ttu-id="30c03-103">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-103">Profiling Enumerations</span></span>

<span data-ttu-id="30c03-104">이 섹션에서는 프로파일링 API에서 사용하는 관리되지 않는 열거형에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-104">This section describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30c03-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="30c03-105">In This Section</span></span>  

 [<span data-ttu-id="30c03-106">COR_PRF_CLAUSE_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-106">COR_PRF_CLAUSE_TYPE Enumeration</span></span>](cor-prf-clause-type-enumeration.md)  
 <span data-ttu-id="30c03-107">코드에서 방금 시작되거나 끝난 예외 절 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-107">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
 [<span data-ttu-id="30c03-108">COR_PRF_CODEGEN_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-108">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>](cor-prf-codegen-flags-enumeration.md)  
 <span data-ttu-id="30c03-109">[ICorProfilerFunctionControl:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) 메서드를 사용 하 여 설정할 수 있는 코드 생성 플래그를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-109">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
 [<span data-ttu-id="30c03-110">COR_PRF_FINALIZER_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-110">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>](cor-prf-finalizer-flags-enumeration.md)  
 <span data-ttu-id="30c03-111">개체에 대한 종료자를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-111">Describes the finalizer for an object.</span></span>  
  
 [<span data-ttu-id="30c03-112">COR_PRF_GC_GENERATION 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-112">COR_PRF_GC_GENERATION Enumeration</span></span>](cor-prf-gc-generation-enumeration.md)  
 <span data-ttu-id="30c03-113">가비지 수집 생성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-113">Identifies a garbage collection generation.</span></span>  
  
 [<span data-ttu-id="30c03-114">COR_PRF_GC_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-114">COR_PRF_GC_REASON Enumeration</span></span>](cor-prf-gc-reason-enumeration.md)  
 <span data-ttu-id="30c03-115">가비지 컬렉션이 수행되는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-115">Indicates the reason that garbage collection is occurring.</span></span>  
  
 [<span data-ttu-id="30c03-116">COR_PRF_GC_ROOT_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-116">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>](cor-prf-gc-root-flags-enumeration.md)  
 <span data-ttu-id="30c03-117">가비지 수집기 루트의 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-117">Indicates properties of a garbage collector root.</span></span>  
  
 [<span data-ttu-id="30c03-118">COR_PRF_GC_ROOT_KIND 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-118">COR_PRF_GC_ROOT_KIND Enumeration</span></span>](cor-prf-gc-root-kind-enumeration.md)  
 <span data-ttu-id="30c03-119">[ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) 콜백에서 노출 하는 가비지 수집기 루트의 종류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-119">Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
 [<span data-ttu-id="30c03-120">COR_PRF_HIGH_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-120">COR_PRF_HIGH_MONITOR Enumeration</span></span>](cor-prf-high-monitor-enumeration.md)  
 <span data-ttu-id="30c03-121">프로파일러에서 로드할 때 [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 메서드에 지정할 수 있는 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형에 있는 플래그 외에도 플래그를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-121">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
 [<span data-ttu-id="30c03-122">COR_PRF_JIT_CACHE 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-122">COR_PRF_JIT_CACHE Enumeration</span></span>](cor-prf-jit-cache-enumeration.md)  
 <span data-ttu-id="30c03-123">캐시된 함수 검색의 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-123">Indicates the result of a cached function search.</span></span>  
  
 [<span data-ttu-id="30c03-124">COR_PRF_MISC 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-124">COR_PRF_MISC Enumeration</span></span>](cor-prf-misc-enumeration.md)  
 <span data-ttu-id="30c03-125">특수 식별자를 지정하는 상수 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-125">Contains constant values that specify special identifiers.</span></span>  
  
 [<span data-ttu-id="30c03-126">COR_PRF_MODULE_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-126">COR_PRF_MODULE_FLAGS Enumeration</span></span>](cor-prf-module-flags-enumeration.md)  
 <span data-ttu-id="30c03-127">모듈의 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-127">Specifies the properties of a module.</span></span>  
  
 [<span data-ttu-id="30c03-128">COR_PRF_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-128">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)  
 <span data-ttu-id="30c03-129">프로파일러가 구독하려는 동작, 기능 또는 이벤트를 지정하는 데 사용되는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-129">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
 [<span data-ttu-id="30c03-130">COR_PRF_RUNTIME_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-130">COR_PRF_RUNTIME_TYPE Enumeration</span></span>](cor-prf-runtime-type-enumeration.md)  
 <span data-ttu-id="30c03-131">공용 언어 런타임의 버전을 나타내는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-131">Contains values that indicate the version of the common language runtime.</span></span>  
  
 [<span data-ttu-id="30c03-132">COR_PRF_SNAPSHOT_INFO 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-132">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>](cor-prf-snapshot-info-enumeration.md)  
 <span data-ttu-id="30c03-133">프로파일러 `StackSnapshotCallback` 함수에 대한 각 호출에서 스택 스냅샷과 함께 다시 전달할 데이터의 양을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-133">Specifies how much data to pass back with a stack snapshot in each call to the profiler's `StackSnapshotCallback` function.</span></span>  
  
 [<span data-ttu-id="30c03-134">COR_PRF_STATIC_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-134">COR_PRF_STATIC_TYPE Enumeration</span></span>](cor-prf-static-type-enumeration.md)  
 <span data-ttu-id="30c03-135">필드가 정적인지 여부와 정적인 경우 필드에 적용될 정적 품질을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-135">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span>  
  
 [<span data-ttu-id="30c03-136">COR_PRF_SUSPEND_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-136">COR_PRF_SUSPEND_REASON Enumeration</span></span>](cor-prf-suspend-reason-enumeration.md)  
 <span data-ttu-id="30c03-137">런타임이 일시 중단된 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-137">Indicates the reason that the runtime was suspended.</span></span>  
  
 [<span data-ttu-id="30c03-138">COR_PRF_TRANSITION_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="30c03-138">COR_PRF_TRANSITION_REASON Enumeration</span></span>](cor-prf-transition-reason-enumeration.md)  
 <span data-ttu-id="30c03-139">관리 코드에서 비관리 코드로 전환 또는 그 반대의 경우로 전환하는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30c03-139">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="30c03-140">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="30c03-140">Related Sections</span></span>  

 [<span data-ttu-id="30c03-141">프로파일링 개요</span><span class="sxs-lookup"><span data-stu-id="30c03-141">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="30c03-142">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30c03-142">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="30c03-143">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="30c03-143">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="30c03-144">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="30c03-144">Profiling Structures</span></span>](profiling-structures.md)
