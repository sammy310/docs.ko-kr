---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionUnwindFunctionEnter 메서드'
title: ICorProfilerCallback::ExceptionUnwindFunctionEnter 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter method [.NET Framework profiling]
- ExceptionUnwindFunctionEnter method [.NET Framework profiling]
ms.assetid: ea3dc625-5650-4bf4-8e67-01e42be065b1
topic_type:
- apiref
ms.openlocfilehash: 3f0376e01263290596aa722b37f6a796ab919139
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706021"
---
# <a name="icorprofilercallbackexceptionunwindfunctionenter-method"></a><span data-ttu-id="8f6a6-103">ICorProfilerCallback::ExceptionUnwindFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="8f6a6-103">ICorProfilerCallback::ExceptionUnwindFunctionEnter Method</span></span>

<span data-ttu-id="8f6a6-104">예외 처리의 해제 단계가 함수 해제를 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8f6a6-104">Notifies the profiler that the unwind phase of exception handling has begun to unwind a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f6a6-105">구문</span><span class="sxs-lookup"><span data-stu-id="8f6a6-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f6a6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f6a6-106">Parameters</span></span>

- `functionId`

  <span data-ttu-id="8f6a6-107">\[in] 해제할 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8f6a6-107">\[in] The ID of the function that is being unwound.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f6a6-108">설명</span><span class="sxs-lookup"><span data-stu-id="8f6a6-108">Remarks</span></span>  

 <span data-ttu-id="8f6a6-109">스택은 가비지 수집을 허용 하는 상태가 아닐 수 있으므로 선점형 가비지 수집을 사용 하도록 설정할 수 없기 때문에 프로파일러는이 메서드의 구현에서 차단 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f6a6-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="8f6a6-110">프로파일러가 여기에서 차단 되 고 가비지 수집이 시도 되는 경우이 콜백이 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f6a6-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="8f6a6-111">이 메서드의 프로파일러 구현은 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f6a6-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f6a6-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f6a6-112">Requirements</span></span>  

 <span data-ttu-id="8f6a6-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f6a6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f6a6-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f6a6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8f6a6-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f6a6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f6a6-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f6a6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f6a6-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f6a6-117">See also</span></span>

- [<span data-ttu-id="8f6a6-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f6a6-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="8f6a6-119">ExceptionUnwindFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="8f6a6-119">ExceptionUnwindFunctionLeave Method</span></span>](icorprofilercallback-exceptionunwindfunctionleave-method.md)
