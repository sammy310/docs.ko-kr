---
description: 'ICorProfilerCallback:: ThreadDestroyed 메서드에 대해 자세히 알아보세요.'
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
ms.openlocfilehash: 63c8c4c523cb398bd7c766fc41bc669a2d74045e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657182"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="ce7a7-103">ICorProfilerCallback::ThreadDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="ce7a7-103">ICorProfilerCallback::ThreadDestroyed Method</span></span>

<span data-ttu-id="ce7a7-104">스레드가 소멸 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ce7a7-104">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce7a7-105">구문</span><span class="sxs-lookup"><span data-stu-id="ce7a7-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce7a7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ce7a7-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="ce7a7-107">진행 제거 된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ce7a7-107">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce7a7-108">설명</span><span class="sxs-lookup"><span data-stu-id="ce7a7-108">Remarks</span></span>  

 <span data-ttu-id="ce7a7-109">`threadId`이 호출 시 값이 더 이상 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce7a7-109">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce7a7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce7a7-110">Requirements</span></span>  

 <span data-ttu-id="ce7a7-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce7a7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce7a7-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ce7a7-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ce7a7-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce7a7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce7a7-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce7a7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7a7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce7a7-115">See also</span></span>

- [<span data-ttu-id="ce7a7-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce7a7-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ce7a7-117">ThreadCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="ce7a7-117">ThreadCreated Method</span></span>](icorprofilercallback-threadcreated-method.md)
