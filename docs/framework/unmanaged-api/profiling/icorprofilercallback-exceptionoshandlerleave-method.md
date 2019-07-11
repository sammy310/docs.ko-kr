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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 468c5b28bb5a574aacf623196f0c516992473707
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756232"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="1d635-102">ICorProfilerCallback::ExceptionOSHandlerLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="1d635-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="1d635-103">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="1d635-103">Not implemented.</span></span> <span data-ttu-id="1d635-104">관리 되지 않는 예외 정보를 필요로 하는 프로파일러는 다른 수단을 통해이 정보를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d635-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d635-105">구문</span><span class="sxs-lookup"><span data-stu-id="1d635-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="1d635-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d635-106">Requirements</span></span>  
 <span data-ttu-id="1d635-107">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d635-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d635-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d635-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d635-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d635-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d635-110">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d635-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d635-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="1d635-111">See also</span></span>

- [<span data-ttu-id="1d635-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d635-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
