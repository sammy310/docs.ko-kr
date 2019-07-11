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
ms.openlocfilehash: b6dd7792fe298aa1950b23053a7c5cd576b62e7b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755885"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="c8a3d-102">ICorProfilerCallback::FunctionUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="c8a3d-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="c8a3d-103">런타임 함수를 언로드할 시작한는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c8a3d-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8a3d-104">구문</span><span class="sxs-lookup"><span data-stu-id="c8a3d-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="c8a3d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8a3d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c8a3d-106">[in] 언로드되고 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8a3d-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8a3d-107">설명</span><span class="sxs-lookup"><span data-stu-id="c8a3d-107">Remarks</span></span>  
 <span data-ttu-id="c8a3d-108">값을 `functionId` 호출자에 게이 메서드가 반환 된 후 매개 변수는 더 이상 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a3d-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8a3d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8a3d-109">Requirements</span></span>  
 <span data-ttu-id="c8a3d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8a3d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8a3d-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c8a3d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c8a3d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8a3d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8a3d-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8a3d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8a3d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8a3d-114">See also</span></span>

- [<span data-ttu-id="c8a3d-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8a3d-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
