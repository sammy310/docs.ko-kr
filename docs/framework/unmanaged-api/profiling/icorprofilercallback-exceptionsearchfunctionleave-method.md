---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionSearchFunctionLeave 메서드'
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
ms.openlocfilehash: 1a30d7ef979f751596cdd723b76eefee3cc1db5a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706151"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="bb022-103">ICorProfilerCallback::ExceptionSearchFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="bb022-103">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>

<span data-ttu-id="bb022-104">예외 처리의 검색 단계에서 함수 검색을 완료 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="bb022-104">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb022-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb022-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="bb022-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb022-106">Requirements</span></span>  

 <span data-ttu-id="bb022-107">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb022-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb022-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bb022-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bb022-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb022-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb022-110">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb022-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb022-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb022-111">See also</span></span>

- [<span data-ttu-id="bb022-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb022-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="bb022-113">ExceptionSearchFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="bb022-113">ExceptionSearchFunctionEnter Method</span></span>](icorprofilercallback-exceptionsearchfunctionenter-method.md)
