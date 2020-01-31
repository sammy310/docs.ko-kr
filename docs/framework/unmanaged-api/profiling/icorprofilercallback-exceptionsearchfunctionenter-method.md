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
ms.openlocfilehash: a64fe598bd9f50b822edb869fa9efca2a4ff280a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790122"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="3dba3-102">ICorProfilerCallback::ExceptionSearchFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="3dba3-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="3dba3-103">예외 처리의 검색 단계가 함수를 검색 하 여 현재 예외에 대 한 처리기를 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3dba3-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dba3-104">구문</span><span class="sxs-lookup"><span data-stu-id="3dba3-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3dba3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3dba3-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="3dba3-106">\[in] 입력 된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3dba3-106">\[in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="3dba3-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3dba3-107">Requirements</span></span>  
 <span data-ttu-id="3dba3-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3dba3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dba3-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3dba3-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3dba3-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dba3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dba3-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dba3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dba3-112">참조</span><span class="sxs-lookup"><span data-stu-id="3dba3-112">See also</span></span>

- [<span data-ttu-id="3dba3-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3dba3-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="3dba3-114">ExceptionSearchFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="3dba3-114">ExceptionSearchFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)
