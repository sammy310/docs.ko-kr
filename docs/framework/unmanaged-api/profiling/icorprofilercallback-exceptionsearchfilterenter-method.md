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
ms.openlocfilehash: 65765795c13948175a7eb5bd78843968d55953d8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445377"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="8a6f5-102">ICorProfilerCallback::ExceptionSearchFilterEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="8a6f5-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="8a6f5-103">예외 처리의 검색 단계에서 사용자 정의 예외 필터를 실행 하기 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8a6f5-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a6f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a6f5-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a6f5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a6f5-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8a6f5-106">진행 필터를 포함 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8a6f5-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a6f5-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a6f5-107">Requirements</span></span>  
 <span data-ttu-id="8a6f5-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a6f5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a6f5-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a6f5-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a6f5-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a6f5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a6f5-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a6f5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a6f5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a6f5-112">See also</span></span>

- [<span data-ttu-id="8a6f5-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a6f5-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="8a6f5-114">ExceptionSearchFilterLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="8a6f5-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
