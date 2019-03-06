---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1944b84863cea1cfdc464489640a6f78d476537d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482524"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="5f2dc-102">ICorProfilerCallback::FunctionUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="5f2dc-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="5f2dc-103">런타임 함수를 언로드할 시작한는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5f2dc-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f2dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="5f2dc-104">Syntax</span></span>  
  
```  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="5f2dc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f2dc-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="5f2dc-106">[in] 언로드되고 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5f2dc-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f2dc-107">설명</span><span class="sxs-lookup"><span data-stu-id="5f2dc-107">Remarks</span></span>  
 <span data-ttu-id="5f2dc-108">값을 `functionId` 호출자에 게이 메서드가 반환 된 후 매개 변수는 더 이상 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2dc-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f2dc-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f2dc-109">Requirements</span></span>  
 <span data-ttu-id="5f2dc-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f2dc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f2dc-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5f2dc-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f2dc-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f2dc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f2dc-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f2dc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f2dc-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="5f2dc-114">See also</span></span>
- [<span data-ttu-id="5f2dc-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f2dc-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
