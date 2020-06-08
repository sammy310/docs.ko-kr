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
ms.openlocfilehash: 8bc97bb0d36a046353587a95aa2b79eff12866e0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499885"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="9a04d-102">ICorProfilerCallback::RuntimeResumeFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="9a04d-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="9a04d-103">런타임이 모든 런타임 스레드를 다시 시작 하 고 정상 작업으로 반환 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9a04d-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a04d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a04d-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9a04d-105">설명</span><span class="sxs-lookup"><span data-stu-id="9a04d-105">Remarks</span></span>  
 <span data-ttu-id="9a04d-106">`RuntimeResumeFinished`콜백은 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) 콜백과 동일한 스레드에서 발생 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a04d-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="9a04d-107">그러나 [ICorProfilerCallback:: Run Esumestarted](icorprofilercallback-runtimeresumestarted-method.md) 콜백과 동일한 스레드에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a04d-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a04d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a04d-108">Requirements</span></span>  
 <span data-ttu-id="9a04d-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a04d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a04d-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9a04d-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a04d-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a04d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a04d-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a04d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a04d-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a04d-113">See also</span></span>

- [<span data-ttu-id="9a04d-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a04d-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
