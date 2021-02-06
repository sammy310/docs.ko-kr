---
description: '자세히 알아보기: ICorProfilerInfo3:: GetFunctionEnter3Info 메서드'
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
ms.openlocfilehash: 3e6c0cfbf2518301e62ed5c57e956190066504ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646818"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="fa5f2-103">ICorProfilerInfo3::GetFunctionEnter3Info 메서드</span><span class="sxs-lookup"><span data-stu-id="fa5f2-103">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>

<span data-ttu-id="fa5f2-104">[FunctionEnter3WithInfo](functionenter3withinfo-function.md) 함수에서 프로파일러에 보고 하는 함수의 스택 프레임 및 인수 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-104">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="fa5f2-105">이 함수는 `FunctionEnter3WithInfo` 콜백 중에만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-105">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa5f2-106">구문</span><span class="sxs-lookup"><span data-stu-id="fa5f2-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa5f2-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fa5f2-107">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="fa5f2-108">[in] 입력 중인 함수의 `FunctionID`입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-108">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="fa5f2-109">[in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-109">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="fa5f2-110">프로파일러는 FunctionEnter3WithInfo 함수에 지정 된 것과 동일한를 제공 해야 합니다 `eltInfo` . [](functionenter3withinfo-function.md)</span><span class="sxs-lookup"><span data-stu-id="fa5f2-110">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="fa5f2-111">[out] 지정된 스택 프레임에 대한 일반 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-111">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="fa5f2-112">이 핸들은 프로파일러가 `GetFunctionEnter3Info` 메서드를 호출한 `FunctionEnter3WithInfo` 콜백 중에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-112">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="fa5f2-113">[in, out] [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) 구조체의 총 크기 (바이트)와이 가리키는 인수 범위의 추가 [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) 구조체에 대 한 포인터 `pArgumentInfo` 입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-113">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="fa5f2-114">지정된 크기가 충분하지 않으면 ERROR_INSUFFICIENT_BUFFER가 반환되고 예상 크기가 `pcbArgumentInfo`에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-114">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="fa5f2-115">단순히 `*pcbArgumentInfo`의 예상 값을 검색하기 위해 `GetFunctionEnter3Info`를 호출하려면 `*pcbArgumentInfo`=0 및 `pArgumentInfo`=NULL을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-115">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="fa5f2-116">제한이 메모리의 함수 인수 위치를 왼쪽에서 오른쪽 순서로 설명 하는 [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-116">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa5f2-117">설명</span><span class="sxs-lookup"><span data-stu-id="fa5f2-117">Remarks</span></span>  

 <span data-ttu-id="fa5f2-118">프로파일러는 검사되는 함수의 `COR_PRF_FUNCTION_ARGUMENT_INFO` 구조체에 대해 충분한 공간을 할당해야 하며 `pcbArgumentInfo` 매개 변수에 크기를 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-118">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa5f2-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa5f2-119">Requirements</span></span>  

 <span data-ttu-id="fa5f2-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa5f2-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa5f2-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa5f2-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa5f2-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa5f2-123">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa5f2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa5f2-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa5f2-124">See also</span></span>

- [<span data-ttu-id="fa5f2-125">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fa5f2-125">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="fa5f2-126">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fa5f2-126">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="fa5f2-127">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fa5f2-127">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="fa5f2-128">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa5f2-128">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="fa5f2-129">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa5f2-129">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="fa5f2-130">프로파일링</span><span class="sxs-lookup"><span data-stu-id="fa5f2-130">Profiling</span></span>](index.md)
