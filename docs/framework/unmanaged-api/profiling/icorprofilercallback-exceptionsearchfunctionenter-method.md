---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionSearchFunctionEnter 메서드'
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
ms.openlocfilehash: 6e77ab5dc8c15a1d0785fb83310183c0a4693225
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706190"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="8c8ba-103">ICorProfilerCallback::ExceptionSearchFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="8c8ba-103">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>

<span data-ttu-id="8c8ba-104">예외 처리의 검색 단계가 함수를 검색 하 여 현재 예외에 대 한 처리기를 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ba-104">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c8ba-105">구문</span><span class="sxs-lookup"><span data-stu-id="8c8ba-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c8ba-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8c8ba-106">Parameters</span></span>

- `functionId`

  <span data-ttu-id="8c8ba-107">\[in] 입력 한 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ba-107">\[in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="8c8ba-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c8ba-108">Requirements</span></span>  

 <span data-ttu-id="8c8ba-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c8ba-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c8ba-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8c8ba-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8c8ba-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c8ba-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c8ba-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c8ba-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c8ba-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c8ba-113">See also</span></span>

- [<span data-ttu-id="8c8ba-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c8ba-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="8c8ba-115">ExceptionSearchFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="8c8ba-115">ExceptionSearchFunctionLeave Method</span></span>](icorprofilercallback-exceptionsearchfunctionleave-method.md)
