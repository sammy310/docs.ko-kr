---
title: 프로파일링 전역 정적 함수
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 20ee2a9e045d839aa8ac043e035c438986b987ef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860868"
---
# <a name="profiling-global-static-functions"></a><span data-ttu-id="29be5-102">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-102">Profiling Global Static Functions</span></span>
<span data-ttu-id="29be5-103">이 섹션에서는 프로 파일링 API에서 사용 하는 관리 되지 않는 API 함수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-103">This section describes the unmanaged API functions that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="29be5-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="29be5-104">In This Section</span></span>  
  
## <a name="net-framework-version-1-profiling-functions"></a><span data-ttu-id="29be5-105">.NET Framework 버전 1 프로 파일링 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-105">.NET Framework version 1 Profiling Functions</span></span>  
 [<span data-ttu-id="29be5-106">FunctionEnter 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-106">FunctionEnter Function</span></span>](functionenter-function.md)  
 <span data-ttu-id="29be5-107">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-107">Notifies the profiler that control is being passed to a function.</span></span> <span data-ttu-id="29be5-108">.NET Framework 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-108">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="29be5-109">FunctionLeave 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-109">FunctionLeave Function</span></span>](functionleave-function.md)  
 <span data-ttu-id="29be5-110">함수가 호출자에 게 반환 될 것 이라고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-110">Notifies the profiler that a function is about to return to the caller.</span></span> <span data-ttu-id="29be5-111">.NET Framework 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-111">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="29be5-112">FunctionTailcall 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-112">FunctionTailcall Function</span></span>](functiontailcall-function.md)  
 <span data-ttu-id="29be5-113">현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-113">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span> <span data-ttu-id="29be5-114">.NET Framework 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-114">Deprecated in the .NET Framework 2.0.</span></span>  
  
## <a name="net-framework-version-2-profiling-functions"></a><span data-ttu-id="29be5-115">.NET Framework 버전 2 프로 파일링 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-115">.NET Framework version 2 Profiling Functions</span></span>  
 [<span data-ttu-id="29be5-116">FunctionIDMapper 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-116">FunctionIDMapper Function</span></span>](functionidmapper-function.md)  
 <span data-ttu-id="29be5-117">함수의 지정 된 식별자를 해당 함수의 [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)및 [FunctionTailcall2](functiontailcall2-function.md) 콜백에서 사용할 대체 ID에 다시 매핑할 수 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-117">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="29be5-118">또한 프로파일러를 사용 하 여 해당 함수에 대해 콜백을 받을지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-118">Also enables the profiler to indicate whether it wants to receive callbacks for that function</span></span>  
  
 [<span data-ttu-id="29be5-119">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-119">FunctionEnter2 Function</span></span>](functionenter2-function.md)  
 <span data-ttu-id="29be5-120">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알리고 스택 프레임 및 함수 인수에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-120">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="29be5-121">.NET Framework 4에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-121">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="29be5-122">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-122">FunctionLeave2 Function</span></span>](functionleave2-function.md)  
 <span data-ttu-id="29be5-123">함수가 호출자에 게 반환 될 것을 프로파일러에 알리고 스택 프레임 및 함수 반환 값에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-123">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span> <span data-ttu-id="29be5-124">.NET Framework 4에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-124">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="29be5-125">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-125">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)  
 <span data-ttu-id="29be5-126">현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알리고 스택 프레임에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-126">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span> <span data-ttu-id="29be5-127">.NET Framework 4에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-127">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="29be5-128">StackSnapshotCallback 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-128">StackSnapshotCallback Function</span></span>](stacksnapshotcallback-function.md)  
 <span data-ttu-id="29be5-129">[ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) 메서드에서 시작 하는 스택 워크를 실행 하는 동안 스택에서 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보를 프로파일러에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-129">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="net-framework-version-4-profiling-functions"></a><span data-ttu-id="29be5-130">.NET Framework 버전 4 프로 파일링 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-130">.NET Framework version 4 Profiling Functions</span></span>  
 [<span data-ttu-id="29be5-131">FunctionIDMapper2 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-131">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)  
 <span data-ttu-id="29be5-132">함수의 지정 된 식별자를 해당 함수의 [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)및 [FunctionTailcall3](functiontailcall3-function.md),[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)및 [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) 콜백에서 사용할 대체 ID에 다시 매핑할 수 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-132">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="29be5-133">또한 프로파일러는 해당 함수에 대해 콜백을 받을지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-133">Also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
 <span data-ttu-id="29be5-134">`FunctionIDMapper2`는 `clientData` 매개 변수를 사용 하 여 [Functionidmapper](functionidmapper-function.md) 함수를 확장 합니다 .이 함수는 프로파일러를 사용 하 여 런타임을 명확 하 게 구분할 수</span><span class="sxs-lookup"><span data-stu-id="29be5-134">`FunctionIDMapper2` extends the [FunctionIDMapper](functionidmapper-function.md) function with a `clientData` parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
 [<span data-ttu-id="29be5-135">FunctionEnter3 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-135">FunctionEnter3 Function</span></span>](functionenter3-function.md)  
 <span data-ttu-id="29be5-136">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-136">Notifies the profiler that control is being passed to a function.</span></span>  
  
 [<span data-ttu-id="29be5-137">FunctionEnter3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-137">FunctionEnter3WithInfo Function</span></span>](functionenter3withinfo-function.md)  
 <span data-ttu-id="29be5-138">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알리고, [ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) 에 전달 하 여 스택 프레임 및 함수 인수를 검색 하는 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-138">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
 [<span data-ttu-id="29be5-139">FunctionLeave3 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-139">FunctionLeave3 Function</span></span>](functionleave3-function.md)  
 <span data-ttu-id="29be5-140">컨트롤이 함수에서 반환 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-140">Notifies the profiler that control is being returned from a function.</span></span>  
  
 [<span data-ttu-id="29be5-141">FunctionLeave3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-141">FunctionLeave3WithInfo Function</span></span>](functionleave3withinfo-function.md)  
 <span data-ttu-id="29be5-142">는 컨트롤이 함수에서 반환 되 고 있음을 프로파일러에 알리고 스택 프레임 및 반환 값을 검색 하기 위해 [ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) 에 전달할 수 있는 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-142">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
 [<span data-ttu-id="29be5-143">FunctionTailcall3 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-143">FunctionTailcall3 Function</span></span>](functiontailcall3-function.md)  
 <span data-ttu-id="29be5-144">현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-144">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
 [<span data-ttu-id="29be5-145">FunctionTailcall3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="29be5-145">FunctionTailcall3WithInfo Function</span></span>](functiontailcall3withinfo-function.md)  
 <span data-ttu-id="29be5-146">현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알리고 스택 프레임을 검색 하기 위해 [ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) 에 전달할 수 있는 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-146">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="29be5-147">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="29be5-147">Related Sections</span></span>  
 [<span data-ttu-id="29be5-148">프로파일링 개요</span><span class="sxs-lookup"><span data-stu-id="29be5-148">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="29be5-149">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29be5-149">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="29be5-150">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="29be5-150">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="29be5-151">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="29be5-151">Profiling Structures</span></span>](profiling-structures.md)
