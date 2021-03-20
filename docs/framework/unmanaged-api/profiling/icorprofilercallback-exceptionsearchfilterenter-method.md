---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionSearchFilterEnter 메서드'
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
ms.openlocfilehash: 29a9eed75e5d8a954dfb23dedf3d2080e0d139d2
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760220"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="7c90f-103">ICorProfilerCallback::ExceptionSearchFilterEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="7c90f-103">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>

<span data-ttu-id="7c90f-104">예외 처리의 검색 단계에서 사용자 정의 예외 필터를 실행 하기 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7c90f-104">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c90f-105">구문</span><span class="sxs-lookup"><span data-stu-id="7c90f-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c90f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c90f-106">Parameters</span></span>

<span data-ttu-id="7c90f-107">`functionId` 진행 필터를 포함 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7c90f-107">`functionId` [in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="7c90f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c90f-108">Requirements</span></span>  

 <span data-ttu-id="7c90f-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c90f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c90f-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c90f-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c90f-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c90f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c90f-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c90f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c90f-113">참조</span><span class="sxs-lookup"><span data-stu-id="7c90f-113">See also</span></span>

- [<span data-ttu-id="7c90f-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c90f-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7c90f-115">ExceptionSearchFilterLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="7c90f-115">ExceptionSearchFilterLeave Method</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)
