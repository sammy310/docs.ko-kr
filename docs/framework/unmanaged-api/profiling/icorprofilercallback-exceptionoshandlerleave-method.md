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
ms.openlocfilehash: 37e3c9139a202e3cb31bd824d182389ae10b7389
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699926"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="e944a-102">ICorProfilerCallback::ExceptionOSHandlerLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="e944a-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>

<span data-ttu-id="e944a-103">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e944a-103">Not implemented.</span></span> <span data-ttu-id="e944a-104">관리 되지 않는 예외 정보가 필요한 프로파일러는 다른 방법으로이 정보를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e944a-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e944a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e944a-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e944a-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e944a-106">Requirements</span></span>  

 <span data-ttu-id="e944a-107">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e944a-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e944a-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e944a-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e944a-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e944a-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e944a-110">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e944a-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e944a-111">참조</span><span class="sxs-lookup"><span data-stu-id="e944a-111">See also</span></span>

- [<span data-ttu-id="e944a-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e944a-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
