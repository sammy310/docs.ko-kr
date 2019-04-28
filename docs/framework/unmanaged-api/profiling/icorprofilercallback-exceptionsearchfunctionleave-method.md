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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bdea3b0cc5b21cd881fe0ff3e0278444a22d083d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598307"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="cce6a-102">ICorProfilerCallback::ExceptionSearchFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="cce6a-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>
<span data-ttu-id="cce6a-103">예외 처리의 검색 단계 함수 검색 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cce6a-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cce6a-104">구문</span><span class="sxs-lookup"><span data-stu-id="cce6a-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="cce6a-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cce6a-105">Requirements</span></span>  
 <span data-ttu-id="cce6a-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cce6a-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cce6a-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cce6a-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cce6a-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cce6a-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cce6a-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cce6a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce6a-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="cce6a-110">See also</span></span>

- [<span data-ttu-id="cce6a-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cce6a-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cce6a-112">ExceptionSearchFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="cce6a-112">ExceptionSearchFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)
