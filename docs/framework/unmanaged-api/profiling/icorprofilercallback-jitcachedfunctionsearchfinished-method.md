---
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
ms.openlocfilehash: ad155c4efb9f11565eeed8bc0a3540311aca4eb7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866275"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="040bd-102">ICorProfilerCallback::JITCachedFunctionSearchFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="040bd-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="040bd-103">네이티브 이미지 생성기 (Ngen.exe)를 사용 하 여 이전에 컴파일된 함수에 대해 검색이 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="040bd-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="040bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="040bd-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a><span data-ttu-id="040bd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="040bd-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="040bd-106">\[in] 검색을 수행한 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="040bd-106">\[in] The ID of the function for which the search was performed.</span></span>

- `result`

  <span data-ttu-id="040bd-107">\[in] 검색 결과를 나타내는 [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="040bd-107">\[in] A value of the [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>

## <a name="remarks"></a><span data-ttu-id="040bd-108">주의</span><span class="sxs-lookup"><span data-stu-id="040bd-108">Remarks</span></span>  
 <span data-ttu-id="040bd-109">.NET Framework 버전 2.0에서는 일반 NGen 이미지의 모든 함수에 대해 [ICorProfilerCallback:: JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) 및 `JITCachedFunctionSearchFinished` 콜백이 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="040bd-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="040bd-110">프로파일러에 대해 최적화 된 NGen 이미지만이 이미지의 모든 함수에 대해 콜백을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="040bd-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="040bd-111">그러나 추가 오버 헤드로 인해 프로파일러는 이러한 콜백을 사용 하 여 함수를 JIT (just-in-time)로 강제 컴파일하는 경우에만 프로파일러 최적화 NGen 이미지를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040bd-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="040bd-112">그렇지 않으면 프로파일러는 함수 정보를 수집 하기 위해 지연 전략을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="040bd-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="040bd-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="040bd-113">Requirements</span></span>  
 <span data-ttu-id="040bd-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="040bd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="040bd-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="040bd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="040bd-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="040bd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="040bd-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="040bd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="040bd-118">참조</span><span class="sxs-lookup"><span data-stu-id="040bd-118">See also</span></span>

- [<span data-ttu-id="040bd-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="040bd-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
