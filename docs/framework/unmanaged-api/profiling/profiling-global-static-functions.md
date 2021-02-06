---
description: '자세히 알아보기: 전역 정적 함수 프로 파일링'
title: 프로파일링 전역 정적 함수
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 86e4b6bda73b0783f5f95e4e7dbc24f1ccccb130
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646376"
---
# <a name="profiling-global-static-functions"></a><span data-ttu-id="6eddb-103">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-103">Profiling Global Static Functions</span></span>

<span data-ttu-id="6eddb-104">이 섹션에서는 프로 파일링 API에서 사용 하는 관리 되지 않는 API 함수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-104">This section describes the unmanaged API functions that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6eddb-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6eddb-105">In This Section</span></span>  
  
## <a name="net-framework-version-1-profiling-functions"></a><span data-ttu-id="6eddb-106">.NET Framework 버전 1 프로 파일링 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-106">.NET Framework version 1 Profiling Functions</span></span>  

 [<span data-ttu-id="6eddb-107">FunctionEnter 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-107">FunctionEnter Function</span></span>](functionenter-function.md)  
 <span data-ttu-id="6eddb-108">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-108">Notifies the profiler that control is being passed to a function.</span></span> <span data-ttu-id="6eddb-109">.NET Framework 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-109">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="6eddb-110">FunctionLeave 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-110">FunctionLeave Function</span></span>](functionleave-function.md)  
 <span data-ttu-id="6eddb-111">함수가 호출자에 게 반환 될 것 이라고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-111">Notifies the profiler that a function is about to return to the caller.</span></span> <span data-ttu-id="6eddb-112">.NET Framework 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-112">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="6eddb-113">FunctionTailcall 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-113">FunctionTailcall Function</span></span>](functiontailcall-function.md)  
 <span data-ttu-id="6eddb-114">현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-114">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span> <span data-ttu-id="6eddb-115">.NET Framework 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-115">Deprecated in the .NET Framework 2.0.</span></span>  
  
## <a name="net-framework-version-2-profiling-functions"></a><span data-ttu-id="6eddb-116">.NET Framework 버전 2 프로 파일링 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-116">.NET Framework version 2 Profiling Functions</span></span>  

 [<span data-ttu-id="6eddb-117">FunctionIDMapper 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-117">FunctionIDMapper Function</span></span>](functionidmapper-function.md)  
 <span data-ttu-id="6eddb-118">함수의 지정 된 식별자를 해당 함수의 [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)및 [FunctionTailcall2](functiontailcall2-function.md) 콜백에서 사용할 대체 ID에 다시 매핑할 수 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-118">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="6eddb-119">또한 프로파일러를 사용 하 여 해당 함수에 대해 콜백을 받을지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-119">Also enables the profiler to indicate whether it wants to receive callbacks for that function</span></span>  
  
 [<span data-ttu-id="6eddb-120">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-120">FunctionEnter2 Function</span></span>](functionenter2-function.md)  
 <span data-ttu-id="6eddb-121">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알리고 스택 프레임 및 함수 인수에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-121">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="6eddb-122">.NET Framework 4에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-122">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="6eddb-123">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-123">FunctionLeave2 Function</span></span>](functionleave2-function.md)  
 <span data-ttu-id="6eddb-124">함수가 호출자에 게 반환 될 것을 프로파일러에 알리고 스택 프레임 및 함수 반환 값에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-124">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span> <span data-ttu-id="6eddb-125">.NET Framework 4에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-125">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="6eddb-126">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-126">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)  
 <span data-ttu-id="6eddb-127">현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알리고 스택 프레임에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-127">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span> <span data-ttu-id="6eddb-128">.NET Framework 4에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-128">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="6eddb-129">StackSnapshotCallback 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-129">StackSnapshotCallback Function</span></span>](stacksnapshotcallback-function.md)  
 <span data-ttu-id="6eddb-130">[ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) 메서드에서 시작 하는 스택 워크를 실행 하는 동안 스택에서 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보를 프로파일러에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-130">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="net-framework-version-4-profiling-functions"></a><span data-ttu-id="6eddb-131">.NET Framework 버전 4 프로 파일링 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-131">.NET Framework version 4 Profiling Functions</span></span>  

 [<span data-ttu-id="6eddb-132">FunctionIDMapper2 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-132">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)  
 <span data-ttu-id="6eddb-133">함수의 지정 된 식별자를 해당 함수의 [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)및 [FunctionTailcall3](functiontailcall3-function.md),[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)및 [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) 콜백에서 사용할 대체 ID에 다시 매핑할 수 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-133">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="6eddb-134">또한 프로파일러는 해당 함수에 대해 콜백을 받을지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-134">Also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
 <span data-ttu-id="6eddb-135">`FunctionIDMapper2` 는 매개 변수를 사용 하 여 [Functionidmapper](functionidmapper-function.md) 함수를 확장 합니다 .이 함수는 `clientData` 프로파일러를 사용 하 여 런타임 중에 모호함을 명확히</span><span class="sxs-lookup"><span data-stu-id="6eddb-135">`FunctionIDMapper2` extends the [FunctionIDMapper](functionidmapper-function.md) function with a `clientData` parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
 [<span data-ttu-id="6eddb-136">FunctionEnter3 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-136">FunctionEnter3 Function</span></span>](functionenter3-function.md)  
 <span data-ttu-id="6eddb-137">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-137">Notifies the profiler that control is being passed to a function.</span></span>  
  
 [<span data-ttu-id="6eddb-138">FunctionEnter3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-138">FunctionEnter3WithInfo Function</span></span>](functionenter3withinfo-function.md)  
 <span data-ttu-id="6eddb-139">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알리고, [ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) 에 전달 하 여 스택 프레임 및 함수 인수를 검색 하는 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-139">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
 [<span data-ttu-id="6eddb-140">FunctionLeave3 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-140">FunctionLeave3 Function</span></span>](functionleave3-function.md)  
 <span data-ttu-id="6eddb-141">컨트롤이 함수에서 반환 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-141">Notifies the profiler that control is being returned from a function.</span></span>  
  
 [<span data-ttu-id="6eddb-142">FunctionLeave3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-142">FunctionLeave3WithInfo Function</span></span>](functionleave3withinfo-function.md)  
 <span data-ttu-id="6eddb-143">는 컨트롤이 함수에서 반환 되 고 있음을 프로파일러에 알리고 스택 프레임 및 반환 값을 검색 하기 위해 [ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) 에 전달할 수 있는 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-143">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
 [<span data-ttu-id="6eddb-144">FunctionTailcall3 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-144">FunctionTailcall3 Function</span></span>](functiontailcall3-function.md)  
 <span data-ttu-id="6eddb-145">현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-145">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
 [<span data-ttu-id="6eddb-146">FunctionTailcall3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="6eddb-146">FunctionTailcall3WithInfo Function</span></span>](functiontailcall3withinfo-function.md)  
 <span data-ttu-id="6eddb-147">현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알리고 스택 프레임을 검색 하기 위해 [ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) 에 전달할 수 있는 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eddb-147">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6eddb-148">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="6eddb-148">Related Sections</span></span>  

 [<span data-ttu-id="6eddb-149">프로파일링 개요</span><span class="sxs-lookup"><span data-stu-id="6eddb-149">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="6eddb-150">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6eddb-150">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="6eddb-151">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="6eddb-151">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="6eddb-152">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="6eddb-152">Profiling Structures</span></span>](profiling-structures.md)
