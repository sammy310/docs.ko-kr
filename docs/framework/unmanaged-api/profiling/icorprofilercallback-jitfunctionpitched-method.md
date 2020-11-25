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
ms.openlocfilehash: 51fec26837b3c7f0a0328a7b64ff4a02148283da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725515"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="e61d9-102">ICorProfilerCallback::JITFunctionPitched 메서드</span><span class="sxs-lookup"><span data-stu-id="e61d9-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>

<span data-ttu-id="e61d9-103">JIT (just-in-time) 컴파일 된 함수가 메모리에서 제거 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e61d9-104">구문</span><span class="sxs-lookup"><span data-stu-id="e61d9-104">Syntax</span></span>  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e61d9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e61d9-105">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="e61d9-106">진행 제거 된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e61d9-107">설명</span><span class="sxs-lookup"><span data-stu-id="e61d9-107">Remarks</span></span>  

 <span data-ttu-id="e61d9-108">제거 된 함수가 호출 되 면 프로파일러는 함수가 다시 컴파일될 때 새 JIT 컴파일 이벤트를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="e61d9-109">현재 CLR (공용 언어 런타임) JIT 컴파일러는 메모리에서 함수를 제거 하지 않으므로이 콜백은 현재 사용 되지 않으며 프로파일러에서 수신 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="e61d9-110">함수를 다시 `functionId` 컴파일할 때까지 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="e61d9-111">함수가 다시 컴파일되면 동일한 `functionId` 값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e61d9-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e61d9-112">Requirements</span></span>  

 <span data-ttu-id="e61d9-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e61d9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e61d9-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e61d9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e61d9-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e61d9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e61d9-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e61d9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61d9-117">참조</span><span class="sxs-lookup"><span data-stu-id="e61d9-117">See also</span></span>

- [<span data-ttu-id="e61d9-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e61d9-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
