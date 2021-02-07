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
ms.openlocfilehash: 3dd5d46a224c0c51dfee251cf5d0c6ae9320b630
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705962"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="e5556-103">ICorProfilerCallback::FunctionUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="e5556-103">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>

<span data-ttu-id="e5556-104">런타임이 함수 언로드를 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e5556-104">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5556-105">구문</span><span class="sxs-lookup"><span data-stu-id="e5556-105">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="e5556-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5556-106">Parameters</span></span>

- `functionId`

  <span data-ttu-id="e5556-107">\[in] 언로드되고 있는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e5556-107">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5556-108">설명</span><span class="sxs-lookup"><span data-stu-id="e5556-108">Remarks</span></span>  

 <span data-ttu-id="e5556-109">`functionId`이 메서드가 호출자에 반환 된 후에는 매개 변수 값이 더 이상 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5556-109">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5556-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5556-110">Requirements</span></span>  

 <span data-ttu-id="e5556-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5556-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5556-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e5556-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e5556-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5556-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5556-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5556-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5556-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5556-115">See also</span></span>

- [<span data-ttu-id="e5556-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5556-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
