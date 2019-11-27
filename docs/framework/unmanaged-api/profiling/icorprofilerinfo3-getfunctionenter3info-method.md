---
title: ICorProfilerInfo3::GetFunctionEnter3Info 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
ms.openlocfilehash: 7e93b92b0b0b4c44955ebc7dfb9d1eb875713c27
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449717"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="d0447-102">ICorProfilerInfo3::GetFunctionEnter3Info 메서드</span><span class="sxs-lookup"><span data-stu-id="d0447-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="d0447-103">[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) 함수에서 프로파일러에 보고 하는 함수의 스택 프레임 및 인수 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0447-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="d0447-104">이 함수는 `FunctionEnter3WithInfo` 콜백 중에만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0447-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0447-105">구문</span><span class="sxs-lookup"><span data-stu-id="d0447-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0447-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0447-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d0447-107">[in] 입력 중인 함수의 `FunctionID`입니다.</span><span class="sxs-lookup"><span data-stu-id="d0447-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="d0447-108">[in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="d0447-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="d0447-109">프로파일러는 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) 함수에서 제공 된 것과 동일한 `eltInfo`를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0447-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="d0447-110">[out] 지정된 스택 프레임에 대한 일반 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="d0447-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="d0447-111">이 핸들은 프로파일러가 `FunctionEnter3WithInfo` 메서드를 호출한 `GetFunctionEnter3Info` 콜백 중에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="d0447-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="d0447-112">[in, out] [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) 구조의 총 크기 (바이트)와 `pArgumentInfo`에서 가리키는 인수 범위의 추가 [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0447-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="d0447-113">지정된 크기가 충분하지 않으면 ERROR_INSUFFICIENT_BUFFER가 반환되고 예상 크기가 `pcbArgumentInfo`에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0447-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="d0447-114">단순히 `GetFunctionEnter3Info`의 예상 값을 검색하기 위해 `*pcbArgumentInfo`를 호출하려면 `*pcbArgumentInfo`=0 및 `pArgumentInfo`=NULL을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0447-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="d0447-115">제한이 메모리의 함수 인수 위치를 왼쪽에서 오른쪽 순서로 설명 하는 [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0447-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0447-116">주의</span><span class="sxs-lookup"><span data-stu-id="d0447-116">Remarks</span></span>  
 <span data-ttu-id="d0447-117">프로파일러는 검사되는 함수의 `COR_PRF_FUNCTION_ARGUMENT_INFO` 구조체에 대해 충분한 공간을 할당해야 하며 `pcbArgumentInfo` 매개 변수에 크기를 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0447-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0447-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0447-118">Requirements</span></span>  
 <span data-ttu-id="d0447-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0447-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0447-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d0447-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d0447-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0447-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0447-122">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0447-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0447-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0447-123">See also</span></span>

- [<span data-ttu-id="d0447-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d0447-124">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="d0447-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d0447-125">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="d0447-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d0447-126">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="d0447-127">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0447-127">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="d0447-128">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0447-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="d0447-129">프로파일링</span><span class="sxs-lookup"><span data-stu-id="d0447-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
