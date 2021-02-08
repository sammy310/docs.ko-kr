---
description: '자세한 정보: 프로 파일링 인터페이스'
title: 프로파일링 인터페이스
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: d35931c0caad93116d7ea26d29020d84e48ebc29
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798929"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="dacfe-103">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-103">Profiling Interfaces</span></span>

<span data-ttu-id="dacfe-104">이 섹션에서는 CLR(공용 언어 런타임)에서 실행되는 프로그램을 프로파일링하는 데 사용할 수 있는 관리되지 않는 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-104">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dacfe-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="dacfe-105">In This Section</span></span>  

 [<span data-ttu-id="dacfe-106">ICLRProfiling 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-106">ICLRProfiling Interface</span></span>](iclrprofiling-interface.md)  
 <span data-ttu-id="dacfe-107">프로파일러가 실행 중인 프로세스에 연결할 수 있도록 하는 [AttachProfiler](iclrprofiling-attachprofiler-method.md) 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-107">Provides the [AttachProfiler](iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="dacfe-108">ICorProfilerAssemblyReferenceProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-108">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="dacfe-109">프로파일러가 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback에서 추가 될 어셈블리 참조의 CLR에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-109">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="dacfe-110">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-110">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)  
 <span data-ttu-id="dacfe-111">코드 프로파일러가 구독한 이벤트가 발생하면 CLR이 해당 프로파일러에 알림을 보내는 데 사용되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-111">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="dacfe-112">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-112">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)  
 <span data-ttu-id="dacfe-113">.NET Framework 2.0 이상 버전에서 지원되는 콜백으로 `ICorProfilerCallback` 인터페이스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-113">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="dacfe-114">ICorProfilerCallback3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-114">ICorProfilerCallback3 Interface</span></span>](icorprofilercallback3-interface.md)  
 <span data-ttu-id="dacfe-115">CLR이 프로파일러에 연결 및 분리 상태 정보를 전달하는 데 사용하는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-115">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="dacfe-116">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-116">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)  
 <span data-ttu-id="dacfe-117">CLR이 프로파일러에 정보를 전달하는 데 사용하는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-117">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="dacfe-118">ICorProfilerCallback5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-118">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)  
 <span data-ttu-id="dacfe-119">가비지 컬렉션 루트에서 참조하는 개체의 전이적 Closure를 식별하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-119">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="dacfe-120">ICorProfilerCallback6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-120">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)  
 <span data-ttu-id="dacfe-121">CLR이 어셈블리를 로드하는 중임을 프로파일러에 알리는 데 사용하는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-121">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="dacfe-122">ICorProfilerCallback7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-122">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)  
 <span data-ttu-id="dacfe-123">메모리 내 모듈과 연관 된 기호 스트림이 업데이트 되었음을 프로파일러에 알리기 위해 공용 언어 런타임에서 사용 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-123">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="dacfe-124">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-124">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)  
<span data-ttu-id="dacfe-125">공용 언어 런타임에서 동적 메서드의 JIT 컴파일이 시작 및 완료 되었음을 프로파일러에 알리는 데 사용 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-125">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="dacfe-126">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-126">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)  
<span data-ttu-id="dacfe-127">공용 언어 런타임에서 동적 메서드가 가비지 수집 되 고 이후에 언로드되는 것을 프로파일러에 알리는 데 사용 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-127">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="dacfe-128">ICorProfilerFunctionControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-128">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="dacfe-129">코드 프로파일러가 CLR과 통신하여 특정 메서드를 다시 컴파일할 때 JIT 컴파일러가 코드를 생성하는 방법을 제어할 수 있도록 하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-129">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="dacfe-130">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-130">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="dacfe-131">CLR에서 함수 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-131">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="dacfe-132">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-132">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)  
 <span data-ttu-id="dacfe-133">코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하고 정보를 요청하는 데 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-133">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="dacfe-134">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-134">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)  
 <span data-ttu-id="dacfe-135">.NET Framework 2.0 이상 버전에서 지원되는 메서드로 `ICorProfilerInfo` 인터페이스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-135">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="dacfe-136">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-136">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)  
 <span data-ttu-id="dacfe-137">`ICorProfilerInfo2`.NET Framework 4 이상 버전에서 지원 되는 메서드로 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-137">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="dacfe-138">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-138">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)  
 <span data-ttu-id="dacfe-139">코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하고 정보를 요청하는 데 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-139">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="dacfe-140">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-140">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)  
 <span data-ttu-id="dacfe-141">코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하는 데 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-141">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="dacfe-142">ICorProfilerInfo6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-142">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)  
 <span data-ttu-id="dacfe-143">지정 된 NGen 모듈에 속하고 지정 된 메서드의 본문에서 인라인 된 모든 메서드에 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-143">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="dacfe-144">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-144">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)  
 <span data-ttu-id="dacfe-145">새로 정의 된 메타 데이터를 모듈에 적용 하 고 메모리 내 기호 스트림에 대 한 액세스를 제공 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-145">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="dacfe-146">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-146">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="dacfe-147">애플리케이션이나 프로파일러가 로드한 모듈 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-147">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="dacfe-148">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-148">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="dacfe-149">[Ngen.exe (네이티브 이미지 생성기)](../../tools/ngen-exe-native-image-generator.md)에서 생성 되는 고정 된 개체의 컬렉션을 순차적으로 반복 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-149">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="dacfe-150">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-150">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="dacfe-151">CLR에서 스레드 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-151">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="dacfe-152">IMethodMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dacfe-152">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)  
 <span data-ttu-id="dacfe-153">새 MSIL (Microsoft 중간 언어) 함수 본문에 메모리를 할당 하는 [Alloc](imethodmalloc-alloc-method.md) 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dacfe-153">Provides the [Alloc](imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dacfe-154">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="dacfe-154">Related Sections</span></span>  

 [<span data-ttu-id="dacfe-155">프로파일링 개요</span><span class="sxs-lookup"><span data-stu-id="dacfe-155">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="dacfe-156">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="dacfe-156">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="dacfe-157">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="dacfe-157">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="dacfe-158">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="dacfe-158">Profiling Structures</span></span>](profiling-structures.md)
