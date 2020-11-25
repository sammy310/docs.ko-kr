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
ms.openlocfilehash: d58f2013e93eb1c7030d26ec60b0ab5ab08d0524
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699861"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="29705-102">ICorProfilerCallback::ExceptionSearchFilterEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="29705-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>

<span data-ttu-id="29705-103">예외 처리의 검색 단계에서 사용자 정의 예외 필터를 실행 하기 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29705-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29705-104">구문</span><span class="sxs-lookup"><span data-stu-id="29705-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29705-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29705-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="29705-106">\[in] 필터를 포함 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="29705-106">\[in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="29705-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29705-107">Requirements</span></span>  

 <span data-ttu-id="29705-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29705-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29705-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="29705-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="29705-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29705-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29705-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29705-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29705-112">참조</span><span class="sxs-lookup"><span data-stu-id="29705-112">See also</span></span>

- [<span data-ttu-id="29705-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29705-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="29705-114">ExceptionSearchFilterLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="29705-114">ExceptionSearchFilterLeave Method</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)
