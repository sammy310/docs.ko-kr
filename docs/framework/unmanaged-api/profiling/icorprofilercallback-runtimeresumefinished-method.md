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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c7b3c3ea5e976645c265b34327caa38ef6a28fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914799"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="34b0a-102">ICorProfilerCallback::RuntimeResumeFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="34b0a-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="34b0a-103">모든 런타임 스레드를 다시 시작 했습니다 런타임과 정상 작업 상태로 반환 되는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="34b0a-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34b0a-104">구문</span><span class="sxs-lookup"><span data-stu-id="34b0a-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="34b0a-105">설명</span><span class="sxs-lookup"><span data-stu-id="34b0a-105">Remarks</span></span>  
 <span data-ttu-id="34b0a-106">`RuntimeResumeFinished` 콜백 보장 되지 않습니다 동일한 스레드에서 발생 합니다 [icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="34b0a-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="34b0a-107">그러나 반드시 동일한 스레드에서 발생 합니다 [icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="34b0a-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34b0a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34b0a-108">Requirements</span></span>  
 <span data-ttu-id="34b0a-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="34b0a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34b0a-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="34b0a-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="34b0a-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34b0a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34b0a-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34b0a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34b0a-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="34b0a-113">See also</span></span>

- [<span data-ttu-id="34b0a-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34b0a-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
