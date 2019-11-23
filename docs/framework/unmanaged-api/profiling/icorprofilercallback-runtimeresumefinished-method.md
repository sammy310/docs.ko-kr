---
title: ICorProfilerCallback::RuntimeResumeFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
ms.openlocfilehash: 81c26214762fba1cac43e42adc1ee9909759972f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430318"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="17c15-102">ICorProfilerCallback::RuntimeResumeFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="17c15-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="17c15-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span><span class="sxs-lookup"><span data-stu-id="17c15-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17c15-104">구문</span><span class="sxs-lookup"><span data-stu-id="17c15-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="17c15-105">주의</span><span class="sxs-lookup"><span data-stu-id="17c15-105">Remarks</span></span>  
 <span data-ttu-id="17c15-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="17c15-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="17c15-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="17c15-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17c15-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="17c15-108">Requirements</span></span>  
 <span data-ttu-id="17c15-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="17c15-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17c15-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="17c15-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="17c15-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17c15-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17c15-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17c15-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17c15-113">참조</span><span class="sxs-lookup"><span data-stu-id="17c15-113">See also</span></span>

- [<span data-ttu-id="17c15-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="17c15-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
