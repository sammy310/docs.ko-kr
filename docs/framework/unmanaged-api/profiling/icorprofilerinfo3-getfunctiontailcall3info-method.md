---
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
ms.openlocfilehash: add89fe81fccbd5e6f5ad5d27f0ab3ace489963e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868527"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="a2f86-102">ICorProfilerInfo3::GetFunctionTailcall3Info 메서드</span><span class="sxs-lookup"><span data-stu-id="a2f86-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="a2f86-103">[FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) 함수가 프로파일러에 보고 하는 함수의 스택 프레임을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2f86-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="a2f86-104">이 함수는 `FunctionTailcall3WithInfo` 콜백 중에만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2f86-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2f86-105">구문</span><span class="sxs-lookup"><span data-stu-id="a2f86-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2f86-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a2f86-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a2f86-107">진행 을 반환 하는 함수의 `FunctionID`입니다.</span><span class="sxs-lookup"><span data-stu-id="a2f86-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="a2f86-108">[in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="a2f86-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="a2f86-109">프로파일러는 `FunctionTailcall3WithInfo` 함수를 통해 프로파일러에 지정 된 것과 동일한 `eltInfo`를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2f86-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="a2f86-110">[out] 지정된 스택 프레임에 대한 일반 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="a2f86-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="a2f86-111">이 핸들은 프로파일러가 `GetFunctionTailcall3Info` 메서드를 호출한 `FunctionTailcall3WithInfo` 콜백 중에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="a2f86-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2f86-112">주의</span><span class="sxs-lookup"><span data-stu-id="a2f86-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2f86-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2f86-113">Requirements</span></span>  
 <span data-ttu-id="a2f86-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2f86-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2f86-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a2f86-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a2f86-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2f86-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2f86-117">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2f86-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f86-118">참조</span><span class="sxs-lookup"><span data-stu-id="a2f86-118">See also</span></span>

- [<span data-ttu-id="a2f86-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a2f86-119">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="a2f86-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a2f86-120">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="a2f86-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a2f86-121">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="a2f86-122">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2f86-122">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="a2f86-123">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2f86-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a2f86-124">프로파일링</span><span class="sxs-lookup"><span data-stu-id="a2f86-124">Profiling</span></span>](index.md)
