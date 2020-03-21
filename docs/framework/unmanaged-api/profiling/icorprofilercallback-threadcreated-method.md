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
ms.openlocfilehash: 7fb58c0eb2446253bd658434fc9d68bb857fe0e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175124"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="0e296-102">ICorProfilerCallback::ThreadCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="0e296-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="0e296-103">프로파일러에 스레드가 생성되었음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e296-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e296-104">구문</span><span class="sxs-lookup"><span data-stu-id="0e296-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);
```  
  
## <a name="parameters"></a><span data-ttu-id="0e296-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0e296-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="0e296-106">【인】 생성된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0e296-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e296-107">설명</span><span class="sxs-lookup"><span data-stu-id="0e296-107">Remarks</span></span>  
 <span data-ttu-id="0e296-108">이 `threadId` 값은 즉시 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="0e296-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e296-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0e296-109">Requirements</span></span>  
 <span data-ttu-id="0e296-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e296-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e296-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e296-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e296-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e296-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e296-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e296-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e296-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e296-114">See also</span></span>

- [<span data-ttu-id="0e296-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0e296-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0e296-116">ThreadDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="0e296-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
