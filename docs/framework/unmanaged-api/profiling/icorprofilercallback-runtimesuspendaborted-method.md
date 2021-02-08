---
description: '자세히 알아보기: ICorProfilerCallback:: RuntimeSuspendAborted 메서드'
title: ICorProfilerCallback::RuntimeSuspendAborted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
ms.openlocfilehash: 892de7ce0b4537f5526a58b6e70f66cd295be2df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788828"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="682f4-103">ICorProfilerCallback::RuntimeSuspendAborted 메서드</span><span class="sxs-lookup"><span data-stu-id="682f4-103">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>

<span data-ttu-id="682f4-104">런타임에서 발생 한 런타임 일시 중단이 중단 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="682f4-104">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="682f4-105">구문</span><span class="sxs-lookup"><span data-stu-id="682f4-105">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="682f4-106">설명</span><span class="sxs-lookup"><span data-stu-id="682f4-106">Remarks</span></span>  

 <span data-ttu-id="682f4-107">두 스레드가 동시에 런타임을 일시 중단 하려고 하면 런타임 일시 중단이 중단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="682f4-107">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="682f4-108">[ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback 또는 `RuntimeSuspendAborted` 콜백은 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback 다음에 나오는 단일 스레드에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="682f4-108">Either the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="682f4-109">콜백은 `RuntimeSuspendAborted` 콜백과 동일한 스레드에서 수행 됩니다 `RuntimeSuspendStarted` .</span><span class="sxs-lookup"><span data-stu-id="682f4-109">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="682f4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="682f4-110">Requirements</span></span>  

 <span data-ttu-id="682f4-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="682f4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="682f4-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="682f4-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="682f4-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="682f4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="682f4-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="682f4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="682f4-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="682f4-115">See also</span></span>

- [<span data-ttu-id="682f4-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="682f4-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
