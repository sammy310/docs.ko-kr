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
ms.openlocfilehash: e5fcc9d19a400e23d98a997d051c26af1c1084a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783019"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="c81a6-102">ICorProfilerCallback::RuntimeResumeStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="c81a6-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="c81a6-103">런타임은 모든 런타임 스레드가 다시 시작 하는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c81a6-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c81a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="c81a6-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="c81a6-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c81a6-105">Requirements</span></span>  
 <span data-ttu-id="c81a6-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c81a6-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c81a6-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c81a6-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c81a6-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c81a6-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c81a6-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c81a6-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c81a6-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="c81a6-110">See also</span></span>

- [<span data-ttu-id="c81a6-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c81a6-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c81a6-112">RuntimeResumeFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="c81a6-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
