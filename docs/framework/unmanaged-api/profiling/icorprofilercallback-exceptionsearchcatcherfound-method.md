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
ms.openlocfilehash: e41378b314b91f42fca9d1039d3011b5eaafe502
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074302"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="35612-102">ICorProfilerCallback::ExceptionSearchCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="35612-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="35612-103">예외 처리의 검색 단계에서 throw 된 예외에 대 한 처리기가 있는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="35612-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35612-104">구문</span><span class="sxs-lookup"><span data-stu-id="35612-104">Syntax</span></span>  
  
```  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35612-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35612-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="35612-106">[in] 예외 처리기가 포함 된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="35612-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35612-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35612-107">Requirements</span></span>  
 <span data-ttu-id="35612-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="35612-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35612-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="35612-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35612-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35612-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35612-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35612-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35612-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="35612-112">See also</span></span>

- [<span data-ttu-id="35612-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35612-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
