---
title: ICorProfilerInfo::GetFunctionInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type:
- apiref
ms.openlocfilehash: 0a3ec1a317fbeba2bf792378663e2fe940a8ec10
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439121"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="d2635-102">ICorProfilerInfo::GetFunctionInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="d2635-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="d2635-103">Gets the parent class and metadata token for the specified function.</span><span class="sxs-lookup"><span data-stu-id="d2635-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2635-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2635-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2635-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2635-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d2635-106">[in] The ID of the function for which to get the parent class and metadata token.</span><span class="sxs-lookup"><span data-stu-id="d2635-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="d2635-107">[out] 함수의 부모 클래스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d2635-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="d2635-108">[out] 함수의 부모 클래스가 정의된 모듈에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d2635-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="d2635-109">[out] 함수의 메타데이터 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d2635-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2635-110">주의</span><span class="sxs-lookup"><span data-stu-id="d2635-110">Remarks</span></span>  
 <span data-ttu-id="d2635-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span><span class="sxs-lookup"><span data-stu-id="d2635-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="d2635-112">`pToken`에서 참조하는 위치로 반환되는 메타데이터 토큰을 사용하여 함수에 대한 메타데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2635-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="d2635-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span><span class="sxs-lookup"><span data-stu-id="d2635-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="d2635-114">In this case, `pClassId` will be 0.</span><span class="sxs-lookup"><span data-stu-id="d2635-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="d2635-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span><span class="sxs-lookup"><span data-stu-id="d2635-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2635-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2635-116">Requirements</span></span>  
 <span data-ttu-id="d2635-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2635-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2635-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d2635-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d2635-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2635-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2635-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2635-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2635-121">참조</span><span class="sxs-lookup"><span data-stu-id="d2635-121">See also</span></span>

- [<span data-ttu-id="d2635-122">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2635-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
