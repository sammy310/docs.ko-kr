---
title: ICorProfilerCallback::ThreadDestroyed 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d4c45290b1ef4360e51b5ed8e1b0fac3dcdde727
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217343"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="1ba84-102">ICorProfilerCallback::ThreadDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="1ba84-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="1ba84-103">스레드 소멸 된 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1ba84-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba84-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ba84-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ba84-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ba84-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="1ba84-106">[in] 소멸 된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1ba84-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ba84-107">설명</span><span class="sxs-lookup"><span data-stu-id="1ba84-107">Remarks</span></span>  
 <span data-ttu-id="1ba84-108">`threadId` 이 호출 시 값이 유효한 이상.</span><span class="sxs-lookup"><span data-stu-id="1ba84-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ba84-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ba84-109">Requirements</span></span>  
 <span data-ttu-id="1ba84-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1ba84-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ba84-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ba84-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1ba84-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ba84-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ba84-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ba84-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba84-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="1ba84-114">See also</span></span>

- [<span data-ttu-id="1ba84-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ba84-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="1ba84-116">ThreadCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="1ba84-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
