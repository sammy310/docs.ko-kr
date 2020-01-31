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
ms.openlocfilehash: 07041d06668d474a3d30968fb623854a24ebf0eb
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865820"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="763e3-102">ICorProfilerCallback::ThreadDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="763e3-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="763e3-103">스레드가 소멸 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="763e3-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="763e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="763e3-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="763e3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="763e3-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="763e3-106">진행 제거 된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="763e3-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="763e3-107">주의</span><span class="sxs-lookup"><span data-stu-id="763e3-107">Remarks</span></span>  
 <span data-ttu-id="763e3-108">이 호출 시에는 `threadId` 값이 더 이상 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="763e3-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="763e3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="763e3-109">Requirements</span></span>  
 <span data-ttu-id="763e3-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="763e3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="763e3-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="763e3-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="763e3-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="763e3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="763e3-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="763e3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="763e3-114">참조</span><span class="sxs-lookup"><span data-stu-id="763e3-114">See also</span></span>

- [<span data-ttu-id="763e3-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="763e3-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="763e3-116">ThreadCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="763e3-116">ThreadCreated Method</span></span>](icorprofilercallback-threadcreated-method.md)
