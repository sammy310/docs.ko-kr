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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f8eca3e8eb755e31e704e557ae614a6e5c1f534
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107772"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="33806-102">ICorProfilerCallback::ThreadCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="33806-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="33806-103">스레드 생성 되어 있는지를 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="33806-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33806-104">구문</span><span class="sxs-lookup"><span data-stu-id="33806-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="33806-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="33806-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="33806-106">[in] 만들어진 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="33806-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33806-107">설명</span><span class="sxs-lookup"><span data-stu-id="33806-107">Remarks</span></span>  
 <span data-ttu-id="33806-108">`threadId` 값이 즉시 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="33806-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33806-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33806-109">Requirements</span></span>  
 <span data-ttu-id="33806-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="33806-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33806-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33806-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33806-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33806-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33806-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33806-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33806-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="33806-114">See also</span></span>

- [<span data-ttu-id="33806-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33806-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="33806-116">ThreadDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="33806-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
