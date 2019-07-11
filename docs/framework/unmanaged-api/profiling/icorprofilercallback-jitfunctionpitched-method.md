---
title: ICorProfilerCallback::JITFunctionPitched 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71df3bc707099cbad06742d964881ee629216b69
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782812"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="cb2bc-102">ICorProfilerCallback::JITFunctionPitched 메서드</span><span class="sxs-lookup"><span data-stu-id="cb2bc-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="cb2bc-103">프로파일러에 알립니다 하는 시간 (JIT) 된 함수-컴파일된 메모리에서 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2bc-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb2bc-104">구문</span><span class="sxs-lookup"><span data-stu-id="cb2bc-104">Syntax</span></span>  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb2bc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb2bc-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="cb2bc-106">[in] 제거 된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="cb2bc-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb2bc-107">설명</span><span class="sxs-lookup"><span data-stu-id="cb2bc-107">Remarks</span></span>  
 <span data-ttu-id="cb2bc-108">제거 함수를 호출 하는 경우 프로파일러는 함수를 다시 컴파일할 때 새 JIT 컴파일 이벤트를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb2bc-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="cb2bc-109">현재는 공용 언어 런타임 (CLR) JIT 컴파일러가 함수를 제거 하지 메모리에서이 콜백은 현재 사용 되지 않습니다 하 고 프로파일러에 의해 수신 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2bc-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="cb2bc-110">변수의 `functionId` 함수가 다시 컴파일될 때까지 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2bc-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="cb2bc-111">함수를 다시 컴파일할 때 동일한 `functionId` 값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb2bc-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb2bc-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb2bc-112">Requirements</span></span>  
 <span data-ttu-id="cb2bc-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cb2bc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb2bc-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb2bc-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb2bc-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb2bc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb2bc-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb2bc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb2bc-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="cb2bc-117">See also</span></span>

- [<span data-ttu-id="cb2bc-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb2bc-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
