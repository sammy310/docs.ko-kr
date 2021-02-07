---
description: '자세히 알아보기: StackSnapshotCallback 함수'
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
ms.openlocfilehash: a49588bc3277956acad612afd0fcab3fa7edffbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736858"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="6746e-103">StackSnapshotCallback 함수</span><span class="sxs-lookup"><span data-stu-id="6746e-103">StackSnapshotCallback Function</span></span>

<span data-ttu-id="6746e-104">[ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) 메서드에서 시작 하는 스택 워크를 실행 하는 동안 스택에서 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보를 프로파일러에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-104">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6746e-105">구문</span><span class="sxs-lookup"><span data-stu-id="6746e-105">Syntax</span></span>  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6746e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6746e-106">Parameters</span></span>  

 `funcId`  
 <span data-ttu-id="6746e-107">진행 이 값이 0 인 경우이 콜백은 관리 되지 않는 프레임의 실행에 대 한 것입니다. 그렇지 않은 경우 관리 되는 함수의 식별자 이며이 콜백은 관리 되는 프레임에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-107">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="6746e-108">진행 프레임에 있는 네이티브 코드 명령 포인터의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-108">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="6746e-109">진행 `COR_PRF_FRAME_INFO` 스택 프레임에 대 한 정보를 참조 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-109">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="6746e-110">이 값은이 콜백 하는 동안에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-110">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="6746e-111">진행 `CONTEXT` 매개 변수에서 참조 하는 구조체의 크기입니다 `context` .</span><span class="sxs-lookup"><span data-stu-id="6746e-111">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="6746e-112">진행 `CONTEXT` 이 프레임의 CPU 상태를 나타내는 Win32 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-112">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="6746e-113">`context`매개 변수는 COR_PRF_SNAPSHOT_CONTEXT 플래그가 전달 된 경우에만 유효 `ICorProfilerInfo2::DoStackSnapshot` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-113">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="6746e-114">진행 에서 직접 전달 되는 클라이언트 데이터에 대 한 포인터입니다 `ICorProfilerInfo2::DoStackSnapshot` .</span><span class="sxs-lookup"><span data-stu-id="6746e-114">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6746e-115">설명</span><span class="sxs-lookup"><span data-stu-id="6746e-115">Remarks</span></span>  

 <span data-ttu-id="6746e-116">`StackSnapshotCallback`함수는 프로파일러 작성기에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-116">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="6746e-117">에서 수행 되는 작업의 복잡성을 제한 해야 합니다 `StackSnapshotCallback` .</span><span class="sxs-lookup"><span data-stu-id="6746e-117">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="6746e-118">예를 들어 비동기 방식으로를 사용 하 `ICorProfilerInfo2::DoStackSnapshot` 는 경우 대상 스레드가 잠금을 보유 하 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-118">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="6746e-119">내의 코드에 `StackSnapshotCallback` 동일한 잠금이 필요한 경우 교착 상태가 뒤따르게 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-119">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="6746e-120">`ICorProfilerInfo2::DoStackSnapshot`메서드는 `StackSnapshotCallback` 관리 되는 프레임당 한 번 또는 관리 되지 않는 프레임의 실행 당 한 번씩 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-120">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="6746e-121">`StackSnapshotCallback`관리 되지 않는 프레임의 실행에 대해를 호출 하면 프로파일러에서 등록 컨텍스트 (매개 변수로 참조 됨)를 사용 `context` 하 여 관리 되지 않는 자체 스택 워크를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-121">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="6746e-122">이 경우 Win32 `CONTEXT` 구조는 관리 되지 않는 프레임 실행 내에서 가장 최근에 푸시되는 프레임의 CPU 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-122">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="6746e-123">Win32 구조에 `CONTEXT` 모든 레지스터의 값이 포함 되어 있지만 스택 포인터 레지스터, 프레임 포인터 레지스터, 명령 포인터 레지스터 및 비휘발성 (즉, 유지 되는) 정수 레지스터의 값만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6746e-123">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6746e-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6746e-124">Requirements</span></span>  

 <span data-ttu-id="6746e-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6746e-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6746e-126">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="6746e-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6746e-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6746e-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6746e-128">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6746e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6746e-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6746e-129">See also</span></span>

- [<span data-ttu-id="6746e-130">DoStackSnapshot 메서드</span><span class="sxs-lookup"><span data-stu-id="6746e-130">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="6746e-131">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="6746e-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
