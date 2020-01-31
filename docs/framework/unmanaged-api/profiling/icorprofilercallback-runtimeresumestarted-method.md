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
ms.openlocfilehash: c7b52954a6be449de0c3633f0ac648980c6d13f6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865924"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="c2582-102">ICorProfilerCallback::RuntimeResumeStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="c2582-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="c2582-103">런타임이 모든 런타임 스레드를 재개 함을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c2582-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2582-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2582-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="c2582-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2582-105">Requirements</span></span>  
 <span data-ttu-id="c2582-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2582-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2582-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2582-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2582-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2582-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2582-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2582-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2582-110">참조</span><span class="sxs-lookup"><span data-stu-id="c2582-110">See also</span></span>

- [<span data-ttu-id="c2582-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2582-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="c2582-112">RuntimeResumeFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="c2582-112">RuntimeResumeFinished Method</span></span>](icorprofilercallback-runtimeresumefinished-method.md)
