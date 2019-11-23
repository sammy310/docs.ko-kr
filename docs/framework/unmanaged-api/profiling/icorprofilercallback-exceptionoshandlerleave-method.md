---
title: ICorProfilerCallback::ExceptionOSHandlerLeave 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerLeave
helpviewer_keywords:
- ExceptionOSHandlerLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerLeave method [.NET Framework profiling]
ms.assetid: 4d164676-0ee9-4f67-a8ea-cb474db09053
topic_type:
- apiref
ms.openlocfilehash: e54f87f5f02a1857fd9b7639d00d4bcb976665b1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445409"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="373fa-102">ICorProfilerCallback::ExceptionOSHandlerLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="373fa-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="373fa-103">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="373fa-103">Not implemented.</span></span> <span data-ttu-id="373fa-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span><span class="sxs-lookup"><span data-stu-id="373fa-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="373fa-105">구문</span><span class="sxs-lookup"><span data-stu-id="373fa-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="373fa-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="373fa-106">Requirements</span></span>  
 <span data-ttu-id="373fa-107">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="373fa-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="373fa-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="373fa-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="373fa-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="373fa-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="373fa-110">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="373fa-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="373fa-111">참조</span><span class="sxs-lookup"><span data-stu-id="373fa-111">See also</span></span>

- [<span data-ttu-id="373fa-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="373fa-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
