---
title: ICorProfilerCallback::RuntimeResumeStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b163d41280c8ea49554cecb845c4be757f55dfc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921981"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="e0b60-102">ICorProfilerCallback::RuntimeResumeStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="e0b60-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="e0b60-103">런타임은 모든 런타임 스레드가 다시 시작 하는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e0b60-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0b60-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0b60-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="e0b60-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0b60-105">Requirements</span></span>  
 <span data-ttu-id="e0b60-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0b60-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0b60-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0b60-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0b60-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0b60-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0b60-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0b60-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0b60-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="e0b60-110">See also</span></span>

- [<span data-ttu-id="e0b60-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0b60-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e0b60-112">RuntimeResumeFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="e0b60-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
