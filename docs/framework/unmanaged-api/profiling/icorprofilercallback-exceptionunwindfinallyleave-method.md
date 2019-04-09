---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ba62ab2c4df73b570fb1c76adaee44a2a2ce8c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117808"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="bbc5d-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="bbc5d-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="bbc5d-103">해제 단계 예외 처리에 남아 있는 프로파일러에 알립니다는 `finally` 절.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbc5d-104">구문</span><span class="sxs-lookup"><span data-stu-id="bbc5d-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="bbc5d-105">설명</span><span class="sxs-lookup"><span data-stu-id="bbc5d-105">Remarks</span></span>  
 <span data-ttu-id="bbc5d-106">가비지 수집을 허용 하는 상태가 스택의 되었을 수 있으므로이 호출 하는 동안 프로파일러 차단 되지 않아야 하 고 따라서 preemptive 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="bbc5d-107">이때 프로파일러가 차단 및 가비지 수집을 시도 하는 경우 런타임은이 콜백에서 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="bbc5d-108">또한이 호출 하는 동안 프로파일러 호출 해서는 안 관리 코드로 또는 관리 되는 메모리 할당에서.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbc5d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bbc5d-109">Requirements</span></span>  
 <span data-ttu-id="bbc5d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbc5d-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bbc5d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bbc5d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbc5d-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bbc5d-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="bbc5d-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bbc5d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="bbc5d-114">See also</span></span>

- [<span data-ttu-id="bbc5d-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bbc5d-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="bbc5d-116">ExceptionUnwindFinallyEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="bbc5d-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
