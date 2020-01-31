---
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
ms.openlocfilehash: 534e0672820cc2509f32765274ad970fda69ec5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866509"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="70e1e-102">ICorProfilerCallback::ExceptionCatcherEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="70e1e-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="70e1e-103">컨트롤이 적절 한 `catch` 블록에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="70e1e-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70e1e-104">구문</span><span class="sxs-lookup"><span data-stu-id="70e1e-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70e1e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70e1e-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="70e1e-106">\[in] `catch` 블록을 포함 하는 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="70e1e-106">\[in] The identifier of the function containing the `catch` block.</span></span>
  
- `objectId`

  <span data-ttu-id="70e1e-107">\[in] 처리 되는 예외의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="70e1e-107">\[in] The identifier of the exception being handled.</span></span>

## <a name="remarks"></a><span data-ttu-id="70e1e-108">주의</span><span class="sxs-lookup"><span data-stu-id="70e1e-108">Remarks</span></span>  
 <span data-ttu-id="70e1e-109">`ExceptionCatcherEnter` 메서드는 catch 지점이 JIT (just-in-time) 컴파일러를 사용 하 여 컴파일된 코드에 있는 경우에만 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e1e-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="70e1e-110">비관리 코드나 런타임의 내부 코드에서 catch 된 예외는이 알림을 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70e1e-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="70e1e-111">`objectId` 값은 `ExceptionThrown` 알림 이후 가비지 수집에서 개체를 이동 했을 수 있으므로 다시 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e1e-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="70e1e-112">스택은 가비지 수집을 허용 하는 상태가 아닐 수 있으므로 선점형 가비지 수집을 사용 하도록 설정할 수 없기 때문에 프로파일러는이 메서드의 구현에서 차단 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e1e-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="70e1e-113">프로파일러가 여기에서 차단 되 고 가비지 수집이 시도 되는 경우이 콜백이 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e1e-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="70e1e-114">이 메서드의 프로파일러 구현은 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e1e-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70e1e-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70e1e-115">Requirements</span></span>  
 <span data-ttu-id="70e1e-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70e1e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70e1e-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70e1e-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="70e1e-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70e1e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70e1e-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70e1e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e1e-120">참조</span><span class="sxs-lookup"><span data-stu-id="70e1e-120">See also</span></span>

- [<span data-ttu-id="70e1e-121">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70e1e-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="70e1e-122">ExceptionCatcherLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="70e1e-122">ExceptionCatcherLeave Method</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)
