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
ms.openlocfilehash: 556048be66a7c60dd82a8d51391a86655db6802a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755930"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="89776-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="89776-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="89776-103">예외 처리의 해제 단계 함수 해제 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="89776-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89776-104">구문</span><span class="sxs-lookup"><span data-stu-id="89776-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="89776-105">설명</span><span class="sxs-lookup"><span data-stu-id="89776-105">Remarks</span></span>  
 <span data-ttu-id="89776-106">경우는 `ExceptionUnwindFunctionLeave` 메서드를 호출 스택에서 함수 인스턴스 및 해당 스택 데이터가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89776-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="89776-107">가비지 수집을 허용 하는 상태가 스택의 되었을 수 있으므로이 호출 하는 동안 프로파일러 차단 되지 않아야 하 고 따라서 preemptive 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89776-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="89776-108">이때 프로파일러가 차단 및 가비지 수집을 시도 하는 경우 런타임은이 콜백에서 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89776-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="89776-109">또한이 호출 하는 동안 프로파일러 호출 해서는 안 관리 코드로 또는 관리 되는 메모리 할당에서.</span><span class="sxs-lookup"><span data-stu-id="89776-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89776-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89776-110">Requirements</span></span>  
 <span data-ttu-id="89776-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="89776-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89776-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89776-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89776-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89776-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89776-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89776-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89776-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="89776-115">See also</span></span>

- [<span data-ttu-id="89776-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89776-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="89776-117">ExceptionUnwindFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="89776-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
