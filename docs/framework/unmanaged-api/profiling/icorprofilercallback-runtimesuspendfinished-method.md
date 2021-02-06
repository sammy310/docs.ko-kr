---
description: '자세히 알아보기: ICorProfilerCallback:: RuntimeSuspendFinished 메서드'
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
ms.openlocfilehash: eab7111f28c77f1440c0e392a36fb2b083c138e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657530"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="a34e0-103">ICorProfilerCallback::RuntimeSuspendFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="a34e0-103">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>

<span data-ttu-id="a34e0-104">런타임이 모든 런타임 스레드의 일시 중단을 완료 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a34e0-104">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a34e0-105">구문</span><span class="sxs-lookup"><span data-stu-id="a34e0-105">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a34e0-106">설명</span><span class="sxs-lookup"><span data-stu-id="a34e0-106">Remarks</span></span>  

 <span data-ttu-id="a34e0-107">비관리 코드에 있는 모든 런타임 스레드는 런타임을 다시 시작 하려고 할 때까지 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a34e0-107">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="a34e0-108">이 시점에서 런타임이 재개 될 때까지 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a34e0-108">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="a34e0-109">이는 런타임에 입력 하는 새 스레드에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a34e0-109">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="a34e0-110">런타임의 모든 스레드는 이미 인터럽트 가능 코드에 있는 경우 즉시 일시 중단 되거나, 인터럽트가 가능한 코드에 도달할 때 일시 중단 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a34e0-110">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="a34e0-111">`RuntimeSuspendFinished`콜백은 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) 콜백과 동일한 스레드에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a34e0-111">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a34e0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a34e0-112">Requirements</span></span>  

 <span data-ttu-id="a34e0-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a34e0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a34e0-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a34e0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a34e0-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a34e0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a34e0-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a34e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a34e0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a34e0-117">See also</span></span>

- [<span data-ttu-id="a34e0-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a34e0-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a34e0-119">RuntimeSuspendAborted 메서드</span><span class="sxs-lookup"><span data-stu-id="a34e0-119">RuntimeSuspendAborted Method</span></span>](icorprofilercallback-runtimesuspendaborted-method.md)
