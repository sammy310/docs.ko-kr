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
ms.openlocfilehash: b222e629cbfce2fde27c2d266b3a343466a1419c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706320"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="a22d6-103">ICorProfilerCallback::ExceptionSearchCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="a22d6-103">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>

<span data-ttu-id="a22d6-104">예외 처리의 검색 단계에서 throw 된 예외에 대 한 처리기를 찾을 때 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a22d6-104">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a22d6-105">구문</span><span class="sxs-lookup"><span data-stu-id="a22d6-105">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a22d6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a22d6-106">Parameters</span></span>

- `functionId`

  <span data-ttu-id="a22d6-107">\[in] 예외 처리기를 포함 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a22d6-107">\[in] The ID of the function that contains the exception handler.</span></span>

## <a name="requirements"></a><span data-ttu-id="a22d6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a22d6-108">Requirements</span></span>  

 <span data-ttu-id="a22d6-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a22d6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a22d6-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a22d6-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a22d6-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a22d6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a22d6-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a22d6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a22d6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a22d6-113">See also</span></span>

- [<span data-ttu-id="a22d6-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a22d6-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
