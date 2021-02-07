---
description: '자세히 알아보기: ICorProfilerInfo2:: GetCodeInfo2 메서드'
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
ms.openlocfilehash: 69b877b2dfe3bf23cd2b13417386c45d51de44d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760508"
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a><span data-ttu-id="f01d7-103">ICorProfilerInfo2::GetCodeInfo2 메서드</span><span class="sxs-lookup"><span data-stu-id="f01d7-103">ICorProfilerInfo2::GetCodeInfo2 Method</span></span>

<span data-ttu-id="f01d7-104">지정된 `FunctionID`와 연결된 네이티브 코드의 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f01d7-104">Gets the extents of native code associated with the specified `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f01d7-105">구문</span><span class="sxs-lookup"><span data-stu-id="f01d7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo2(  
    [in]  FunctionID functionID,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f01d7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f01d7-106">Parameters</span></span>  

 `functionID`  
 <span data-ttu-id="f01d7-107">[in] 네이티브 코드가 연결된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f01d7-107">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="f01d7-108">[in] `codeInfos` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f01d7-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="f01d7-109">제한이 사용할 수 있는 [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조체의 총 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f01d7-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="f01d7-110">[out] 호출자가 제공한 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="f01d7-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="f01d7-111">메서드가 반환된 후에는 각각 네이티브 코드 블록을 설명하는 `COR_PRF_CODE_INFO` 구조체의 배열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f01d7-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f01d7-112">설명</span><span class="sxs-lookup"><span data-stu-id="f01d7-112">Remarks</span></span>  

 <span data-ttu-id="f01d7-113">범위는 MSIL(Microsoft Intermediate Language) 오프셋의 오름차순으로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="f01d7-113">The extents are sorted in order of increasing Microsoft intermediate language (MSIL) offset.</span></span>  
  
 <span data-ttu-id="f01d7-114">`GetCodeInfo2`가 반환된 후 `codeInfos` 버퍼가 모든 `COR_PRF_CODE_INFO` 구조체를 포함하기에 충분히 큰지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01d7-114">After `GetCodeInfo2` returns, you must verify that the `codeInfos` buffer was large enough to contain all the `COR_PRF_CODE_INFO` structures.</span></span> <span data-ttu-id="f01d7-115">이렇게 하려면 `cCodeInfos` 값을 `cchName` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="f01d7-115">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="f01d7-116">`cCodeInfos`를 `COR_PRF_CODE_INFO` 구조체의 크기로 나눈 값이 `pcCodeInfos`보다 작으면 더 큰 `codeInfos` 버퍼를 할당하고 `cCodeInfos`를 더 큰 새 크기로 업데이트한 다음 `GetCodeInfo2`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f01d7-116">If `cCodeInfos` divided by the size of a `COR_PRF_CODE_INFO` structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo2` again.</span></span>  
  
 <span data-ttu-id="f01d7-117">또는 길이가 0인 `codeInfos` 버퍼로 `GetCodeInfo2`를 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="f01d7-117">Alternatively, you can first call `GetCodeInfo2` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="f01d7-118">그런 다음 `codeInfos` 버퍼 크기를 `pcCodeInfos`에서 반환된 값에 `COR_PRF_CODE_INFO` 구조체의 크기를 곱한 값으로 설정하고 `GetCodeInfo2`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f01d7-118">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a `COR_PRF_CODE_INFO` structure, and call `GetCodeInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f01d7-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f01d7-119">Requirements</span></span>  

 <span data-ttu-id="f01d7-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f01d7-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f01d7-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f01d7-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f01d7-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f01d7-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f01d7-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f01d7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f01d7-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f01d7-124">See also</span></span>

- [<span data-ttu-id="f01d7-125">GetCodeInfo3 메서드</span><span class="sxs-lookup"><span data-stu-id="f01d7-125">GetCodeInfo3 Method</span></span>](icorprofilerinfo4-getcodeinfo3-method.md)
- [<span data-ttu-id="f01d7-126">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f01d7-126">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="f01d7-127">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f01d7-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="f01d7-128">프로파일링</span><span class="sxs-lookup"><span data-stu-id="f01d7-128">Profiling</span></span>](index.md)
