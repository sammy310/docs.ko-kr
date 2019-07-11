---
title: ICorProfilerCallback::ExceptionSearchCatcherFound 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 12f16b9bc87ea65e2699ec902d717b08d3155b95
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756174"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="5a3d0-102">ICorProfilerCallback::ExceptionSearchCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="5a3d0-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="5a3d0-103">예외 처리의 검색 단계에서 throw 된 예외에 대 한 처리기가 있는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5a3d0-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a3d0-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a3d0-104">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a3d0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a3d0-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="5a3d0-106">[in] 예외 처리기가 포함 된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a3d0-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a3d0-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a3d0-107">Requirements</span></span>  
 <span data-ttu-id="5a3d0-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a3d0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a3d0-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a3d0-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a3d0-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a3d0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a3d0-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a3d0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a3d0-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="5a3d0-112">See also</span></span>

- [<span data-ttu-id="5a3d0-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a3d0-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
