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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a070d2e863aecf7b13eb59a118848b96d2cccc17
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781302"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="59e9b-102">FunctionIDMapper2 함수</span><span class="sxs-lookup"><span data-stu-id="59e9b-102">FunctionIDMapper2 Function</span></span>
<span data-ttu-id="59e9b-103">함수는 지정 된 식별자에 사용할 대체 ID를 다시 매핑할 수는 프로파일러에 알립니다. 합니다 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)를 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), 및 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), 또는[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)를 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), 및 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) 해당 함수에 대 한 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="59e9b-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), or[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="59e9b-104">`FunctionIDMapper2`를 통해 프로파일러는 해당 함수에 대한 콜백을 받을지 여부를 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e9b-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59e9b-105">구문</span><span class="sxs-lookup"><span data-stu-id="59e9b-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59e9b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59e9b-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="59e9b-107">[in] 다시 매핑할 함수 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="59e9b-107">[in] The function identifier to be remapped.</span></span>  
  
 `clientData`  
 <span data-ttu-id="59e9b-108">[in] 런타임 중 명확히 구분하는 데 사용되는 데이터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59e9b-108">[in] A pointer to data that is used to disambiguate among runtimes.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="59e9b-109">[out] 프로파일러가 `FunctionEnter3`, `FunctionLeave3` 및 `FunctionTailcall3` 또는 `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo` 및 `FunctionTailcall3WithInfo` 콜백을 받으려는 경우 `true`로 설정하는 값에 대한 포인터입니다. 그러지 않으면 이 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="59e9b-109">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59e9b-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="59e9b-110">Return Value</span></span>  
 <span data-ttu-id="59e9b-111">프로파일러는 실행 엔진이 대체 함수 식별자로 사용하는 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="59e9b-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="59e9b-112">`false`가 `pbHookFunction`에 반환되지 않는 한 반환 값은 null일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59e9b-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="59e9b-113">그러지 않은 경우 null 반환 값에서 프로세스 중지를 포함하여 예기치 않은 결과가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="59e9b-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59e9b-114">설명</span><span class="sxs-lookup"><span data-stu-id="59e9b-114">Remarks</span></span>  
 <span data-ttu-id="59e9b-115">이 메서드가 확장 합니다 [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) 클라이언트 데이터를 전달 하는 데 사용 되는 추가 매개 변수를 사용 하 여 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="59e9b-115">This method extends the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="59e9b-116">클라이언트 데이터는 런타임 중 명확히 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="59e9b-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59e9b-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59e9b-117">Requirements</span></span>  
 <span data-ttu-id="59e9b-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="59e9b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59e9b-119">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="59e9b-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="59e9b-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59e9b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59e9b-121">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59e9b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59e9b-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="59e9b-122">See also</span></span>

- [<span data-ttu-id="59e9b-123">ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="59e9b-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="59e9b-124">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="59e9b-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="59e9b-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="59e9b-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="59e9b-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="59e9b-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="59e9b-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="59e9b-127">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="59e9b-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="59e9b-128">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="59e9b-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="59e9b-129">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="59e9b-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="59e9b-130">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="59e9b-131">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="59e9b-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
