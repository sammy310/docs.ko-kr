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
ms.openlocfilehash: 89e4d046deced4294edb98d55e4816f00480fe19
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790071"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="accf9-102">ICorProfilerCallback::FunctionUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="accf9-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="accf9-103">런타임이 함수 언로드를 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="accf9-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="accf9-104">구문</span><span class="sxs-lookup"><span data-stu-id="accf9-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="accf9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="accf9-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="accf9-106">\[in] 언로드되고 있는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="accf9-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="accf9-107">주의</span><span class="sxs-lookup"><span data-stu-id="accf9-107">Remarks</span></span>  
 <span data-ttu-id="accf9-108">이 메서드가 호출자에 게 반환 된 후에는 `functionId` 매개 변수의 값이 더 이상 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="accf9-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="accf9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="accf9-109">Requirements</span></span>  
 <span data-ttu-id="accf9-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="accf9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="accf9-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="accf9-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="accf9-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="accf9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="accf9-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="accf9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="accf9-114">참조</span><span class="sxs-lookup"><span data-stu-id="accf9-114">See also</span></span>

- [<span data-ttu-id="accf9-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="accf9-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
