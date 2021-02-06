---
description: '자세히 알아보기: ICorProfilerCallback:: RuntimeThreadResumed 메서드'
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
ms.openlocfilehash: a01be057bb442c69890d3b1cb4ebe1f861d2518c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657348"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="9b64e-103">ICorProfilerCallback::RuntimeThreadResumed 메서드</span><span class="sxs-lookup"><span data-stu-id="9b64e-103">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>

<span data-ttu-id="9b64e-104">지정 된 스레드가 일시 중단 된 후 다시 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9b64e-104">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b64e-105">구문</span><span class="sxs-lookup"><span data-stu-id="9b64e-105">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b64e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b64e-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="9b64e-107">진행 다시 시작 된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9b64e-107">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b64e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b64e-108">Requirements</span></span>  

 <span data-ttu-id="9b64e-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b64e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b64e-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9b64e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9b64e-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b64e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b64e-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b64e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b64e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b64e-113">See also</span></span>

- [<span data-ttu-id="9b64e-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b64e-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9b64e-115">RuntimeThreadSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="9b64e-115">RuntimeThreadSuspended Method</span></span>](icorprofilercallback-runtimethreadsuspended-method.md)
