---
title: ICorProfilerInfo3::GetFunctionLeave3Info 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d51462017287d42fd468ed0a74a2e83203a3d94
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000625"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="caccf-102">ICorProfilerInfo3::GetFunctionLeave3Info 메서드</span><span class="sxs-lookup"><span data-stu-id="caccf-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>
<span data-ttu-id="caccf-103">스택 프레임 및 프로파일러에 보고 되는 함수의 반환 값을 제공 합니다 [FunctionLeave3WithInfo 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="caccf-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="caccf-104">이 함수는 `FunctionLeave3WithInfo` 콜백 중에만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caccf-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caccf-105">구문</span><span class="sxs-lookup"><span data-stu-id="caccf-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caccf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="caccf-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="caccf-107">[in] `FunctionID` 를 반환 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="caccf-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="caccf-108">[in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="caccf-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="caccf-109">프로파일러는 동일한 제공 해야 `eltInfo` 프로파일러는 지정 된 된 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="caccf-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="caccf-110">[out] 지정된 스택 프레임에 대한 일반 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="caccf-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="caccf-111">이 핸들은 프로파일러가 `GetFunctionLeave3Info` 메서드를 호출한 `FunctionLeave3WithInfo` 콜백 중에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="caccf-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="caccf-112">[out] 에 대 한 포인터를 [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) 함수에서 반환 되는 값이 포함 된 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="caccf-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="caccf-113">반환 값 정보에 액세스할 수는 `COR_PRF_ENABLE_FUNCTION_RETVAL` 플래그를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caccf-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="caccf-114">프로파일러를 사용 하 여 수를 [icorprofilerinfo:: Seteventmask 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 이벤트 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="caccf-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="caccf-115">설명</span><span class="sxs-lookup"><span data-stu-id="caccf-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caccf-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="caccf-116">Requirements</span></span>  
 <span data-ttu-id="caccf-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="caccf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caccf-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="caccf-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="caccf-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caccf-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caccf-120">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caccf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caccf-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="caccf-121">See also</span></span>

- [<span data-ttu-id="caccf-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="caccf-122">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="caccf-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="caccf-123">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="caccf-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="caccf-124">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="caccf-125">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="caccf-125">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="caccf-126">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="caccf-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="caccf-127">프로파일링</span><span class="sxs-lookup"><span data-stu-id="caccf-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
