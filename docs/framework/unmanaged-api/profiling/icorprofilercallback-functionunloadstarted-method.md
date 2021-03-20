---
description: '자세히 알아보기: ICorProfilerCallback:: FunctionUnloadStarted 메서드'
title: ICorProfilerCallback::FunctionUnloadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: ce3cf406b8d2f91613bce878db8a4f9e0838c052
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760433"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="6b4a1-103">ICorProfilerCallback::FunctionUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="6b4a1-103">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>

<span data-ttu-id="6b4a1-104">런타임이 함수 언로드를 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6b4a1-104">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b4a1-105">구문</span><span class="sxs-lookup"><span data-stu-id="6b4a1-105">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="6b4a1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6b4a1-106">Parameters</span></span>

<span data-ttu-id="6b4a1-107">`functionId` 진행 언로드될 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6b4a1-107">`functionId` [in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b4a1-108">설명</span><span class="sxs-lookup"><span data-stu-id="6b4a1-108">Remarks</span></span>  

 <span data-ttu-id="6b4a1-109">`functionId`이 메서드가 호출자에 반환 된 후에는 매개 변수 값이 더 이상 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b4a1-109">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b4a1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b4a1-110">Requirements</span></span>  

 <span data-ttu-id="6b4a1-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b4a1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b4a1-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6b4a1-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6b4a1-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b4a1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b4a1-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b4a1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b4a1-115">참조</span><span class="sxs-lookup"><span data-stu-id="6b4a1-115">See also</span></span>

- [<span data-ttu-id="6b4a1-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b4a1-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
