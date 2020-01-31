---
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
ms.openlocfilehash: 6514606290bf006443d7011c1a428bebb4cca0f6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865833"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="6ef03-102">ICorProfilerCallback::ThreadCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="6ef03-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="6ef03-103">스레드가 생성 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6ef03-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ef03-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ef03-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="6ef03-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ef03-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="6ef03-106">진행 만들어진 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ef03-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ef03-107">주의</span><span class="sxs-lookup"><span data-stu-id="6ef03-107">Remarks</span></span>  
 <span data-ttu-id="6ef03-108">`threadId` 값이 즉시 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ef03-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ef03-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ef03-109">Requirements</span></span>  
 <span data-ttu-id="6ef03-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ef03-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ef03-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ef03-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6ef03-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ef03-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ef03-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ef03-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef03-114">참조</span><span class="sxs-lookup"><span data-stu-id="6ef03-114">See also</span></span>

- [<span data-ttu-id="6ef03-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ef03-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6ef03-116">ThreadDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="6ef03-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
