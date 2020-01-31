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
ms.openlocfilehash: e27fd3147182e8c820fb1d30f172e0517ca4e77e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866479"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="54fe4-102">ICorProfilerCallback::ExceptionOSHandlerEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="54fe4-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="54fe4-103">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="54fe4-103">Not implemented.</span></span> <span data-ttu-id="54fe4-104">관리 되지 않는 예외 정보가 필요한 프로파일러는 다른 방법으로이 정보를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fe4-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54fe4-105">구문</span><span class="sxs-lookup"><span data-stu-id="54fe4-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="54fe4-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54fe4-106">Requirements</span></span>  
 <span data-ttu-id="54fe4-107">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54fe4-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54fe4-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="54fe4-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="54fe4-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54fe4-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54fe4-110">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54fe4-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54fe4-111">참조</span><span class="sxs-lookup"><span data-stu-id="54fe4-111">See also</span></span>

- [<span data-ttu-id="54fe4-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54fe4-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
