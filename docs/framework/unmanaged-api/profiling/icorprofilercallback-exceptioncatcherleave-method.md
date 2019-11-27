---
title: ICorProfilerCallback::ExceptionCatcherLeave 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherLeave
helpviewer_keywords:
- ExceptionCatcherLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCatcherLeave method [.NET Framework profiling]
ms.assetid: 1f3dbdf5-db0c-4b07-bbb7-375de2a63673
topic_type:
- apiref
ms.openlocfilehash: 7d61a6db8f42398a0d6e0d818605592f4fe71cf7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445001"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="ab574-102">ICorProfilerCallback::ExceptionCatcherLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="ab574-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="ab574-103">제어를 적절 한 `catch` 블록 외부로 전달할지 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ab574-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab574-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab574-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ab574-105">주의</span><span class="sxs-lookup"><span data-stu-id="ab574-105">Remarks</span></span>  
 <span data-ttu-id="ab574-106">스택은 가비지 수집을 허용 하는 상태가 아닐 수 있으므로 선점형 가비지 수집을 사용 하도록 설정할 수 없기 때문에 프로파일러는이 메서드의 구현에서 차단 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab574-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="ab574-107">프로파일러가 여기에서 차단 되 고 가비지 수집이 시도 되는 경우이 콜백이 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab574-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="ab574-108">이 메서드의 프로파일러 구현은 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab574-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab574-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab574-109">Requirements</span></span>  
 <span data-ttu-id="ab574-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab574-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab574-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ab574-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ab574-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab574-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab574-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab574-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab574-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab574-114">See also</span></span>

- [<span data-ttu-id="ab574-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab574-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ab574-116">ExceptionCatcherEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="ab574-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
