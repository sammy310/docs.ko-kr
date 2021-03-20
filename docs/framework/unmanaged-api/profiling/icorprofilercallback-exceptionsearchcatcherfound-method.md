---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionSearchCatcherFound 메서드'
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
ms.openlocfilehash: 080e9be61e4f10cbfb60696a5089aca0c3f2843f
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759991"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="30b58-103">ICorProfilerCallback::ExceptionSearchCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="30b58-103">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>

<span data-ttu-id="30b58-104">예외 처리의 검색 단계에서 throw 된 예외에 대 한 처리기를 찾을 때 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="30b58-104">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30b58-105">구문</span><span class="sxs-lookup"><span data-stu-id="30b58-105">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30b58-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="30b58-106">Parameters</span></span>

<span data-ttu-id="30b58-107">`functionId` 진행 예외 처리기를 포함 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="30b58-107">`functionId` [in] The ID of the function that contains the exception handler.</span></span>

## <a name="requirements"></a><span data-ttu-id="30b58-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30b58-108">Requirements</span></span>  

 <span data-ttu-id="30b58-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30b58-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30b58-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30b58-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="30b58-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30b58-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30b58-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30b58-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30b58-113">참조</span><span class="sxs-lookup"><span data-stu-id="30b58-113">See also</span></span>

- [<span data-ttu-id="30b58-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30b58-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
