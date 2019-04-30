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
ms.openlocfilehash: 810875d1b91265fe886ce3cd11970cad7fee122d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041771"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="06c07-102">ICorProfilerCallback::RuntimeThreadResumed 메서드</span><span class="sxs-lookup"><span data-stu-id="06c07-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="06c07-103">지정된 된 스레드의 일시 중단 된 후 다시 시작 했습니다는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="06c07-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06c07-104">구문</span><span class="sxs-lookup"><span data-stu-id="06c07-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06c07-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06c07-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="06c07-106">[in] 다시 시작 되었습니다 하는 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="06c07-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06c07-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06c07-107">Requirements</span></span>  
 <span data-ttu-id="06c07-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="06c07-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06c07-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06c07-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06c07-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06c07-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06c07-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06c07-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c07-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="06c07-112">See also</span></span>

- [<span data-ttu-id="06c07-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06c07-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="06c07-114">RuntimeThreadSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="06c07-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
