---
description: '자세히 알아보기: ICorProfilerCallback:: JITCachedFunctionSearchFinished 메서드'
title: ICorProfilerCallback::JITCachedFunctionSearchFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
ms.openlocfilehash: b5025a7d33800047bb6244b82308ba2ab158cea7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705852"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="1c064-103">ICorProfilerCallback::JITCachedFunctionSearchFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="1c064-103">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>

<span data-ttu-id="1c064-104">NGen.exe (네이티브 이미지 생성기)를 사용 하 여 이전에 컴파일된 함수에 대해 검색이 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1c064-104">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c064-105">구문</span><span class="sxs-lookup"><span data-stu-id="1c064-105">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c064-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1c064-106">Parameters</span></span>

- `functionId`

  <span data-ttu-id="1c064-107">\[in] 검색을 수행한 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1c064-107">\[in] The ID of the function for which the search was performed.</span></span>

- `result`

  <span data-ttu-id="1c064-108">\[in] 검색 결과를 나타내는 [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1c064-108">\[in] A value of the [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c064-109">설명</span><span class="sxs-lookup"><span data-stu-id="1c064-109">Remarks</span></span>  

 <span data-ttu-id="1c064-110">.NET Framework 버전 2.0에서는 일반 NGen 이미지의 모든 함수에 대해 [ICorProfilerCallback:: JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) 및 `JITCachedFunctionSearchFinished` 콜백이 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c064-110">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="1c064-111">프로파일러에 대해 최적화 된 NGen 이미지만이 이미지의 모든 함수에 대해 콜백을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c064-111">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="1c064-112">그러나 추가 오버 헤드로 인해 프로파일러는 이러한 콜백을 사용 하 여 함수를 JIT (just-in-time)로 강제 컴파일하는 경우에만 프로파일러 최적화 NGen 이미지를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c064-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="1c064-113">그렇지 않으면 프로파일러는 함수 정보를 수집 하기 위해 지연 전략을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c064-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c064-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c064-114">Requirements</span></span>  

 <span data-ttu-id="1c064-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c064-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c064-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c064-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1c064-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c064-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c064-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c064-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c064-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c064-119">See also</span></span>

- [<span data-ttu-id="1c064-120">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c064-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
