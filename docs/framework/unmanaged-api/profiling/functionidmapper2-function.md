---
title: FunctionIDMapper2 함수
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
ms.openlocfilehash: 7aa90b92d129f1269d901f1cbb5c6a0750de9a90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728539"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="42bd5-102">FunctionIDMapper2 함수</span><span class="sxs-lookup"><span data-stu-id="42bd5-102">FunctionIDMapper2 Function</span></span>

<span data-ttu-id="42bd5-103">함수의 지정 된 식별자를 해당 함수의 [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)및 [FunctionTailcall3](functiontailcall3-function.md),[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)및 [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) 콜백에서 사용할 대체 ID에 다시 매핑할 수 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="42bd5-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="42bd5-104">`FunctionIDMapper2`를 통해 프로파일러는 해당 함수에 대한 콜백을 받을지 여부를 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42bd5-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42bd5-105">구문</span><span class="sxs-lookup"><span data-stu-id="42bd5-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42bd5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42bd5-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="42bd5-107">\[in] 다시 매핑할 함수 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="42bd5-107">\[in] The function identifier to be remapped.</span></span>

- `clientData`

  <span data-ttu-id="42bd5-108">\[in] 런타임 중에 명확 하 게 구분 하는 데 사용 되는 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="42bd5-108">\[in] A pointer to data that is used to disambiguate among runtimes.</span></span>

- `pbHookFunction`

  <span data-ttu-id="42bd5-109">\[out],,,,, 및 콜백을 수신 하려는 경우 프로파일러가 설정 하는 값에 대 한 포인터이 고, `true` `FunctionEnter3` `FunctionLeave3` `FunctionTailcall3` `FunctionEnter3WithInfo` `FunctionLeave3WithInfo` `FunctionTailcall3WithInfo` 그렇지 않으면이 값을로 설정 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="42bd5-109">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="42bd5-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="42bd5-110">Return Value</span></span>  

 <span data-ttu-id="42bd5-111">프로파일러는 실행 엔진이 대체 함수 식별자로 사용하는 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="42bd5-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="42bd5-112">`false`가 `pbHookFunction`에 반환되지 않는 한 반환 값은 null일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42bd5-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="42bd5-113">그러지 않은 경우 null 반환 값에서 프로세스 중지를 포함하여 예기치 않은 결과가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="42bd5-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42bd5-114">설명</span><span class="sxs-lookup"><span data-stu-id="42bd5-114">Remarks</span></span>  

 <span data-ttu-id="42bd5-115">이 메서드는 클라이언트 데이터를 전달 하는 데 사용 되는 추가 매개 변수를 사용 하 여 [Functionidmapper](functionidmapper-function.md) 함수를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="42bd5-115">This method extends the [FunctionIDMapper](functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="42bd5-116">클라이언트 데이터는 런타임 중 명확히 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="42bd5-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42bd5-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42bd5-117">Requirements</span></span>  

 <span data-ttu-id="42bd5-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42bd5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42bd5-119">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="42bd5-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="42bd5-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42bd5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42bd5-121">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42bd5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42bd5-122">참조</span><span class="sxs-lookup"><span data-stu-id="42bd5-122">See also</span></span>

- [<span data-ttu-id="42bd5-123">ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="42bd5-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="42bd5-124">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="42bd5-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="42bd5-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="42bd5-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="42bd5-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="42bd5-126">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="42bd5-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="42bd5-127">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="42bd5-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="42bd5-128">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="42bd5-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="42bd5-129">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="42bd5-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="42bd5-130">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="42bd5-131">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="42bd5-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
