---
title: 프로파일링 인터페이스
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: f073794b4fdf89f289b70fed9967ee37b5f4e133
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494035"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="c5508-102">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-102">Profiling Interfaces</span></span>
<span data-ttu-id="c5508-103">이 섹션에서는 CLR(공용 언어 런타임)에서 실행되는 프로그램을 프로파일링하는 데 사용할 수 있는 관리되지 않는 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c5508-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c5508-104">In This Section</span></span>  
 [<span data-ttu-id="c5508-105">ICLRProfiling 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-105">ICLRProfiling Interface</span></span>](iclrprofiling-interface.md)  
 <span data-ttu-id="c5508-106">프로파일러가 실행 중인 프로세스에 연결할 수 있도록 하는 [AttachProfiler](iclrprofiling-attachprofiler-method.md) 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-106">Provides the [AttachProfiler](iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="c5508-107">ICorProfilerAssemblyReferenceProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="c5508-108">프로파일러가 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback에서 추가 될 어셈블리 참조의 CLR에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="c5508-109">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-109">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)  
 <span data-ttu-id="c5508-110">코드 프로파일러가 구독한 이벤트가 발생하면 CLR이 해당 프로파일러에 알림을 보내는 데 사용되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="c5508-111">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-111">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)  
 <span data-ttu-id="c5508-112">.NET Framework 2.0 이상 버전에서 지원되는 콜백으로 `ICorProfilerCallback` 인터페이스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="c5508-113">ICorProfilerCallback3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-113">ICorProfilerCallback3 Interface</span></span>](icorprofilercallback3-interface.md)  
 <span data-ttu-id="c5508-114">CLR이 프로파일러에 연결 및 분리 상태 정보를 전달하는 데 사용하는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="c5508-115">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-115">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)  
 <span data-ttu-id="c5508-116">CLR이 프로파일러에 정보를 전달하는 데 사용하는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="c5508-117">ICorProfilerCallback5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-117">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)  
 <span data-ttu-id="c5508-118">가비지 컬렉션 루트에서 참조하는 개체의 전이적 Closure를 식별하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="c5508-119">ICorProfilerCallback6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-119">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)  
 <span data-ttu-id="c5508-120">CLR이 어셈블리를 로드하는 중임을 프로파일러에 알리는 데 사용하는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="c5508-121">ICorProfilerCallback7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-121">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)  
 <span data-ttu-id="c5508-122">메모리 내 모듈과 연관 된 기호 스트림이 업데이트 되었음을 프로파일러에 알리기 위해 공용 언어 런타임에서 사용 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="c5508-123">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)  
<span data-ttu-id="c5508-124">공용 언어 런타임에서 동적 메서드의 JIT 컴파일이 시작 및 완료 되었음을 프로파일러에 알리는 데 사용 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="c5508-125">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-125">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)  
<span data-ttu-id="c5508-126">공용 언어 런타임에서 동적 메서드가 가비지 수집 되 고 이후에 언로드되는 것을 프로파일러에 알리는 데 사용 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="c5508-127">ICorProfilerFunctionControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-127">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="c5508-128">코드 프로파일러가 CLR과 통신하여 특정 메서드를 다시 컴파일할 때 JIT 컴파일러가 코드를 생성하는 방법을 제어할 수 있도록 하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="c5508-129">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-129">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="c5508-130">CLR에서 함수 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="c5508-131">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-131">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)  
 <span data-ttu-id="c5508-132">코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하고 정보를 요청하는 데 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="c5508-133">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-133">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)  
 <span data-ttu-id="c5508-134">.NET Framework 2.0 이상 버전에서 지원되는 메서드로 `ICorProfilerInfo` 인터페이스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="c5508-135">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-135">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)  
 <span data-ttu-id="c5508-136">`ICorProfilerInfo2`.NET Framework 4 이상 버전에서 지원 되는 메서드로 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="c5508-137">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-137">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)  
 <span data-ttu-id="c5508-138">코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하고 정보를 요청하는 데 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="c5508-139">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-139">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)  
 <span data-ttu-id="c5508-140">코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하는 데 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="c5508-141">ICorProfilerInfo6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-141">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)  
 <span data-ttu-id="c5508-142">지정 된 NGen 모듈에 속하고 지정 된 메서드의 본문에서 인라인 된 모든 메서드에 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="c5508-143">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-143">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)  
 <span data-ttu-id="c5508-144">새로 정의 된 메타 데이터를 모듈에 적용 하 고 메모리 내 기호 스트림에 대 한 액세스를 제공 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="c5508-145">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-145">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="c5508-146">애플리케이션이나 프로파일러가 로드한 모듈 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="c5508-147">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-147">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="c5508-148">[Ngen.exe (네이티브 이미지 생성기)](../../tools/ngen-exe-native-image-generator.md)에 의해 생성 되는 고정 된 개체의 컬렉션을 순차적으로 반복 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="c5508-149">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-149">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="c5508-150">CLR에서 스레드 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="c5508-151">IMethodMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5508-151">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)  
 <span data-ttu-id="c5508-152">새 MSIL (Microsoft 중간 언어) 함수 본문에 메모리를 할당 하는 [Alloc](imethodmalloc-alloc-method.md) 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5508-152">Provides the [Alloc](imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c5508-153">관련 단원</span><span class="sxs-lookup"><span data-stu-id="c5508-153">Related Sections</span></span>  
 [<span data-ttu-id="c5508-154">프로파일링 개요</span><span class="sxs-lookup"><span data-stu-id="c5508-154">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="c5508-155">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="c5508-155">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="c5508-156">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="c5508-156">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="c5508-157">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="c5508-157">Profiling Structures</span></span>](profiling-structures.md)
