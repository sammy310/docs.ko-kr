---
title: StackSnapshotCallback 함수
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 891423661f45a1167d53385e6e0306fb09487278
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000417"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="cf147-102">StackSnapshotCallback 함수</span><span class="sxs-lookup"><span data-stu-id="cf147-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="cf147-103">프로파일러가 시작 되는 스택 워크 중 스택의 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보를 제공 합니다 [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="cf147-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf147-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf147-104">Syntax</span></span>  
  
```  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf147-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf147-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="cf147-106">[in] 이 콜백을 실행 하는 관리 되지 않는 프레임입니다이 값이 0 인 경우 이 고, 그렇지 관리 되는 함수의 식별자 이며이 콜백은 관리 되는 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="cf147-107">[in] 프레임에서 네이티브 코드 명령 포인터의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="cf147-108">[in] `COR_PRF_FRAME_INFO` 스택 프레임에 대 한 정보를 참조 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="cf147-109">이 값은이 콜백 중에 사용 하기에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="cf147-110">[in] 크기를 `CONTEXT` 에서 참조 하는 구조는 `context` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="cf147-111">[in] Win32에 대 한 포인터 `CONTEXT` 이 프레임에 대 한 CPU의 상태를 나타내는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="cf147-112">합니다 `context` 매개 변수는 COR_PRF_SNAPSHOT_CONTEXT 플래그에 전달 된 경우에 유효 `ICorProfilerInfo2::DoStackSnapshot`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="cf147-113">[in] 직접 전달 되는 클라이언트 데이터에 대 한 포인터 `ICorProfilerInfo2::DoStackSnapshot`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf147-114">설명</span><span class="sxs-lookup"><span data-stu-id="cf147-114">Remarks</span></span>  
 <span data-ttu-id="cf147-115">`StackSnapshotCallback` 프로파일러 작성기에서 함수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="cf147-116">수행 된 작업의 복잡성을 제한 해야 `StackSnapshotCallback`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="cf147-117">예를 들어, 사용 하는 경우 `ICorProfilerInfo2::DoStackSnapshot` 비동기 방식으로, 대상 스레드가 있습니다 잠금을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="cf147-118">경우 내 코드 `StackSnapshotCallback` 같은 잠금이 필요 교착 상태 충돌 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="cf147-119">합니다 `ICorProfilerInfo2::DoStackSnapshot` 메서드 호출을 `StackSnapshotCallback` 함수 관리 되는 프레임 마다 한 번씩 또는 관리 되지 않는 프레임 실행 당 한 번입니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="cf147-120">경우 `StackSnapshotCallback` 라고 관리 되지 않는 프레임의 실행에 대 한 프로파일러 레지스터 컨텍스트로 사용할 수 있습니다 (에서 참조 하는 `context` 매개 변수)는 자체 관리 되지 않는 스택 워크가 수행 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="cf147-121">이 경우 Win32 `CONTEXT` 구조 관리 되지 않는 프레임이 실행 되는 가장 최근에 푸시된 프레임에 대 한 CPU 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="cf147-122">하지만 Win32 `CONTEXT` 모든 등록에 대 한 값을 포함 하는 구조, 스택 포인터 레지스터와 프레임 포인터 레지스터, 명령 포인터 레지스터 (보존)이 표시 되는 비휘발성의 값에만 의존 하는 정수 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="cf147-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf147-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf147-123">Requirements</span></span>  
 <span data-ttu-id="cf147-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cf147-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf147-125">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="cf147-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="cf147-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf147-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf147-127">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf147-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf147-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="cf147-128">See also</span></span>

- [<span data-ttu-id="cf147-129">DoStackSnapshot 메서드</span><span class="sxs-lookup"><span data-stu-id="cf147-129">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="cf147-130">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="cf147-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
