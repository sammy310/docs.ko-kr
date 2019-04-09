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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7f1b2756dd180cb0a701429978a34ea80447a86
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107642"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="b9b81-102">ICorProfilerCallback::ExceptionCatcherLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="b9b81-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="b9b81-103">컨트롤에서 적절 한 전달 되는 프로파일러에 알립니다 `catch` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b81-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b81-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9b81-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="b9b81-105">설명</span><span class="sxs-lookup"><span data-stu-id="b9b81-105">Remarks</span></span>  
 <span data-ttu-id="b9b81-106">가비지 수집을 허용 하는 상태가 스택의 되었을 수 있으므로이 메서드의 구현에서 프로파일러 차단 되지 않아야 하 고 따라서 preemptive 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b81-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="b9b81-107">프로파일러 여기 차단 하는 경우 가비지 수집을 시도 하 고, 런타임이이 콜백에서 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b81-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="b9b81-108">이 메서드 구현은 프로파일러의 관리 되는 메모리 할당에서 또는 관리 코드를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b81-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9b81-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9b81-109">Requirements</span></span>  
 <span data-ttu-id="b9b81-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9b81-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9b81-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b9b81-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b9b81-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9b81-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b9b81-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b9b81-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b9b81-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="b9b81-114">See also</span></span>

- [<span data-ttu-id="b9b81-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9b81-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="b9b81-116">ExceptionCatcherEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="b9b81-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
