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
ms.openlocfilehash: d9989ef8b1ae50202ba6900b95504a7d50e10dfc
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759484"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="ed68c-103">ICorProfilerCallback::ExceptionSearchFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="ed68c-103">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>

<span data-ttu-id="ed68c-104">예외 처리의 검색 단계가 함수를 검색 하 여 현재 예외에 대 한 처리기를 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ed68c-104">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed68c-105">구문</span><span class="sxs-lookup"><span data-stu-id="ed68c-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed68c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed68c-106">Parameters</span></span>

<span data-ttu-id="ed68c-107">`functionId` 진행 입력 된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed68c-107">`functionId` [in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ed68c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed68c-108">Requirements</span></span>  

 <span data-ttu-id="ed68c-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed68c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed68c-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ed68c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ed68c-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed68c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed68c-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed68c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed68c-113">참조</span><span class="sxs-lookup"><span data-stu-id="ed68c-113">See also</span></span>

- [<span data-ttu-id="ed68c-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed68c-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ed68c-115">ExceptionSearchFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="ed68c-115">ExceptionSearchFunctionLeave Method</span></span>](icorprofilercallback-exceptionsearchfunctionleave-method.md)
