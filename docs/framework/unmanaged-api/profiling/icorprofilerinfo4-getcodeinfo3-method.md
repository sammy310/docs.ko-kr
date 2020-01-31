---
title: ICorProfilerInfo4::GetCodeInfo3 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
ms.openlocfilehash: 164e042ab0f1a275ff07b917658024e22c2d7b0b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862038"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="fe593-102">ICorProfilerInfo4::GetCodeInfo3 메서드</span><span class="sxs-lookup"><span data-stu-id="fe593-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="fe593-103">지정된 함수의 JIT 다시 컴파일된 버전과 연결된 네이티브 코드의 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe593-104">구문</span><span class="sxs-lookup"><span data-stu-id="fe593-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe593-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fe593-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="fe593-106">[in] 네이티브 코드가 연결된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="fe593-107">[in] JIT 다시 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="fe593-108">[in] `codeInfos` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="fe593-109">제한이 사용할 수 있는 [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조체의 총 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="fe593-110">[out] 호출자가 제공한 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="fe593-111">메서드가 반환된 후에는 각각 네이티브 코드 블록을 설명하는 `COR_PRF_CODE_INFO` 구조체의 배열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe593-112">주의</span><span class="sxs-lookup"><span data-stu-id="fe593-112">Remarks</span></span>  
 <span data-ttu-id="fe593-113">`GetCodeInfo3` 메서드는 지정 된 IP 주소를 포함 하는 함수의 JIT 다시 컴파일된 ID를 가져오는 점을 제외 하 고 [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md)와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe593-114">`GetCodeInfo3` 가비지 수집을 트리거할 수 있지만 [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) 는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="fe593-115">자세한 내용은 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](corprof-e-unsupported-call-sequence-hresult.md) HRESULT를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe593-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="fe593-116">범위는 CIL(Common Intermediate Language) 오프셋의 오름차순으로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="fe593-117">`GetCodeInfo3` 반환한 후에는 `codeInfos` 버퍼가 모든 [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조를 포함할 수 있을 만큼 충분히 큰지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="fe593-118">이렇게 하려면 `cCodeInfos` 값을 `cchName` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="fe593-119">[COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조의 크기로 나눈 `cCodeInfos` `pcCodeInfos`보다 작은 경우 더 큰 `codeInfos` 버퍼를 할당 하 고, 더 큰 새 크기를 사용 하 여 `cCodeInfos`를 업데이트 하 고, `GetCodeInfo3`을 다시 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="fe593-120">또는 길이가 0인 `codeInfos` 버퍼로 `GetCodeInfo3`를 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="fe593-121">그런 다음 `codeInfos` 버퍼 크기를 `pcCodeInfos`에서 반환 된 값으로 설정 하 고 [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조의 크기를 곱하여 `GetCodeInfo3`를 다시 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe593-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe593-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe593-122">Requirements</span></span>  
 <span data-ttu-id="fe593-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe593-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe593-124">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fe593-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fe593-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe593-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe593-126">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe593-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe593-127">참조</span><span class="sxs-lookup"><span data-stu-id="fe593-127">See also</span></span>

- [<span data-ttu-id="fe593-128">GetCodeInfo2 메서드</span><span class="sxs-lookup"><span data-stu-id="fe593-128">GetCodeInfo2 Method</span></span>](icorprofilerinfo2-getcodeinfo2-method.md)
- [<span data-ttu-id="fe593-129">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe593-129">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="fe593-130">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe593-130">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="fe593-131">프로파일링</span><span class="sxs-lookup"><span data-stu-id="fe593-131">Profiling</span></span>](index.md)
