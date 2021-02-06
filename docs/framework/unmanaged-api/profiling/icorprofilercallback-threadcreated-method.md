---
description: '자세히 알아보기: ICorProfilerCallback:: ThreadCreated 메서드'
title: ICorProfilerCallback::ThreadCreated 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type:
- apiref
ms.openlocfilehash: 8b6208856b78298f643161cd6bb78773ac86bc3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657205"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="dc39e-103">ICorProfilerCallback::ThreadCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="dc39e-103">ICorProfilerCallback::ThreadCreated Method</span></span>

<span data-ttu-id="dc39e-104">스레드가 생성 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="dc39e-104">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc39e-105">구문</span><span class="sxs-lookup"><span data-stu-id="dc39e-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);
```  
  
## <a name="parameters"></a><span data-ttu-id="dc39e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc39e-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="dc39e-107">진행 만들어진 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc39e-107">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc39e-108">설명</span><span class="sxs-lookup"><span data-stu-id="dc39e-108">Remarks</span></span>  

 <span data-ttu-id="dc39e-109">`threadId`값이 즉시 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc39e-109">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc39e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc39e-110">Requirements</span></span>  

 <span data-ttu-id="dc39e-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc39e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc39e-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dc39e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dc39e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc39e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc39e-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc39e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc39e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc39e-115">See also</span></span>

- [<span data-ttu-id="dc39e-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc39e-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="dc39e-117">ThreadDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="dc39e-117">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
