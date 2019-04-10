---
title: ICorProfilerCallback::ExceptionUnwindFunctionLeave 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 305c8c7abf778ea68efe06f3bdb57af001ea1b9a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227725"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="1649b-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="1649b-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="1649b-103">예외 처리의 해제 단계 함수 해제 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1649b-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1649b-104">구문</span><span class="sxs-lookup"><span data-stu-id="1649b-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1649b-105">설명</span><span class="sxs-lookup"><span data-stu-id="1649b-105">Remarks</span></span>  
 <span data-ttu-id="1649b-106">경우는 `ExceptionUnwindFunctionLeave` 메서드를 호출 스택에서 함수 인스턴스 및 해당 스택 데이터가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1649b-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="1649b-107">가비지 수집을 허용 하는 상태가 스택의 되었을 수 있으므로이 호출 하는 동안 프로파일러 차단 되지 않아야 하 고 따라서 preemptive 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1649b-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="1649b-108">이때 프로파일러가 차단 및 가비지 수집을 시도 하는 경우 런타임은이 콜백에서 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1649b-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="1649b-109">또한이 호출 하는 동안 프로파일러 호출 해서는 안 관리 코드로 또는 관리 되는 메모리 할당에서.</span><span class="sxs-lookup"><span data-stu-id="1649b-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1649b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1649b-110">Requirements</span></span>  
 <span data-ttu-id="1649b-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1649b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1649b-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1649b-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1649b-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1649b-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1649b-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="1649b-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1649b-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="1649b-115">See also</span></span>

- [<span data-ttu-id="1649b-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1649b-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="1649b-117">ExceptionUnwindFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="1649b-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
