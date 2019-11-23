---
title: ICorProfilerCallback::ExceptionUnwindFinallyEnter 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type:
- apiref
ms.openlocfilehash: 1f16add7b5a9d18e0c1eb33209b609e9bf7e18b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445316"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="aed83-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="aed83-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="aed83-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span><span class="sxs-lookup"><span data-stu-id="aed83-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aed83-104">구문</span><span class="sxs-lookup"><span data-stu-id="aed83-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aed83-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aed83-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="aed83-106">[in] The ID of the function that contains the `finally` clause.</span><span class="sxs-lookup"><span data-stu-id="aed83-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aed83-107">주의</span><span class="sxs-lookup"><span data-stu-id="aed83-107">Remarks</span></span>  
 <span data-ttu-id="aed83-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span><span class="sxs-lookup"><span data-stu-id="aed83-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="aed83-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span><span class="sxs-lookup"><span data-stu-id="aed83-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="aed83-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span><span class="sxs-lookup"><span data-stu-id="aed83-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aed83-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aed83-111">Requirements</span></span>  
 <span data-ttu-id="aed83-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aed83-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aed83-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aed83-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aed83-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aed83-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aed83-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aed83-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aed83-116">참조</span><span class="sxs-lookup"><span data-stu-id="aed83-116">See also</span></span>

- [<span data-ttu-id="aed83-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aed83-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="aed83-118">GetNotifiedExceptionClauseInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="aed83-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="aed83-119">ExceptionUnwindFinallyLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="aed83-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
