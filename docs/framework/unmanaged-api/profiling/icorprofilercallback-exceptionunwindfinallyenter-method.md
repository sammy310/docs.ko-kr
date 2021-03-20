---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionUnwindFinallyEnter 메서드'
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
ms.openlocfilehash: a142aa39f1c601c8c814d2f760cb6414d84b8494
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759445"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="47c2a-103">ICorProfilerCallback::ExceptionUnwindFinallyEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="47c2a-103">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>

<span data-ttu-id="47c2a-104">예외 처리의 해제 단계가 `finally` 지정 된 함수에 포함 된 절을 입력 하 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="47c2a-104">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47c2a-105">구문</span><span class="sxs-lookup"><span data-stu-id="47c2a-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47c2a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47c2a-106">Parameters</span></span>

<span data-ttu-id="47c2a-107">`functionId` 진행 절이 포함 된 함수의 ID입니다 `finally` .</span><span class="sxs-lookup"><span data-stu-id="47c2a-107">`functionId` [in] The ID of the function that contains the `finally` clause.</span></span>

## <a name="remarks"></a><span data-ttu-id="47c2a-108">설명</span><span class="sxs-lookup"><span data-stu-id="47c2a-108">Remarks</span></span>  

 <span data-ttu-id="47c2a-109">스택은 가비지 수집을 허용 하는 상태가 아닐 수 있으므로 선점형 가비지 수집을 사용 하도록 설정할 수 없기 때문에 프로파일러는이 메서드의 구현에서 차단 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47c2a-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="47c2a-110">프로파일러가 여기에서 차단 되 고 가비지 수집이 시도 되는 경우이 콜백이 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47c2a-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="47c2a-111">이 메서드의 프로파일러 구현은 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c2a-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47c2a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47c2a-112">Requirements</span></span>  

 <span data-ttu-id="47c2a-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47c2a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47c2a-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="47c2a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="47c2a-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47c2a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47c2a-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47c2a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c2a-117">참조</span><span class="sxs-lookup"><span data-stu-id="47c2a-117">See also</span></span>

- [<span data-ttu-id="47c2a-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47c2a-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="47c2a-119">GetNotifiedExceptionClauseInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="47c2a-119">GetNotifiedExceptionClauseInfo Method</span></span>](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="47c2a-120">ExceptionUnwindFinallyLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="47c2a-120">ExceptionUnwindFinallyLeave Method</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)
