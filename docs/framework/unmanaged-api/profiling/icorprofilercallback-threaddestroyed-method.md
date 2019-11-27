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
ms.openlocfilehash: 35b87b3a2c0230b26fb68af44dc1aa864a6449e0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439935"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="3ccd1-102">ICorProfilerCallback::ThreadDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="3ccd1-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="3ccd1-103">스레드가 소멸 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd1-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ccd1-104">구문</span><span class="sxs-lookup"><span data-stu-id="3ccd1-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ccd1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3ccd1-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="3ccd1-106">진행 제거 된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd1-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ccd1-107">설명</span><span class="sxs-lookup"><span data-stu-id="3ccd1-107">Remarks</span></span>  
 <span data-ttu-id="3ccd1-108">이 호출 시에는 `threadId` 값이 더 이상 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ccd1-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ccd1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3ccd1-109">Requirements</span></span>  
 <span data-ttu-id="3ccd1-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ccd1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ccd1-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ccd1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ccd1-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ccd1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ccd1-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ccd1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ccd1-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="3ccd1-114">See also</span></span>

- [<span data-ttu-id="3ccd1-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3ccd1-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="3ccd1-116">ThreadCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="3ccd1-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
