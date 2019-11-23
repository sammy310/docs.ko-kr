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
ms.openlocfilehash: f57a3ed70267de65daed85305ad7d623b4ca0337
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448023"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="61212-102">ICorProfilerCallback::FunctionUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="61212-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="61212-103">Notifies the profiler that the runtime has started to unload a function.</span><span class="sxs-lookup"><span data-stu-id="61212-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61212-104">구문</span><span class="sxs-lookup"><span data-stu-id="61212-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="61212-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="61212-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="61212-106">[in] The ID of the function that is being unloaded.</span><span class="sxs-lookup"><span data-stu-id="61212-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61212-107">주의</span><span class="sxs-lookup"><span data-stu-id="61212-107">Remarks</span></span>  
 <span data-ttu-id="61212-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span><span class="sxs-lookup"><span data-stu-id="61212-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61212-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61212-109">Requirements</span></span>  
 <span data-ttu-id="61212-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61212-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61212-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="61212-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="61212-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61212-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61212-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61212-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61212-114">참조</span><span class="sxs-lookup"><span data-stu-id="61212-114">See also</span></span>

- [<span data-ttu-id="61212-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61212-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
