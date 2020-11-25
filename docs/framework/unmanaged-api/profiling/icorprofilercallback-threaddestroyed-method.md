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
ms.openlocfilehash: 0cef868861155d553aba42fe28c3f1f1b86763b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731971"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="38aa9-102">ICorProfilerCallback::ThreadDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="38aa9-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>

<span data-ttu-id="38aa9-103">스레드가 소멸 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38aa9-104">구문</span><span class="sxs-lookup"><span data-stu-id="38aa9-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38aa9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38aa9-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="38aa9-106">진행 제거 된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38aa9-107">설명</span><span class="sxs-lookup"><span data-stu-id="38aa9-107">Remarks</span></span>  

 <span data-ttu-id="38aa9-108">`threadId`이 호출 시 값이 더 이상 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38aa9-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38aa9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38aa9-109">Requirements</span></span>  

 <span data-ttu-id="38aa9-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38aa9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38aa9-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="38aa9-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38aa9-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38aa9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38aa9-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38aa9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38aa9-114">참조</span><span class="sxs-lookup"><span data-stu-id="38aa9-114">See also</span></span>

- [<span data-ttu-id="38aa9-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38aa9-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="38aa9-116">ThreadCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="38aa9-116">ThreadCreated Method</span></span>](icorprofilercallback-threadcreated-method.md)
