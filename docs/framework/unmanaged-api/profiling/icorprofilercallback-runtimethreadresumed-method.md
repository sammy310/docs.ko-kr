---
title: ICorProfilerCallback::RuntimeThreadResumed 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadResumed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 20a34da8f868a34f3d447ac1a5f6a56eb0bdafe1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481418"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="2e32f-102">ICorProfilerCallback::RuntimeThreadResumed 메서드</span><span class="sxs-lookup"><span data-stu-id="2e32f-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="2e32f-103">지정된 된 스레드의 일시 중단 된 후 다시 시작 했습니다는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2e32f-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e32f-104">구문</span><span class="sxs-lookup"><span data-stu-id="2e32f-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e32f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e32f-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="2e32f-106">[in] 다시 시작 되었습니다 하는 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2e32f-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e32f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e32f-107">Requirements</span></span>  
 <span data-ttu-id="2e32f-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2e32f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e32f-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2e32f-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2e32f-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e32f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e32f-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e32f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e32f-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="2e32f-112">See also</span></span>
- [<span data-ttu-id="2e32f-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e32f-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2e32f-114">RuntimeThreadSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="2e32f-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
