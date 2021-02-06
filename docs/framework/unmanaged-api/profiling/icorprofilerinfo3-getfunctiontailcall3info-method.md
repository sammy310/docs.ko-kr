---
description: '자세히 알아보기: ICorProfilerInfo3:: GetFunctionTailcall3Info 메서드'
title: ICorProfilerInfo3::GetFunctionTailcall3Info 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
ms.openlocfilehash: a8976a11cf7a2c556afa62a559e3a294d81b9a1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646805"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="fed40-103">ICorProfilerInfo3::GetFunctionTailcall3Info 메서드</span><span class="sxs-lookup"><span data-stu-id="fed40-103">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>

<span data-ttu-id="fed40-104">[FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) 함수가 프로파일러에 보고 하는 함수의 스택 프레임을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fed40-104">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="fed40-105">이 함수는 `FunctionTailcall3WithInfo` 콜백 중에만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed40-105">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed40-106">구문</span><span class="sxs-lookup"><span data-stu-id="fed40-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fed40-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fed40-107">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="fed40-108">진행 을 `FunctionID` 반환 하는 함수의입니다.</span><span class="sxs-lookup"><span data-stu-id="fed40-108">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="fed40-109">[in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="fed40-109">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="fed40-110">프로파일러는 `eltInfo` 함수에 의해 프로파일러에 지정 된 것과 동일한를 제공 해야 합니다 `FunctionTailcall3WithInfo` .</span><span class="sxs-lookup"><span data-stu-id="fed40-110">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="fed40-111">[out] 지정된 스택 프레임에 대한 일반 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="fed40-111">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="fed40-112">이 핸들은 프로파일러가 `GetFunctionTailcall3Info` 메서드를 호출한 `FunctionTailcall3WithInfo` 콜백 중에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="fed40-112">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fed40-113">설명</span><span class="sxs-lookup"><span data-stu-id="fed40-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fed40-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fed40-114">Requirements</span></span>  

 <span data-ttu-id="fed40-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fed40-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fed40-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fed40-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fed40-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fed40-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fed40-118">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fed40-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed40-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fed40-119">See also</span></span>

- [<span data-ttu-id="fed40-120">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fed40-120">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="fed40-121">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fed40-121">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="fed40-122">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fed40-122">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="fed40-123">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fed40-123">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="fed40-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fed40-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="fed40-125">프로파일링</span><span class="sxs-lookup"><span data-stu-id="fed40-125">Profiling</span></span>](index.md)
