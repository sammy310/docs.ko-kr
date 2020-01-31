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
ms.openlocfilehash: 5cafbca75992a5fe8a7d3d95628e0018f1a2e8fa
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865950"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="a6bef-102">ICorProfilerCallback::RuntimeResumeFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="a6bef-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="a6bef-103">런타임이 모든 런타임 스레드를 다시 시작 하 고 정상 작업으로 반환 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a6bef-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6bef-104">구문</span><span class="sxs-lookup"><span data-stu-id="a6bef-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a6bef-105">주의</span><span class="sxs-lookup"><span data-stu-id="a6bef-105">Remarks</span></span>  
 <span data-ttu-id="a6bef-106">`RuntimeResumeFinished` 콜백은 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) 콜백과 동일한 스레드에서 수행 되는 것이 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6bef-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="a6bef-107">그러나 [ICorProfilerCallback:: Run Esumestarted](icorprofilercallback-runtimeresumestarted-method.md) 콜백과 동일한 스레드에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6bef-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6bef-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6bef-108">Requirements</span></span>  
 <span data-ttu-id="a6bef-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6bef-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6bef-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6bef-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6bef-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6bef-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6bef-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6bef-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6bef-113">참조</span><span class="sxs-lookup"><span data-stu-id="a6bef-113">See also</span></span>

- [<span data-ttu-id="a6bef-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6bef-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
