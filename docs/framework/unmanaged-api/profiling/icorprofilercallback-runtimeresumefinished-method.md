---
description: '자세히 알아보기: ICorProfilerCallback:: RuntimeResumeFinished 메서드'
title: ICorProfilerCallback::RuntimeResumeFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
ms.openlocfilehash: a8a38ff8372df9890239966c90175d72bda4b09d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788854"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="21bd7-103">ICorProfilerCallback::RuntimeResumeFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="21bd7-103">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>

<span data-ttu-id="21bd7-104">런타임이 모든 런타임 스레드를 다시 시작 하 고 정상 작업으로 반환 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="21bd7-104">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21bd7-105">구문</span><span class="sxs-lookup"><span data-stu-id="21bd7-105">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="21bd7-106">설명</span><span class="sxs-lookup"><span data-stu-id="21bd7-106">Remarks</span></span>  

 <span data-ttu-id="21bd7-107">`RuntimeResumeFinished`콜백은 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) 콜백과 동일한 스레드에서 발생 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21bd7-107">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="21bd7-108">그러나 [ICorProfilerCallback:: Run Esumestarted](icorprofilercallback-runtimeresumestarted-method.md) 콜백과 동일한 스레드에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="21bd7-108">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21bd7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21bd7-109">Requirements</span></span>  

 <span data-ttu-id="21bd7-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21bd7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21bd7-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21bd7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21bd7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21bd7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21bd7-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21bd7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21bd7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21bd7-114">See also</span></span>

- [<span data-ttu-id="21bd7-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21bd7-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
