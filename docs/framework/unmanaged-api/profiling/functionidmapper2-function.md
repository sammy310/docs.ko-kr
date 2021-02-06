---
description: '자세히 알아보기: FunctionIDMapper2 함수'
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
ms.openlocfilehash: 1fd6680ffaa7b28e679dc3eaeb9840981ead5c45
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648573"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="c2cab-103">FunctionIDMapper2 함수</span><span class="sxs-lookup"><span data-stu-id="c2cab-103">FunctionIDMapper2 Function</span></span>

<span data-ttu-id="c2cab-104">함수의 지정 된 식별자를 해당 함수의 [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)및 [FunctionTailcall3](functiontailcall3-function.md),[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)및 [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) 콜백에서 사용할 대체 ID에 다시 매핑할 수 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c2cab-104">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="c2cab-105">`FunctionIDMapper2`를 통해 프로파일러는 해당 함수에 대한 콜백을 받을지 여부를 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cab-105">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2cab-106">구문</span><span class="sxs-lookup"><span data-stu-id="c2cab-106">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2cab-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2cab-107">Parameters</span></span>

- `funcId`

  <span data-ttu-id="c2cab-108">\[in] 다시 매핑할 함수 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cab-108">\[in] The function identifier to be remapped.</span></span>

- `clientData`

  <span data-ttu-id="c2cab-109">\[in] 런타임 중에 명확 하 게 구분 하는 데 사용 되는 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2cab-109">\[in] A pointer to data that is used to disambiguate among runtimes.</span></span>

- `pbHookFunction`

  <span data-ttu-id="c2cab-110">\[out],,,,, 및 콜백을 수신 하려는 경우 프로파일러가 설정 하는 값에 대 한 포인터이 고, `true` `FunctionEnter3` `FunctionLeave3` `FunctionTailcall3` `FunctionEnter3WithInfo` `FunctionLeave3WithInfo` `FunctionTailcall3WithInfo` 그렇지 않으면이 값을로 설정 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cab-110">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="c2cab-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="c2cab-111">Return Value</span></span>  

 <span data-ttu-id="c2cab-112">프로파일러는 실행 엔진이 대체 함수 식별자로 사용하는 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cab-112">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="c2cab-113">`false`가 `pbHookFunction`에 반환되지 않는 한 반환 값은 null일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2cab-113">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="c2cab-114">그러지 않은 경우 null 반환 값에서 프로세스 중지를 포함하여 예기치 않은 결과가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cab-114">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2cab-115">설명</span><span class="sxs-lookup"><span data-stu-id="c2cab-115">Remarks</span></span>  

 <span data-ttu-id="c2cab-116">이 메서드는 클라이언트 데이터를 전달 하는 데 사용 되는 추가 매개 변수를 사용 하 여 [Functionidmapper](functionidmapper-function.md) 함수를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2cab-116">This method extends the [FunctionIDMapper](functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="c2cab-117">클라이언트 데이터는 런타임 중 명확히 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2cab-117">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2cab-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2cab-118">Requirements</span></span>  

 <span data-ttu-id="c2cab-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2cab-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2cab-120">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="c2cab-120">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c2cab-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2cab-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2cab-122">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2cab-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2cab-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2cab-123">See also</span></span>

- [<span data-ttu-id="c2cab-124">ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="c2cab-124">ICorProfilerInfo::SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="c2cab-125">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="c2cab-125">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="c2cab-126">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="c2cab-126">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="c2cab-127">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="c2cab-127">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="c2cab-128">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="c2cab-128">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="c2cab-129">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c2cab-129">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="c2cab-130">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c2cab-130">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="c2cab-131">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c2cab-131">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="c2cab-132">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="c2cab-132">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
