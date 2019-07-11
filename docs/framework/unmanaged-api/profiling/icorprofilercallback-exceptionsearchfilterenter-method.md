---
title: ICorProfilerCallback::ExceptionSearchFilterEnter 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterEnter
helpviewer_keywords:
- ExceptionSearchFilterEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFilterEnter method [.NET Framework profiling]
ms.assetid: acc239ce-3eef-418c-b1df-c5a6dd8e8a4c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d39dbf44b21400c8eb5a7abf361dc868b8d39a22
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756104"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="528a9-102">ICorProfilerCallback::ExceptionSearchFilterEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="528a9-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="528a9-103">예외 처리의 검색 단계는 사용자 정의 예외 필터를 실행을 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="528a9-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="528a9-104">구문</span><span class="sxs-lookup"><span data-stu-id="528a9-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="528a9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="528a9-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="528a9-106">[in] ID 필터를 포함 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="528a9-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="528a9-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="528a9-107">Requirements</span></span>  
 <span data-ttu-id="528a9-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="528a9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="528a9-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="528a9-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="528a9-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="528a9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="528a9-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="528a9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="528a9-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="528a9-112">See also</span></span>

- [<span data-ttu-id="528a9-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="528a9-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="528a9-114">ExceptionSearchFilterLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="528a9-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
