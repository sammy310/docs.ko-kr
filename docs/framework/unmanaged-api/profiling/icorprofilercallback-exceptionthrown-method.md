---
description: 'ICorProfilerCallback:: ExceptionThrown 메서드에 대해 자세히 알아보세요.'
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
ms.openlocfilehash: aed3d6c4c3c45b546fa8af1db918a6f68eda9bde
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760407"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="1b941-103">ICorProfilerCallback::ExceptionThrown 메서드</span><span class="sxs-lookup"><span data-stu-id="1b941-103">ICorProfilerCallback::ExceptionThrown Method</span></span>

<span data-ttu-id="1b941-104">예외가 throw 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1b941-104">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b941-105">이 함수는 예외가 관리 코드에 도달 하는 경우에만 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b941-105">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b941-106">구문</span><span class="sxs-lookup"><span data-stu-id="1b941-106">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b941-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1b941-107">Parameters</span></span>

<span data-ttu-id="1b941-108">`thrownObjectId` 진행 예외를 throw 한 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1b941-108">`thrownObjectId` [in] The ID of the object that caused the exception to be thrown.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1b941-109">설명</span><span class="sxs-lookup"><span data-stu-id="1b941-109">Remarks</span></span>  

 <span data-ttu-id="1b941-110">스택은 가비지 수집을 허용 하는 상태가 아닐 수 있으므로 선점형 가비지 수집을 사용 하도록 설정할 수 없기 때문에 프로파일러는이 메서드의 구현에서 차단 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b941-110">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="1b941-111">프로파일러가 여기에서 차단 되 고 가비지 수집이 시도 되는 경우이 콜백이 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b941-111">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="1b941-112">이 메서드의 프로파일러 구현은 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b941-112">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b941-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1b941-113">Requirements</span></span>  

 <span data-ttu-id="1b941-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b941-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b941-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1b941-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1b941-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b941-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b941-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b941-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b941-118">참조</span><span class="sxs-lookup"><span data-stu-id="1b941-118">See also</span></span>

- [<span data-ttu-id="1b941-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b941-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
