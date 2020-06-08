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
ms.openlocfilehash: 08e76e295e30ede48733ab35870ec965eb157f60
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499872"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="c2b71-102">ICorProfilerCallback::RuntimeResumeStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="c2b71-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="c2b71-103">런타임이 모든 런타임 스레드를 재개 함을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c2b71-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2b71-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2b71-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="c2b71-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2b71-105">Requirements</span></span>  
 <span data-ttu-id="c2b71-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2b71-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2b71-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2b71-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2b71-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2b71-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2b71-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2b71-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b71-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2b71-110">See also</span></span>

- [<span data-ttu-id="c2b71-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2b71-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="c2b71-112">RuntimeResumeFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="c2b71-112">RuntimeResumeFinished Method</span></span>](icorprofilercallback-runtimeresumefinished-method.md)
