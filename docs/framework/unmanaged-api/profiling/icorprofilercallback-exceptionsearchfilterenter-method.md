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
ms.openlocfilehash: 96ca2b926217ced6c88f8890f0facc7346fe10c7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790134"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="ddfcf-102">ICorProfilerCallback::ExceptionSearchFilterEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="ddfcf-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="ddfcf-103">예외 처리의 검색 단계에서 사용자 정의 예외 필터를 실행 하기 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ddfcf-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddfcf-104">구문</span><span class="sxs-lookup"><span data-stu-id="ddfcf-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddfcf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ddfcf-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="ddfcf-106">\[in] 필터를 포함 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ddfcf-106">\[in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="ddfcf-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ddfcf-107">Requirements</span></span>  
 <span data-ttu-id="ddfcf-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddfcf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddfcf-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ddfcf-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ddfcf-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddfcf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddfcf-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddfcf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddfcf-112">참조</span><span class="sxs-lookup"><span data-stu-id="ddfcf-112">See also</span></span>

- [<span data-ttu-id="ddfcf-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ddfcf-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ddfcf-114">ExceptionSearchFilterLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="ddfcf-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
