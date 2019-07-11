---
title: ICorProfilerInfo2::GetCodeInfo2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetCodeInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetCodeInfo2
helpviewer_keywords:
- ICorProfilerInfo2::GetCodeInfo2 method [.NET Framework profiling]
- GetCodeInfo2 method [.NET Framework profiling]
ms.assetid: 532da6ee-7f0a-401b-a61e-fc47ec235d2e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1acdc5d094fe93118e6cc62774f1cbf47a357dfc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751810"
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a><span data-ttu-id="123a5-102">ICorProfilerInfo2::GetCodeInfo2 메서드</span><span class="sxs-lookup"><span data-stu-id="123a5-102">ICorProfilerInfo2::GetCodeInfo2 Method</span></span>
<span data-ttu-id="123a5-103">지정된 `FunctionID`와 연결된 네이티브 코드의 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="123a5-103">Gets the extents of native code associated with the specified `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="123a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="123a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo2(  
    [in]  FunctionID functionID,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="123a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="123a5-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="123a5-106">[in] 네이티브 코드가 연결된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="123a5-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="123a5-107">[in] `codeInfos` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="123a5-107">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="123a5-108">[out] 총 수에 대 한 포인터 [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) 구조를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="123a5-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="123a5-109">[out] 호출자가 제공한 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="123a5-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="123a5-110">메서드가 반환된 후에는 각각 네이티브 코드 블록을 설명하는 `COR_PRF_CODE_INFO` 구조체의 배열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="123a5-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="123a5-111">설명</span><span class="sxs-lookup"><span data-stu-id="123a5-111">Remarks</span></span>  
 <span data-ttu-id="123a5-112">범위는 MSIL(Microsoft Intermediate Language) 오프셋의 오름차순으로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="123a5-112">The extents are sorted in order of increasing Microsoft intermediate language (MSIL) offset.</span></span>  
  
 <span data-ttu-id="123a5-113">`GetCodeInfo2`가 반환된 후 `codeInfos` 버퍼가 모든 `COR_PRF_CODE_INFO` 구조체를 포함하기에 충분히 큰지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="123a5-113">After `GetCodeInfo2` returns, you must verify that the `codeInfos` buffer was large enough to contain all the `COR_PRF_CODE_INFO` structures.</span></span> <span data-ttu-id="123a5-114">이렇게 하려면 `cCodeInfos` 값을 `cchName` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="123a5-114">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="123a5-115">`cCodeInfos`를 `COR_PRF_CODE_INFO` 구조체의 크기로 나눈 값이 `pcCodeInfos`보다 작으면 더 큰 `codeInfos` 버퍼를 할당하고 `cCodeInfos`를 더 큰 새 크기로 업데이트한 다음 `GetCodeInfo2`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="123a5-115">If `cCodeInfos` divided by the size of a `COR_PRF_CODE_INFO` structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo2` again.</span></span>  
  
 <span data-ttu-id="123a5-116">또는 길이가 0인 `codeInfos` 버퍼로 `GetCodeInfo2`를 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="123a5-116">Alternatively, you can first call `GetCodeInfo2` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="123a5-117">그런 다음 `codeInfos` 버퍼 크기를 `pcCodeInfos`에서 반환된 값에 `COR_PRF_CODE_INFO` 구조체의 크기를 곱한 값으로 설정하고 `GetCodeInfo2`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="123a5-117">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a `COR_PRF_CODE_INFO` structure, and call `GetCodeInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="123a5-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="123a5-118">Requirements</span></span>  
 <span data-ttu-id="123a5-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="123a5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="123a5-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="123a5-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="123a5-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="123a5-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="123a5-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="123a5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123a5-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="123a5-123">See also</span></span>

- [<span data-ttu-id="123a5-124">GetCodeInfo3 메서드</span><span class="sxs-lookup"><span data-stu-id="123a5-124">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)
- [<span data-ttu-id="123a5-125">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="123a5-125">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="123a5-126">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="123a5-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="123a5-127">프로파일링</span><span class="sxs-lookup"><span data-stu-id="123a5-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
