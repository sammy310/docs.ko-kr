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
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="bdf1a-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="bdf1a-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="bdf1a-103">예외 처리의 해제 단계가 지정 된 함수에 포함 된 `finally` 절을 입력 함을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="bdf1a-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf1a-104">구문</span><span class="sxs-lookup"><span data-stu-id="bdf1a-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdf1a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bdf1a-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="bdf1a-106">진행 `finally` 절을 포함 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bdf1a-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdf1a-107">주의</span><span class="sxs-lookup"><span data-stu-id="bdf1a-107">Remarks</span></span>  
 <span data-ttu-id="bdf1a-108">스택은 가비지 수집을 허용 하는 상태가 아닐 수 있으므로 선점형 가비지 수집을 사용 하도록 설정할 수 없기 때문에 프로파일러는이 메서드의 구현에서 차단 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdf1a-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="bdf1a-109">프로파일러가 여기에서 차단 되 고 가비지 수집이 시도 되는 경우이 콜백이 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdf1a-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="bdf1a-110">이 메서드의 프로파일러 구현은 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf1a-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdf1a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bdf1a-111">Requirements</span></span>  
 <span data-ttu-id="bdf1a-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdf1a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdf1a-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bdf1a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bdf1a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdf1a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdf1a-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdf1a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf1a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdf1a-116">See also</span></span>

- [<span data-ttu-id="bdf1a-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bdf1a-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="bdf1a-118">GetNotifiedExceptionClauseInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="bdf1a-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="bdf1a-119">ExceptionUnwindFinallyLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="bdf1a-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
