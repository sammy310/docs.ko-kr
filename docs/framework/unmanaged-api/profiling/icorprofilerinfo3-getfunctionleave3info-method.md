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
ms.openlocfilehash: f365a95b0859f4f97dab96ec85af6d7dfb96d8e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721622"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="4fe28-102">ICorProfilerInfo3::GetFunctionLeave3Info 메서드</span><span class="sxs-lookup"><span data-stu-id="4fe28-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>

<span data-ttu-id="4fe28-103">[FunctionLeave3WithInfo 함수](functionleave3withinfo-function.md) 함수를 통해 프로파일러에 보고 하는 함수의 스택 프레임 및 반환 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fe28-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="4fe28-104">이 함수는 `FunctionLeave3WithInfo` 콜백 중에만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fe28-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fe28-105">구문</span><span class="sxs-lookup"><span data-stu-id="4fe28-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fe28-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4fe28-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="4fe28-107">진행 을 `FunctionID` 반환 하는 함수의입니다.</span><span class="sxs-lookup"><span data-stu-id="4fe28-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="4fe28-108">[in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="4fe28-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="4fe28-109">프로파일러는 `eltInfo` [FunctionLeave3WithInfo](functionleave3withinfo-function.md) 함수에 의해 프로파일러에 지정 된 것과 동일한를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fe28-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="4fe28-110">[out] 지정된 스택 프레임에 대한 일반 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="4fe28-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="4fe28-111">이 핸들은 프로파일러가 `GetFunctionLeave3Info` 메서드를 호출한 `FunctionLeave3WithInfo` 콜백 중에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="4fe28-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="4fe28-112">제한이 함수에서 반환 되는 값을 포함 하는 [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4fe28-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="4fe28-113">반환 값 정보에 액세스 하려면 `COR_PRF_ENABLE_FUNCTION_RETVAL` 플래그를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fe28-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="4fe28-114">프로파일러는 [ICorProfilerInfo:: SetEventMask 메서드](icorprofilerinfo-seteventmask-method.md) 를 사용 하 여 이벤트 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fe28-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fe28-115">설명</span><span class="sxs-lookup"><span data-stu-id="4fe28-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fe28-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4fe28-116">Requirements</span></span>  

 <span data-ttu-id="4fe28-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fe28-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fe28-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4fe28-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4fe28-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fe28-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fe28-120">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fe28-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fe28-121">참조</span><span class="sxs-lookup"><span data-stu-id="4fe28-121">See also</span></span>

- [<span data-ttu-id="4fe28-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4fe28-122">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="4fe28-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4fe28-123">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="4fe28-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4fe28-124">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="4fe28-125">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fe28-125">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="4fe28-126">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fe28-126">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="4fe28-127">프로파일링</span><span class="sxs-lookup"><span data-stu-id="4fe28-127">Profiling</span></span>](index.md)
