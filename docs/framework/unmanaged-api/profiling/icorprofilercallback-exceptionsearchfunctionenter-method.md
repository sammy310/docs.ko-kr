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
ms.openlocfilehash: d310ad49debf69d1139f2286cb76e51e9b622ea9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445348"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="a5cac-102">ICorProfilerCallback::ExceptionSearchFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="a5cac-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="a5cac-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span><span class="sxs-lookup"><span data-stu-id="a5cac-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5cac-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5cac-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5cac-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5cac-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a5cac-106">[in] The ID of the function that has been entered.</span><span class="sxs-lookup"><span data-stu-id="a5cac-106">[in] The ID of the function that has been entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5cac-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5cac-107">Requirements</span></span>  
 <span data-ttu-id="a5cac-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5cac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5cac-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5cac-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5cac-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5cac-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5cac-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5cac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5cac-112">참조</span><span class="sxs-lookup"><span data-stu-id="a5cac-112">See also</span></span>

- [<span data-ttu-id="a5cac-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5cac-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a5cac-114">ExceptionSearchFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="a5cac-114">ExceptionSearchFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)
