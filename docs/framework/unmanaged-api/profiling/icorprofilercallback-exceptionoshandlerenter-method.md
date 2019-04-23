---
title: ICorProfilerCallback::ExceptionOSHandlerEnter 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fcdd52e648b2461036921772b6b5684ba6aec22
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175840"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="24517-102">ICorProfilerCallback::ExceptionOSHandlerEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="24517-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="24517-103">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="24517-103">Not implemented.</span></span> <span data-ttu-id="24517-104">관리 되지 않는 예외 정보를 필요로 하는 프로파일러는 다른 수단을 통해이 정보를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24517-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24517-105">구문</span><span class="sxs-lookup"><span data-stu-id="24517-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="24517-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="24517-106">Requirements</span></span>  
 <span data-ttu-id="24517-107">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="24517-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24517-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24517-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24517-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24517-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24517-110">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24517-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24517-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="24517-111">See also</span></span>

- [<span data-ttu-id="24517-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="24517-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
