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
ms.openlocfilehash: 273c3cefa2e67a7d8c429982b4da4126168b2830
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699965"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="5d012-102">ICorProfilerCallback::ExceptionOSHandlerEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="5d012-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>

<span data-ttu-id="5d012-103">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5d012-103">Not implemented.</span></span> <span data-ttu-id="5d012-104">관리 되지 않는 예외 정보가 필요한 프로파일러는 다른 방법으로이 정보를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d012-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d012-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d012-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5d012-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d012-106">Requirements</span></span>  

 <span data-ttu-id="5d012-107">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d012-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d012-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5d012-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5d012-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d012-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d012-110">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d012-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d012-111">참조</span><span class="sxs-lookup"><span data-stu-id="5d012-111">See also</span></span>

- [<span data-ttu-id="5d012-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d012-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
