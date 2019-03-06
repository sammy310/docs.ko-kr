---
title: ICorProfilerCallback::ExceptionSearchFunctionEnter 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0615f37d97359f73eb1277da174b7e6401bfc313
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500345"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="e7087-102">ICorProfilerCallback::ExceptionSearchFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="e7087-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="e7087-103">예외 처리의 검색 단계는 현재 예외에 대 한 처리기를 찾아야 하는 함수를 검색 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e7087-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7087-104">구문</span><span class="sxs-lookup"><span data-stu-id="e7087-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7087-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e7087-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="e7087-106">[in] 입력 된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e7087-106">[in] The ID of the function that has been entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7087-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7087-107">Requirements</span></span>  
 <span data-ttu-id="e7087-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7087-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7087-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e7087-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e7087-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7087-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7087-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7087-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7087-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="e7087-112">See also</span></span>
- [<span data-ttu-id="e7087-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7087-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e7087-114">ExceptionSearchFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="e7087-114">ExceptionSearchFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)
