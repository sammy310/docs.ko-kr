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
ms.openlocfilehash: 064f87fe0cee8d0ad7efcba478e9cf1954a3f291
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699758"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="6b31a-102">ICorProfilerCallback::ExceptionSearchFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="6b31a-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>

<span data-ttu-id="6b31a-103">예외 처리의 검색 단계에서 함수 검색을 완료 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6b31a-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b31a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b31a-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="6b31a-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b31a-105">Requirements</span></span>  

 <span data-ttu-id="6b31a-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b31a-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b31a-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6b31a-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6b31a-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b31a-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b31a-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b31a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b31a-110">참조</span><span class="sxs-lookup"><span data-stu-id="6b31a-110">See also</span></span>

- [<span data-ttu-id="6b31a-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b31a-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6b31a-112">ExceptionSearchFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="6b31a-112">ExceptionSearchFunctionEnter Method</span></span>](icorprofilercallback-exceptionsearchfunctionenter-method.md)
