---
title: ICorProfilerCallback::RuntimeSuspendFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
ms.openlocfilehash: 17dd0cc8d26c328bf6128795f02d751b7ae9e471
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717259"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="4ea6a-102">ICorProfilerCallback::RuntimeSuspendFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="4ea6a-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>

<span data-ttu-id="4ea6a-103">런타임이 모든 런타임 스레드의 일시 중단을 완료 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4ea6a-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ea6a-104">구문</span><span class="sxs-lookup"><span data-stu-id="4ea6a-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4ea6a-105">설명</span><span class="sxs-lookup"><span data-stu-id="4ea6a-105">Remarks</span></span>  

 <span data-ttu-id="4ea6a-106">비관리 코드에 있는 모든 런타임 스레드는 런타임을 다시 시작 하려고 할 때까지 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea6a-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="4ea6a-107">이 시점에서 런타임이 재개 될 때까지 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea6a-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="4ea6a-108">이는 런타임에 입력 하는 새 스레드에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea6a-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="4ea6a-109">런타임의 모든 스레드는 이미 인터럽트 가능 코드에 있는 경우 즉시 일시 중단 되거나, 인터럽트가 가능한 코드에 도달할 때 일시 중단 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea6a-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="4ea6a-110">`RuntimeSuspendFinished`콜백은 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) 콜백과 동일한 스레드에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea6a-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ea6a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ea6a-111">Requirements</span></span>  

 <span data-ttu-id="4ea6a-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ea6a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ea6a-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ea6a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ea6a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ea6a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ea6a-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ea6a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ea6a-116">참조</span><span class="sxs-lookup"><span data-stu-id="4ea6a-116">See also</span></span>

- [<span data-ttu-id="4ea6a-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ea6a-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4ea6a-118">RuntimeSuspendAborted 메서드</span><span class="sxs-lookup"><span data-stu-id="4ea6a-118">RuntimeSuspendAborted Method</span></span>](icorprofilercallback-runtimesuspendaborted-method.md)
