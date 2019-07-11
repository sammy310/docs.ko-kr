---
title: ICorProfilerCallback::ExceptionThrown 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionThrown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb95c11900b84b78a3f862bcb73f0700aaabeeaa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755982"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="1a66c-102">ICorProfilerCallback::ExceptionThrown 메서드</span><span class="sxs-lookup"><span data-stu-id="1a66c-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="1a66c-103">예외가 throw 되는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1a66c-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a66c-104">이 함수는 예외에는 관리 코드에 도달 하는 경우에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a66c-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a66c-105">구문</span><span class="sxs-lookup"><span data-stu-id="1a66c-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a66c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a66c-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="1a66c-107">[in] 예외를 throw 시킨 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1a66c-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a66c-108">설명</span><span class="sxs-lookup"><span data-stu-id="1a66c-108">Remarks</span></span>  
 <span data-ttu-id="1a66c-109">가비지 수집을 허용 하는 상태가 스택의 되었을 수 있으므로이 메서드의 구현에서 프로파일러 차단 되지 않아야 하 고 따라서 preemptive 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a66c-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="1a66c-110">프로파일러 여기 차단 하는 경우 가비지 수집을 시도 하 고, 런타임이이 콜백에서 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a66c-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="1a66c-111">이 메서드 구현은 프로파일러의 관리 되는 메모리 할당에서 또는 관리 코드를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a66c-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a66c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a66c-112">Requirements</span></span>  
 <span data-ttu-id="1a66c-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1a66c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a66c-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1a66c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1a66c-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a66c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a66c-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a66c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a66c-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="1a66c-117">See also</span></span>

- [<span data-ttu-id="1a66c-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a66c-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
