---
title: 프로파일링 인터페이스
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d97960a43e1d7ce625d96755a7c597a0425d0911
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2019
ms.locfileid: "66457468"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="d398f-102">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-102">Profiling Interfaces</span></span>
<span data-ttu-id="d398f-103">이 섹션에서는 CLR(공용 언어 런타임)에서 실행되는 프로그램을 프로파일링하는 데 사용할 수 있는 관리되지 않는 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d398f-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d398f-104">In This Section</span></span>  
 [<span data-ttu-id="d398f-105">ICLRProfiling 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="d398f-106">제공 된 [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) 프로파일러를 실행 중인 프로세스에 연결할 수 있도록 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="d398f-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="d398f-107">ICorProfilerAssemblyReferenceProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="d398f-108">CLR 프로파일러에 추가할 어셈블리 참조에 알리기 위해 프로파일러를 사용 하도록 설정 합니다 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="d398f-109">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="d398f-110">코드 프로파일러가 구독한 이벤트가 발생하면 CLR이 해당 프로파일러에 알림을 보내는 데 사용되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="d398f-111">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="d398f-112">.NET Framework 2.0 이상 버전에서 지원되는 콜백으로 `ICorProfilerCallback` 인터페이스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="d398f-113">ICorProfilerCallback3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="d398f-114">CLR이 프로파일러에 연결 및 분리 상태 정보를 전달하는 데 사용하는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="d398f-115">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="d398f-116">CLR이 프로파일러에 정보를 전달하는 데 사용하는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="d398f-117">ICorProfilerCallback5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="d398f-118">가비지 컬렉션 루트에서 참조하는 개체의 전이적 Closure를 식별하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="d398f-119">ICorProfilerCallback6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="d398f-120">CLR이 어셈블리를 로드하는 중임을 프로파일러에 알리는 데 사용하는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="d398f-121">ICorProfilerCallback7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="d398f-122">메모리 내 모듈과 연관 된 기호 스트림이 업데이트 되는 프로파일러에 알리기 위해 공용 언어 런타임에서 사용 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="d398f-123">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-123">ICorProfilerCallback8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-interface.md)  
<span data-ttu-id="d398f-124">동적 메서드의 JIT 컴파일을 시작 되 고 완료 하는 프로파일러에 알리기 위해 공용 언어 런타임에서 사용 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="d398f-125">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-125">ICorProfilerCallback9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback9-interface.md)  
<span data-ttu-id="d398f-126">동적 메서드는 가비지 수집 되 고 이후에 언로드된 프로파일러에 알리기 위해 공용 언어 런타임에서 사용 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="d398f-127">ICorProfilerFunctionControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-127">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="d398f-128">코드 프로파일러가 CLR과 통신하여 특정 메서드를 다시 컴파일할 때 JIT 컴파일러가 코드를 생성하는 방법을 제어할 수 있도록 하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="d398f-129">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-129">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="d398f-130">CLR에서 함수 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="d398f-131">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-131">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="d398f-132">코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하고 정보를 요청하는 데 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="d398f-133">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-133">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="d398f-134">.NET Framework 2.0 이상 버전에서 지원되는 메서드로 `ICorProfilerInfo` 인터페이스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="d398f-135">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-135">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="d398f-136">확장 된 `ICorProfilerInfo2` .NET Framework 4 및 이후 버전에서 지원 되는 메서드를 사용 하 여 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="d398f-137">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-137">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="d398f-138">코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하고 정보를 요청하는 데 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="d398f-139">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-139">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="d398f-140">코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하는 데 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="d398f-141">ICorProfilerInfo6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-141">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="d398f-142">지정 된 NGen 모듈에 속하고 지정 된 메서드의 본문에 인라인 처리 되지 않은 모든 메서드는 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="d398f-143">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-143">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="d398f-144">메모리 내 기호 스트림에 대 한 액세스를 제공 하는 및 모듈에 정의 된 메타 데이터가 새로 적용 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="d398f-145">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-145">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="d398f-146">애플리케이션이나 프로파일러가 로드한 모듈 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="d398f-147">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-147">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="d398f-148">생성 되는 고정 된 개체의 컬렉션을 순차적으로 반복 하는 메서드를 제공 [Ngen.exe (네이티브 이미지 생성기)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="d398f-149">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-149">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="d398f-150">CLR에서 스레드 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="d398f-151">IMethodMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d398f-151">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="d398f-152">제공 된 [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) 새 Microsoft MSIL (intermediate language) 함수 본문에 대 한 메모리를 할당 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d398f-152">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d398f-153">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d398f-153">Related Sections</span></span>  
 [<span data-ttu-id="d398f-154">프로파일링 개요</span><span class="sxs-lookup"><span data-stu-id="d398f-154">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="d398f-155">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="d398f-155">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="d398f-156">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="d398f-156">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="d398f-157">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="d398f-157">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
