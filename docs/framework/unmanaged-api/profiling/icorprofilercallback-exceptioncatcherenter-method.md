---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionCatcherEnter 메서드'
title: ICorProfilerCallback::ExceptionCatcherEnter 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: f9ea2b44e7a783f9b21f4aa385585dfebc48b1d4
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760524"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="26460-103">ICorProfilerCallback::ExceptionCatcherEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="26460-103">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>

<span data-ttu-id="26460-104">컨트롤이 적절 한 블록에 전달 되 고 있음을 프로파일러에 알립니다 `catch` .</span><span class="sxs-lookup"><span data-stu-id="26460-104">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26460-105">구문</span><span class="sxs-lookup"><span data-stu-id="26460-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26460-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="26460-106">Parameters</span></span>

<span data-ttu-id="26460-107">`functionId` 진행 블록을 포함 하는 함수의 식별자입니다 `catch` .</span><span class="sxs-lookup"><span data-stu-id="26460-107">`functionId` [in] The identifier of the function containing the `catch` block.</span></span>
  
<span data-ttu-id="26460-108">`objectId` 진행 처리 되는 예외의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="26460-108">`objectId` [in] The identifier of the exception being handled.</span></span>

## <a name="remarks"></a><span data-ttu-id="26460-109">설명</span><span class="sxs-lookup"><span data-stu-id="26460-109">Remarks</span></span>  

 <span data-ttu-id="26460-110">`ExceptionCatcherEnter`메서드는 catch 지점이 JIT (just-in-time) 컴파일러를 사용 하 여 컴파일된 코드에 있는 경우에만 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26460-110">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="26460-111">비관리 코드나 런타임의 내부 코드에서 catch 된 예외는이 알림을 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26460-111">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="26460-112">`objectId`이 값은 알림 이후 가비지 수집에서 개체를 이동 했을 수 있으므로 다시 전달 됩니다 `ExceptionThrown` .</span><span class="sxs-lookup"><span data-stu-id="26460-112">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="26460-113">스택은 가비지 수집을 허용 하는 상태가 아닐 수 있으므로 선점형 가비지 수집을 사용 하도록 설정할 수 없기 때문에 프로파일러는이 메서드의 구현에서 차단 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26460-113">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="26460-114">프로파일러가 여기에서 차단 되 고 가비지 수집이 시도 되는 경우이 콜백이 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26460-114">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="26460-115">이 메서드의 프로파일러 구현은 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26460-115">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26460-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="26460-116">Requirements</span></span>  

 <span data-ttu-id="26460-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26460-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26460-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="26460-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="26460-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26460-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26460-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26460-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26460-121">참조</span><span class="sxs-lookup"><span data-stu-id="26460-121">See also</span></span>

- [<span data-ttu-id="26460-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26460-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="26460-123">ExceptionCatcherLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="26460-123">ExceptionCatcherLeave Method</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)
