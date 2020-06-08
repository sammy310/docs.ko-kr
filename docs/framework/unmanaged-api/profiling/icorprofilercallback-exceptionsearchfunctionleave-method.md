---
title: ICorProfilerCallback::ExceptionSearchFunctionLeave 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionLeave
helpviewer_keywords:
- ExceptionSearchFunctionLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionLeave method [.NET Framework profiling]
ms.assetid: 01de7ac6-0aad-42ef-bf93-50737667b0a4
topic_type:
- apiref
ms.openlocfilehash: 11ce99fe650f68b80c380c740472e5e0ac8904db
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500184"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="3d14c-102">ICorProfilerCallback::ExceptionSearchFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="3d14c-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>
<span data-ttu-id="3d14c-103">예외 처리의 검색 단계에서 함수 검색을 완료 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3d14c-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d14c-104">구문</span><span class="sxs-lookup"><span data-stu-id="3d14c-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="3d14c-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d14c-105">Requirements</span></span>  
 <span data-ttu-id="3d14c-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d14c-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d14c-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d14c-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d14c-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d14c-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d14c-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d14c-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d14c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d14c-110">See also</span></span>

- [<span data-ttu-id="3d14c-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d14c-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="3d14c-112">ExceptionSearchFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="3d14c-112">ExceptionSearchFunctionEnter Method</span></span>](icorprofilercallback-exceptionsearchfunctionenter-method.md)
